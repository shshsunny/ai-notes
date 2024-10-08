- PROM：可编程只读存储器，**与阵列固定，或阵列可编程**。实际上不是时序逻辑电路的存储器，就是通过硬件编码形成的组合逻辑电路。
- PLA：可编程逻辑阵列，**与、或阵列均可编程**。
- PAL：可编程阵列逻辑，**与阵列可编程、或阵列固定**。
- GAL：**通用**阵列逻辑。相较于PAL，最大区别是==**输出逻辑宏单元可编程定义**==。

- CPLD：复杂可编程逻辑器件，由若干类似于PAL的宏单元组成，有更复杂功能。

- 存储器阵列：相较于触发器构成的寄存器，能更节约材料地**批量存储数据**。分为RAM、ROM（但实际上都采用随机存取方式）
	- RAM：分为动态、静态两种
		- SRAM静态随机存取存储器：MOS管多，价格较高；需要一直保持通电维持数据，功耗较大。读写快。
		- DRAM动态随机存取存储器：用电容表示存储内容，读出时根据**电容放电**情况判断内容为0或1，是**破坏性读出**，需要定时刷新（加强电容电荷）。价格低、功耗小、集成度较高，因为电容充放电较慢，**读写速度较慢**。
	- ROM：除了PROM之外还有其他可擦除、可电擦除电改写的类型。EPROM, EEPROM