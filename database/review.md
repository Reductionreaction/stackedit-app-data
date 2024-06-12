

**课程内容与学时分配：**

**第一章** **数据库系统概述（****2****学时）**
1.1基本概念

- 数据库、
- 数据库管理系统、
- 数据库系统、
- 数据库管理员

1.2 数据库系统的发展及趋势

<![if !supportLists]>1.3 <![endif]>数据库系统的特点

<![if !supportLists]>u <![endif]>数据集成化、数据独立性、数据共享、数据冗余、数据的安全性、完整性和一致性、并发控制和故障恢复

<![if !supportLists]>1.4 <![endif]>数据库内部结构体系

<![if !supportLists]>u <![endif]>数据库的三级结构：三级模式、二级映射

**第二章** **数据模型** **（****6****学时）**

<![if !supportLists]>2.1 <![endif]>数据模型的基本概念

<![if !supportLists]>u <![endif]>概念数据模型、逻辑数据模型、物理数据模型

<![if !supportLists]>2.2 <![endif]>数据模型的四个世界

<![if !supportLists]>2.3 <![endif]>概念世界与概念模型

<![if !supportLists]>u <![endif]>E-R模型与E-R图：实体、属性、联系

<![if !supportLists]>u <![endif]>扩充E-R模型与扩充E-R图：IS-A联系、弱实体

<![if !supportLists]>u <![endif]>面向对象模型：对象、对象标识符、类、方法、超类和子类、聚合和分解、继承和合成、方法、消息、封装

<![if !supportLists]>2.4 <![endif]>信息世界和逻辑模型

<![if !supportLists]>u <![endif]>关系模型：关系、属性、值域、元组、关系数据库、关键字

<![if !supportLists]>2.5 <![endif]>计算机世界与物理模型

<![if !supportLists]>u <![endif]>磁盘组织与文件系统

<![if !supportLists]>u <![endif]>逻辑模型的物理存储：项、记录、文件、索引、集簇

**第三章** **关系数据库系统** **（****14****学时）**

<![if !supportLists]>3.1 <![endif]>关系数据库系统概述

<![if !supportLists]>3.2 <![endif]>关系数据库系统的衡量准则

<![if !supportLists]>u <![endif]>完全关系型的十二条衡量准则

<![if !supportLists]>u <![endif]>空值（NULL）

<![if !supportLists]>3.3 <![endif]>关系模型数学理论—关系代数

<![if !supportLists]>3.3.0 <![endif]>关系模型

<![if !supportLists]>u <![endif]>关系数据结构

<![if !supportLists]>l <![endif]>表结构：表框架、表的元数与基数

<![if !supportLists]>l <![endif]>关系：二维表的性质

<![if !supportLists]>l <![endif]>关键字：候选关键字、主关键字、外关键字

<![if !supportLists]>l <![endif]>关系数据库：关系子模式—视图（view）

<![if !supportLists]>u <![endif]>关系操纵

<![if !supportLists]>l <![endif]>数据查询：两个关系的合并、单个关系内的元组选择、单个关系内的属性指定

<![if !supportLists]>l <![endif]>数据删除、插入、修改

<![if !supportLists]>l <![endif]>空值的处理

<![if !supportLists]>u <![endif]>关系中的数据约束

<![if !supportLists]>l <![endif]>实体完整性约束、参照完整性约束、用户定义的完整性

<![if !supportLists]>3.3.1 <![endif]>关系的表示

<![if !supportLists]>u <![endif]>关系的表示、迪卡尔乘积

<![if !supportLists]>3.3.2 <![endif]>关系操纵的表示

<![if !supportLists]>u <![endif]>关系代数中的五种基本运算：选择、投影、笛卡儿积、并、差

<![if !supportLists]>u <![endif]>基本运算的应用实例

<![if !supportLists]>3.3.3 <![endif]>关系模型与关系代数

<![if !supportLists]>3.3.4 <![endif]>关系代数中的扩充运算

