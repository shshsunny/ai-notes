![[Pasted image 20240627173214.png]]![[Pasted image 20240627173426.png]]
注意：这是两种不同的PC增量顺序。一种是在取出指令之后PC就变成当前指令的下一条指令的地址，即图2；另一种是在完成指令译码之后算出下地址，但下地址直到下个时钟边沿触发到来时才写入PC，相当于PC增量在每个周期最后进行，然后从PC指示的新地址读取新指令，即图1。自己比较习惯图1，因为书上的实现主要是按照图1来的。两种都对。


# CPU的基本组成
CPU包括：
- 数据通路Datapath：包括数据流动的线路和线路上的元件。元件包括操作原件（组合逻辑电路）和状态原件（时序逻辑电路）。数据通路是由操作原件、状态原件通过总线或分散方式连接而成的**存储、处理和传送数据**的路径。
- 控制组件Control Unit：即控制器，用于生成控制信号调度各模块等。

需要注意：整个CPU是一个**庞大的时序逻辑电路**，可能存在clock skew（时钟偏移），时钟信号到达各组件有略微的不同步，clock skew的值取为**时钟信号到达第一个组件和到达最后一个组件之间的时差**。时钟周期的设计必须容忍时钟偏移：$t_{clk}>t_{ffpd(max)}+t_{comb(max)}+t_{setup}+t_{clk-skew}$。
# 计算机性能与时间指标

性能考察的基本指标：
- 吞吐率——单位时间内**完成的工作量**。更具体化——带宽：单位时间内**传输**的信息量。
- 响应时间：从作业提交到完成的耗时。
	- 执行时间：用户感觉到的程序执行时间，并不是程序真正的执行时间
		- **用户CPU时间：CPU用于执行本程序所有指令的时间**
		- 其他时间：包括在不同线程之间切换所需的访存、输入输出等
	- 等待时间

CPU性能与系统性能不等同，后者由前者综合其他外部设备性能而成。CPU性能只用用户CPU时间度量。

用户CPU时间的计算：
- 时钟周期、时钟频率
- **CPI：Cycles per instruction：执行一条指令所需的时钟周期数**。对于整个指令集而言取平均值。
用户CPU时间=程序时钟周期总数（该程序所有指令执行所需时钟周期数）×时钟周期=CPI×指令总数

执行同样的程序，用户CPU时间越短，计算机性能越好。**性能可以视为用户CPU时间的倒数**。
# CPU设计流程
列出要实现的所有指令->用RTL语言表达->列举并连接需要的操作元件和状态元件成为实现各个指令的数据通路->确定**在各个指令执行中数据通路各个部位分别需要什么样的控制信号**->综合确定指令与控制信号的对应关系，列出真值表，实现逻辑表达式->根据逻辑表达式设计组合逻辑电路得到控制器。

下面是单周期CPU的设计

## 单周期CPU数据通路
以实现RV32I的9条典型指令为例。RV32I的指令长度为32位，RV32C的指令长度为16位（2字节），因此为提高用立即数表达指令跳转的能力，imm12左移1位（乘2）之后得到的才是前后地址增量（按字节编址）。

基础组件：
- 立即数扩展器：根据6种类型的指令格式（实际只有I,U,S,B,J五种有立即数，R不带立即数，可以将R情况下的扩展器输出视为无意义），从指令中正确读取、拼接立即数部分并进行符号扩展SEXT。
- ALU：实现满足各指令功能的算术逻辑运算功能。包括：加减法、位运算（按位与、或等），并输出标志位。另外也有原封不动输出某个操作数的功能，目的是简化数据通路，即便不需要计算的数据也流经ALU。
- 取指令部件