[法律声明](01_legal_statement.md)

1. [如何使用此书](chapter01_how_to_use_this_book/sec00.md)<br />
1.1 [路标](chapter01_how_to_use_this_book/sec01_roadmap.md)<br />
1.2 [快速测验](chapter01_how_to_use_this_book/sec02_quick_quizzes.md)<br />
1.3 [其他参考](chapter01_how_to_use_this_book/sec03_alternatives_to_this_book.md)<br />
1.4 [例子源代码](chapter01_how_to_use_this_book/sec04_sample_source_code.md)<br />
1.5 [这是谁的书](chapter01_how_to_use_this_book/sec05_whose_book_is_this.md)<br />

2. [简介](chapter02_introduction/sec00.md)<br />
2.1 导致并行编程困难的历史原因<br />
2.2 并行编程的目标<br />
2.2.1 性能<br />
2.2.2 生产率<br />
2.2.3 通用性<br />
2.3 并行编程的替代方案<br />
2.3.1 顺序应用多实例化<br />
2.3.2 使用现有的并行软件<br />
2.3.3 性能优化<br />
2.4 是什么使并行编程变得困难？<br />
2.4.1 工作分割<br />
2.4.2 并行访问控制<br />
2.4.3 资源分割和复制<br />
2.4.4 与硬件交互<br />
2.4.5 组合使用<br />
2.4.6 语言和环境如何对这样的任务进行支持<br />
2.5 讨论<br />

3. 硬件及其习性<br />
3.1 概述<br />
3.1.1 CPU流水线<br />
3.1.2 内存引用<br />
3.1.3 原子操作<br />
3.1.4 内存屏障<br />
3.1.5 Cache Miss<br />
3.1.6 I/O操作<br />
3.2 开销<br />
3.2.1 硬件体系结构<br />
3.2.2 操作的开销<br />
3.3 硬件的免费午餐?<br />
3.3.1 3D集成<br />
3.3.2 新材料和新工艺<br />
3.3.3 专用加速器<br />
3.3.4 现有的并行软件<br />
3.4 软件设计Implication<br />

4. 工具<br />
4.1 脚本语言<br />
4.2 POSIX多进程<br />
4.2.1 POSIX进程创建和撤销<br />
4.2.2 POSIX线程的创建和撤销<br />
4.2.3 POSIX锁<br />
4.2.4 POSIX读写锁<br />
4.3 原子操作<br />
4.4 Linux内核中类似POSIX的操作<br />
4.5 趁手的工具——该如何选择？<br />

5. 计数<br />
5.1 为什么并发计数不可小看？<br />
5.2 统计计数器<br />
5.2.1 设计<br />
5.2.2 基于数组的实现<br />
5.2.3 结果一致的实现<br />
5.2.4 基于每线程变量的实现<br />
5.2.5 讨论<br />
5.3 近似上限计数器<br />
5.3.1 设计<br />
5.3.2 简单的上限计数器实现<br />
5.3.3 关于简单上限计数器的讨论<br />
5.3.4 近似上限计数器的实现<br />
5.3.5 关于近似上限计数器的讨论<br />
5.4 精确上限计数器<br />
5.4.1 原子上限计数器的实现<br />
5.4.2 关于原子上限计数器的讨论<br />
5.4.3 Signal-Theft上限计数器的设计<br />
5.4.4 Signal-Theft上限计数器的实现<br />
5.4.5 Signal-Theft上限计数器讨论<br />
5.5 特殊的并行计数器<br />
5.6 并行计数的讨论<br />
5.6.1 并行计数的性能<br />
5.6.2 并行计数的规格<br />
5.6.3 并行计数学得到什么<br />

6. 分割和同步设计<br />
6.1 分割练习<br />
6.1.1 哲学家就餐问题<br />
6.1.2 双端队列<br />
6.1.3 关于分割问题示例的讨论<br />
6.2 设计准则<br />
6.3 同步粒度<br />
6.3.1 串行程序<br />
6.3.2 代码锁<br />
6.3.3 数据锁<br />
6.3.4 数据所有权<br />
6.3.5 锁粒度与性能<br />
6.4 并行快速路径<br />
6.4.1 读写锁<br />
6.4.2 层级锁<br />
6.4.3 资源分配器缓存<br />
6.5 超越分隔<br />
6.5.1 并行工作队列的迷宫求解<br />
6.5.2 迷宫求解的可选并行方案<br />
6.5.3 性能比较１<br />
6.5.4 迷宫求解的可选串行方案<br />
6.5.5 性能比较2<br />
6.5.6 未来的方向和结论<br />
6.6 分隔、并行和优化<br />