<![if !supportLists]>u <![endif]>交、除法、联接与自然联接、外联接

<![if !supportLists]>u <![endif]>扩充运算的应用实例

<![if !supportLists]>3.3.5 <![endif]>关系代数实例

<![if !supportLists]>u <![endif]>综合的关系代数应用实例

<![if !supportLists]>3.4 <![endif]>关系数据库语言SQL’92

<![if !supportLists]>3.4.1 <![endif]>SQL概貌

<![if !supportLists]>u <![endif]>SQL标准的发展历史、SQL的基本概念与使用方式、SQL功能简介

<![if !supportLists]>3.4.2 <![endif]>SQL数据定义功能

<![if !supportLists]>u <![endif]>SQL中的数据类型、Oracle数据类型

<![if !supportLists]>u <![endif]>基本的表结构定义和修改命令

<![if !supportLists]>3.4.3 <![endif]>SQL数据操纵功能

<![if !supportLists]>u <![endif]>SQL语言与关系代数的关系

<![if !supportLists]>u <![endif]>映像语句结构

<![if !supportLists]>u <![endif]>基本查询功能：LIKE、IS NULL谓词、表的联接查询与自联接查询、ORDER BY子句的功能

<![if !supportLists]>u <![endif]>嵌套查询：IN、SOME/ANY/ALL，EXISTS等谓词、相关子查询与独立子查询

<![if !supportLists]>u <![endif]>子查询的合并：UNION / INTERSECT / EXCEPT [ALL]运算

<![if !supportLists]>u <![endif]>统计查询：统计与分组统计查询、空值与空集在统计函数中的处理方法

<![if !supportLists]>u <![endif]>复杂数据查询：两层的NOT EXISTS嵌套结构以实现关系代数中的除法运算的查询功能

<![if !supportLists]>3.4.4 <![endif]>SQL的更新功能

<![if !supportLists]>u <![endif]>删除功能

<![if !supportLists]>u <![endif]>插入功能：常量元组的插入、带子查询的元组插入

<![if !supportLists]>u <![endif]>修改功能

<![if !supportLists]>3.4.5 <![endif]>视图

<![if !supportLists]>u <![endif]>视图概念、视图与基表的区别

<![if !supportLists]>u <![endif]>视图的定义命令：嵌套定义功能

<![if !supportLists]>u <![endif]>视图的删除命令：视图删除中的连锁反应

<![if !supportLists]>u <![endif]>视图上的数据访问：可更新视图

<![if !supportLists]>u <![endif]>视图的优点

**第四章** **数据库的安全性与完整性保护（****6****学时）**

<![if !supportLists]>4.1 <![endif]>数据库的安全性保护

<![if !supportLists]>u <![endif]>数据库的安全与安全数据库

<![if !supportLists]>u <![endif]>数据库安全的基本概念与内容：主体、客体、身份标识与鉴别、自主访问控制、强制访问控制、隐蔽通道、审计

<![if !supportLists]>u <![endif]>数据库的安全标准：国标GB17859

<![if !supportLists]>u <![endif]>SQL对数据库安全的支持：SQL语言所提供的与数据库安全保护有关的命令

<![if !supportLists]>4.2 <![endif]>数据库的完整性保护

<![if !supportLists]>u <![endif]>数据库完整性保护的功能：目的与常用实现措施

<![if !supportLists]>u <![endif]>完整性规则的三个内容：实体完整性、参照完整性、用户定义完整性

<![if !supportLists]>u <![endif]>完整性约束的设置、检查与处理：在SQL语言的CREATE TABLE命令中提供的完整性约束定义子句

<![if !supportLists]>u <![endif]>触发器

<![if !supportLists]>**第五章** <![endif]>**事务处理、并发控制与故障恢复技术（****10****学时）**

<![if !supportLists]>5.1 <![endif]>事务处理

<![if !supportLists]>u <![endif]>事务的定义与ACID性质

<![if !supportLists]>u <![endif]>事务活动及其状态转换图

