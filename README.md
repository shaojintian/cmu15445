# CMU15445-2021-FALL

在本课程项目中，需要完成关系数据库`bustub`的磁盘页面缓冲池、索引功能、查询执行功能以及并发控制功能。并在课程中学习关如下知识：

- 关系数据库的基本概念，以及基于SQLite简易关系数据库的SQL语句语法及其实践；
- 关系数据库中页面存储、页面布局及元组布局等数据库物理存储模型，以及DBMS中的页面缓冲池的功能及原理；
- 关系数据库中索引的功能及分类，以及基于B+-tree和可扩展哈希表的可磁盘备份索引的具体实现及并发控制；
- 关系数据库中元组排序、聚合、连接功能的具体实现和性能分析，连接、聚合、插入等物理查询计划的具体执行策略，以及基于启发式和成本模型的查询计划优化方法；
- 关系数据库中事务的基本概念及其所应达到的标准ACID(原子性、一致性、隔离性、持久性)的定义及要求；
- 关系数据库中并发控制协议（即执行多个事务的方式）的悲观及乐观实现策略，如两阶段锁、基于时间戳并发控制、多版本并发控制；
- 关系数据库中保证原子性、隔离性、持久性的崩溃恢复算法的策略，包括日志、检查点、重做和撤销操作；
## 课程项目笔记

### Project 0 : C++ primer [note0](https://github.com/jlu-xiurui/CMU15445-2021-FALL/blob/ghess/p2-refinement/notes/Project%200%20%20C%2B%2B%20Primer.md)

实现一个简单的矩阵运算类，用于检查实验者的基本C++编程水平。

### Project 1 : BUFFER POOL [note1](https://github.com/jlu-xiurui/CMU15445-2021-FALL/blob/ghess/p2-refinement/notes/Project%201%20%20BUFFER%20POOL.md)

在本实验中，需要在存储管理器中实现缓冲池。缓冲池负责将物理页面从磁盘中读入内存、或从内存中写回磁盘，使得DBMS可以支持大于内存大小的存储容量。并且，缓冲池应当是用户透明且线程安全的。

### Project 2 : EXTENDIBLE HASH INDEX [note2](https://github.com/jlu-xiurui/CMU15445-2021-FALL/blob/ghess/p2-refinement/notes/Project%202%20%20EXTENDIBLE%20HASH%20INDEX.md)

在本实验中，需要实现一个**磁盘备份**的**可扩展哈希表**，用于DBMS中的索引检索。磁盘备份指该哈希表可写入至磁盘中，在系统重启时可以将其重新读取至内存中使用。可扩展哈希表是动态哈希表的一种类型，其特点为桶在充满或清空时可以桶为单位进行桶分裂或合并，尽在特定情况下进行哈希表全表的扩展和收缩，以减小扩展和收缩操作对全表的影响。

本文介绍了书中未讲解的**低位可拓展哈希表**的原理及其实现，且原理与实现之间设置了跳转以方便阅读。

### Project 3 : QUERY EXECUTION [note3](https://github.com/jlu-xiurui/CMU15445-2021-FALL/blob/ghess/p2-refinement/notes/Project%203%20%20QUERY%20EXECUTION.md)

在关系数据库中，SQL语句将被转换为逻辑查询计划，并在进行查询优化后转化为物理查询计划，系统通过执行物理查询计划完成对应的语句功能。在本实验中，需要为`bustub`实现物理查询计划执行功能，包括顺序扫描、插入、删除、更改、连接、聚合以及`DISTINCT`和`LIMIT`。

### Project 4 : CONCURRENCY CONTROL [note4](https://github.com/jlu-xiurui/CMU15445-2021-FALL/blob/ghess/p2-refinement/notes/Project%204%20%20CONCURRENCY%20CONTROL.md)

本实验将实现`bustub`中的锁管理器，其负责跟踪数据库中使用的元组级锁，以使得数据库支持并发的查询计划执行。
