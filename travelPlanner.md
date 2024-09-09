# TraverPlanner
[TravelPlanner: A Benchmark for Real-World Planning with Language Agents](https://arxiv.org/abs/2402.01622)
分为两种规划方法：
- two-stage: 首先使用FlightSearch这些工具，然后根据所搜索到的结果再进行规划
- sole：将需要规划的信息直接提供给LLM，然后进行规划
规划中有一些约束：
Environmental-Constraint: 两地之间没有交通工具，没有对应的景点
Commonsense Constraint:不能提供数据集中没有的城市，信息要完整（如不能出现一天没有住宿的情况），交通工具选择合理
Hard-Constraint: 总预算，住宿要求，饮食要求
![输入图片说明](/imgs/2024-09-09/2VG9BqHbzRjSiNM9.png)


[SMT solver](https://www.youtube.com/watch?v=UmAZMVrJnHM&list=PLqinEaadXCHYW_1Z3W05rNx0skQIxrmQB)

<!--stackedit_data:
eyJoaXN0b3J5IjpbNzI4ODA3Njk5LC0zMTQ1MzY3NDFdfQ==
-->