<![if !supportLists]>u <![endif]>事务控制及相关的参数设置语句：事务的提交与回滚、事务的读/写类型与隔离级别

<![if !supportLists]>u <![endif]>事务的语句组成成分

<![if !supportLists]>5.2 <![endif]>并发控制技术

<![if !supportLists]>u <![endif]>事务

<![if !supportLists]>l <![endif]>事务的并发性、并发控制

<![if !supportLists]>l <![endif]>调度、串行调度、可串行化调度、冲突与冲突可串行化、冲突可串行化的判定方法

<![if !supportLists]>l <![endif]>三种数据不一致现象：丢失修改、脏读、不可重复读

<![if !supportLists]>u <![endif]>封锁

<![if !supportLists]>l <![endif]>共享锁、排它锁、所相容矩阵、合适事务

<![if !supportLists]>l <![endif]>基于封锁技术的并发控制实现方法

<![if !supportLists]>l <![endif]>封锁协议：三级封锁协议、两阶段封锁协议

<![if !supportLists]>l <![endif]>合法调度：两阶段封锁协议与冲突可串行化的关系

<![if !supportLists]>l <![endif]>多粒度封锁：封锁粒度与多粒度封锁、意向锁及其锁相容矩阵、多粒度封锁协议

<![if !supportLists]>l <![endif]>死锁及其解决方法、活锁及其解决方法

<![if !supportLists]>5.3 <![endif]>数据库恢复技术

<![if !supportLists]>u <![endif]>数据库恢复的含义、方法和常用措施

<![if !supportLists]>u <![endif]>数据库故障的分类

<![if !supportLists]>u <![endif]>数据库故障恢复三大技术

<![if !supportLists]>l <![endif]>数据转储：静态转储/动态转储、海量转储/增量转储

<![if !supportLists]>l <![endif]>日志：

<![if !supportLists]>– <![endif]>日志的内容、组成、作用与记载原则

<![if !supportLists]>– <![endif]>UNDO日志的记录格式、记载规则以及使用UNDO日志的恢复过程、UNDO日志中的静止/非静止检查点的设置方法以及使用带检查点的UNDO日志的恢复过程

<![if !supportLists]>– <![endif]>REDO日志的记录格式、记载规则以及使用REDO日志的恢复过程、REDO日志中的（非静止）检查点的设置方法以及使用带检查点的REDO日志的恢复过程

<![if !supportLists]>– <![endif]>UNDO日志与REDO日志的区别与不足

<![if !supportLists]>– <![endif]>UNDO/REDO日志的记录格式、记载规则以及使用UNDO/ REDO日志的恢复过程、UNDO/REDO日志中的检查点的设置方法以及使用带检查点的UNDO/REDO日志的恢复过程

<![if !supportLists]>l <![endif]>事务的撤销（UNDO）与重做（REDO）

<![if !supportLists]>u <![endif]>恢复策略：小型/中型/大型故障的恢复策略

<![if !supportLists]>u <![endif]>数据库镜像

<![if !supportLists]>**第六章** <![endif]>**数据库中的数据交换（****2****学时）**

<![if !supportLists]>6.1 <![endif]>概述

<![if !supportLists]>u <![endif]>数据交换的五种方式

<![if !supportLists]>6.2 <![endif]>数据交换的管理

<![if !supportLists]>u <![endif]>会话管理

<![if !supportLists]>u <![endif]>连接管理

<![if !supportLists]>u <![endif]>游标管理：游标的定义、打开、使用与关闭命令、可滚动游标的定义及其在数据更新命令中的使用

<![if !supportLists]>u <![endif]>诊断管理

<![if !supportLists]>u <![endif]>动态SQL

<![if !supportLists]>6.3 <![endif]>数据交换的流程

<![if !supportLists]>6.4 <![endif]>数据交换的四种方式

<![if !supportLists]>u <![endif]>嵌入式SQL：嵌入式SQL的编程方式及其程序结构