7. 锁<br />
7.1 生存（staying alive）<br />
7.1.1 死锁<br />
7.1.2 活锁<br />
7.1.3 不公平<br />
7.1.4 低效率<br />
7.2 锁的类型<br />
7.2.1 互斥锁<br />
7.2.2 读写锁<br />
7.2.3 Beyond Reader-Writer Locks<br />
7.2.4 scoped locking<br />
7.3 锁实现事宜<br />
7.3.1 基于automic exchange的排他锁实现<br />
7.3.2 其他排他锁实现<br />
7.4 基于锁的存在担保（existence guarantee）<br />
7.5 锁是英雄还是恶棍<br />
7.5.1 应用程序的锁是英雄<br />
7.5.2 并行库中的锁只是另一个工具<br />
7.5.3 并行化里串行库的锁就是恶棍<br />
7.6 总结<br />

<!--
8. 数据所有者………………………………………………………………………………. 140

9. 延迟处理………………………………………………………………………………….. 142
9.1. 屏障…………………………………………………………………………………… 142
9.2. 引用计数……………………………………………………………………………. 142
9.2.1. 引用计数类型的实现……………………………………………………. 143
9.2.2. 支持引用计数的Linux原语 …………………………………………. 150
9.2.3. 计数器优化………………………………………………………………….. 151
9.3. Read-Copy Update（RCU）………………………………………………… 151
9.3.1. RCU基础 ……………………………………………………………………. 151
9.3.2. RCU用法 ……………………………………………………………………. 163
9.3.3. Linux内核中的RCU API……………………………………………… 176
9.3.4. “玩具式”的RCU实现 ……………………………………………… 183
9.3.5. RCU练习 ……………………………………………………………………. 206

9. 使用RCU ………………………………………………………………………………… 207
9.1. RCU和基于每线程变量的统计计数器 ……………………………….. 207
9.1.1. 设计…………………………………………………………………………….. 207
9.1.2. 实现…………………………………………………………………………….. 207
9.1.3. 讨论…………………………………………………………………………….. 211
9.2. RCU和可移除I/O设备的计数器 ……………………………………….. 211

10. 验证：调试及分析……………………………………………………………………. 214

11. 数据结构………………………………………………………………………………….. 216

12. 高级同步………………………………………………………………………………….. 218
12.1. 避免锁……………………………………………………………………………….. 218
12.2. 内存屏障……………………………………………………………………………. 218
12.2.1. 内存序及内存屏障…………………………………………………. 218
12.2.2. 如果B在A后面, 并且C在B后面, 为什么C不在A后面? 220
12.2.3. 变量可以拥有多个值……………………………………………… 221
12.2.4. 能信任什么东西? …………………………………………………… 222
12.2.5. 锁实现回顾……………………………………………………………. 229
12.2.6. 一些简单的规则…………………………………………………….. 230
12.2.7. 抽象内存访问模型…………………………………………………. 230
12.2.8. 设备操作……………………………………………………………….. 233
12.2.9. 保证………………………………………………………………………. 233
12.2.10. 什么是内存屏障? …………………………………………………… 234
12.2.11. 锁约束…………………………………………………………………… 247
12.2.12. 内存屏障示例………………………………………………………… 248
12.2.13. CPU ………………………………………………………………………. 251
12.2.14. 哪里需要内存屏障? ……………………………………………….. 253
12.3. 非阻塞同步………………………………………………………………………… 253
12.3.1. 简单 NBS ……………………………………………………………… 253
12.3.2. 冒险指针……………………………………………………………….. 253
12.3.3. 原子数据结构………………………………………………………… 253
12.3.4. “Macho” NBS………………………………………………………… 253

13. 易于使用………………………………………………………………………………….. 254
13.1. Rusty Scale for API Design ………………………………………………….. 254
13.2. Shaving the Mandelbrot Set ………………………………………………….. 255

14. 时间管理………………………………………………………………………………….. 258

15. 未来的冲突………………………………………………………………………………. 259
15.1. 可交易内存………………………………………………………………………… 259
15.1.1. I/O 操作 ……………………………………………………………….. 260
15.1.2. RPC 操作 ……………………………………………………………… 260
15.1.3. 内存映射操作………………………………………………………… 261
15.1.4. 多线程事务……………………………………………………………. 262
15.1.5. 外部的事务访问…………………………………………………….. 263
15.1.6. 延时………………………………………………………………………. 264
15.1.7. 锁………………………………………………………………………….. 264
15.1.8. 读者-写者锁 ………………………………………………………….. 265
15.1.9. 持续性…………………………………………………………………… 266
TM如何提供类似的持续性功能？……………………………………………………….. 266
15.1.10. 动态链接装载………………………………………………………… 266
15.1.11. 调试………………………………………………………………………. 267
15.1.12. exec() 系统调用…………………………………………………….. 268
15.1.13. RCU ……………………………………………………………………… 268
15.1.14. 讨论………………………………………………………………………. 270
15.2. 共享内存并行编程……………………………………………………………… 270
15.3. 基于任务的并行编程………………………………………………………….. 270
-->