<![if !supportLists]>u <![endif]>自含式SQL：函数与过程

<![if !supportLists]>u <![endif]>调用层接口：ODBC/JDBC函数的基本使用流程

<![if !supportLists]>u <![endif]>Web方式

<![if !supportLists]>**第七章** <![endif]>**数据库的物理组织（****4****学时）**

<![if !supportLists]>7.1 <![endif]>概论

<![if !supportLists]>7.2 <![endif]>数据库的物理存储介质

<![if !supportLists]>u <![endif]>计算机物理存储介质的层次划分

<![if !supportLists]>7.3 <![endif]>磁盘存储器及其结构

<![if !supportLists]>u <![endif]>计算机磁盘存储器的物理组织方式

<![if !supportLists]>7.4 <![endif]>文件组织

<![if !supportLists]>u <![endif]>文件的组织结构

<![if !supportLists]>u <![endif]>文件中的记录在磁盘上的分配方式

<![if !supportLists]>u <![endif]>定长记录与变长记录的组织方式

<![if !supportLists]>7.5 <![endif]>文件记录组织

<![if !supportLists]>u <![endif]>堆文件、顺序文件、散列文件、聚集文件

<![if !supportLists]>7.6 <![endif]>索引技术与散列技术

<![if !supportLists]>u <![endif]>顺序文件的组织方式

<![if !supportLists]>u <![endif]>索引文件的组织方式

<![if !supportLists]>l <![endif]>在顺序文件上的索引技术：稠密索引、稀疏索引、多级索引

<![if !supportLists]>l <![endif]>非顺序文件中的索引技术

<![if !supportLists]>l <![endif]>具有重复键值的索引、多维索引

<![if !supportLists]>u <![endif]>B/B+树文件

<![if !supportLists]>l <![endif]>树的结构与各个节点的组成内容

<![if !supportLists]>l <![endif]>B+树上的搜索、插入、删除算法

<![if !supportLists]>l <![endif]>B+的特点及其与B树的区别

<![if !supportLists]>u <![endif]>HASH文件：散列索引文件的组织方式

<![if !supportLists]>7.7 <![endif]>数据库与文件

**第八章** **关系数据库规范化理论（****8****学时）**

<![if !supportLists]>8.1 <![endif]>概述

<![if !supportLists]>u <![endif]>模式设计质量的评价指标：数据冗余度、插入/删除等更新异常

<![if !supportLists]>8.2 <![endif]>规范化理论

<![if !supportLists]>8.2.1 <![endif]>函数依赖

<![if !supportLists]>u <![endif]>各种函数依赖的定义：完全/部分FD、平凡/非平凡FD、直接/传递FD

<![if !supportLists]>u <![endif]>Armstrong公理系统

<![if !supportLists]>u <![endif]>使用函数依赖定义的关键字

<![if !supportLists]>u <![endif]>属性集闭包与关键字的计算算法

<![if !supportLists]>8.2.2 <![endif]>与函数依赖有关的范式

<![if !supportLists]>u <![endif]>范式：1NF、2NF、3NF、BCNF

<![if !supportLists]>u <![endif]>各级范式的分解方法

<![if !supportLists]>8.2.3 <![endif]>多值依赖与第四范式

<![if !supportLists]>u <![endif]>多值依赖、与多值依赖有关的推理规则、4NF

<![if !supportLists]>8.3 <![endif]>规范化所引起的一些问题

<![if !supportLists]>u <![endif]>函数依赖的逻辑蕴涵、函数依赖集的等价、最小函数依赖集及其判定条件、最小函数依赖集的计算算法

<![if !supportLists]>u <![endif]>模式分解的无损联结性、依赖保持性及其判定方法

<![if !supportLists]>u <![endif]>直接到3NF且满足无损联结性和依赖保持性的模式分解算法

**第九章** **数据库设计（****6****学时）**

<![if !supportLists]>9.1 <![endif]>数据库设计概述

<![if !supportLists]>u <![endif]>数据库设计的基本任务、数据库的生命周期

<![if !supportLists]>9.2 <![endif]>数据库设计的需求分析

<![if !supportLists]>u <![endif]>需求说明书

<![if !supportLists]>9.3 <![endif]>数据库的概念设计

<![if !supportLists]>u <![endif]>数据库概念设计的过程

<![if !supportLists]>u <![endif]>视图集成的原理、策略与步骤、冲突的解决办法

<![if !supportLists]>9.4 <![endif]>数据库的逻辑设计

<![if !supportLists]>u <![endif]>E-R模型和扩充E-R模型向关系模型的转换

<![if !supportLists]>9.5 <![endif]>数据库的物理设计

<![if !supportLists]>u <![endif]>存储结构、存取路径、集簇、索引

**第十章** **数据库管理（****2****学时）**

<![if !supportLists]>10.1<![endif]>数据库管理概述

<![if !supportLists]>10.2<![endif]>数据库管理的内容

<![if !supportLists]>10.3<![endif]>数据库管理员DBA

<![if !supportLists]>10.4<![endif]>数据库性能配置和优化（缓冲池、数据重组、查询优化）

<![if !supportLists]>10.5<![endif]>数据库管理系统

**上机实验（****8****学时）**

<![if !supportLists]>1．<![endif]>实验目的

<![if !supportLists]>1) <![endif]>加深对数据库课程的理解

<![if !supportLists]>2) <![endif]>通过实验掌握一种数据库产品的SQL语言的使用方法与操作能力

<![if !supportLists]>3) <![endif]>通过数据库建模实践培养学生分析问题与解决问题的能力

<![if !supportLists]>2．<![endif]>实验要求

<![if !supportLists]>w <![endif]>实验一（2课时）：熟悉一种数据库产品的操作使用环境，掌握交互方式下SQL语言的数据操纵功能

<![if !supportLists]>w <![endif]>实验二（2课时）：掌握SQL语言的数据定义功能，包括各种完整性约束和简单的触发器

<![if !supportLists]>w <![endif]>实验三（2课时）：掌握高级程序设计语言与数据库的数据交换，以及简单的存储过程和存储函数

<![if !supportLists]>w <![endif]>实验四（2课时）：掌握数据库的建模设计

<![if !supportLists]>3．<![endif]>实验方法

<![if !supportLists]>1) <![endif]>所有实验应由学生个人独立完成（不推荐学生以组为单位完成）

<![if !supportLists]>2) <![endif]>所有实验都在系教学用计算机机房中进行，但学生可以提前在机房或属舍里进行练习

<![if !supportLists]>3) <![endif]>教师及助教检查学生的实验报告和代码，并给出成绩，计入课程总分中

**课程考核方法**

课后作业（20%）+ 上机实验（10%）+ 期末考试（70%）

**教材**

<![if !supportLists]>[1] <![endif]>徐洁磐, 柏文阳, 刘奇志. 数据库系统实用教程. 高等教育出版社, 2006

**参考书**

<![if !supportLists]>[2] <![endif]>王珊, 萨石煊. 数据库系统概论（第5版）. 高等教育出版社, 2014

<![if !supportLists]>[3] <![endif]>A. Silberschatz, H.E. Korth, S. Sudarshan. Database System Concepts (6th Ed.). 杨冬青 等译. 机械工业出版社, 2012

<![if !supportLists]>[4] <![endif]>施伯乐, 丁宝康, 汪卫. 数据库系统教程（第3版）. 高等教育出版社, 2008

<![if !supportLists]>[5] <![endif]>J.D. Ullman, J. Widom. A First Course in Database Systems (3rd Ed.). 岳丽华 等译. 机械工业出版社, 2009

<![if !supportLists]>[6] <![endif]>H. Garcia-Molina, J.D. Ullman, J. Widom. Database System Implementation (2nd Ed.). 杨冬青 等译. 机械工业出版社, 2010
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTU3ODAyNzczXX0=
-->