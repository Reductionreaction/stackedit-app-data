# TraverPlanner
[TravelPlanner: A Benchmark for Real-World Planning with Language Agents](https://arxiv.org/abs/2402.01622)
分为两种规划方法：
- two-stage: 首先使用FlightSearch这些工具，然后根据所搜索到的结果再进行规划
- sole：将需要规划的信息直接提供给LLM，然后进行规划
![输入图片说明](/imgs/2024-09-09/2evWr3U5S5QKVS0o.png)
规划中有一些约束：
Environmental-Constraint: 两地之间没有交通工具，没有对应的景点
Commonsense Constraint:不能提供数据集中没有的城市，信息要完整（如不能出现一天没有住宿的情况），交通工具选择合理
Hard-Constraint: 总预算，住宿要求，饮食要求
![输入图片说明](/imgs/2024-09-09/2VG9BqHbzRjSiNM9.png)
得出的结论是及时是GPT4也只有0.6%的通过率，单纯通过LLM和数据库进行Travel Plan是不可行的
并没有在文章中看到有关训练的具体细节，没有搞懂是怎么进行训练的，这篇文章似乎是提出和尝试解决了一个问题

[Large Language Models Can Plan Your Travels Rigorously with Formal
Verification Tools](https://arxiv.org/abs/2404.11891)
在上篇文章的基础上进行了改进，首先将用户的自然语言转为JSON，然后在LLM的帮助下一步步将JSON转化为SMT solver的代码判断数据库中的信息是否能够满足这个规划，再通过LLM整理信息进行输出。这样就解决了two-stage中LLM无法理解并使用工具的问题
![输入图片说明](/imgs/2024-09-09/bSnj93akpV4h7hEE.png)
这样的结果得出的正确率很高
[SMT solver](https://www.youtube.com/watch?v=UmAZMVrJnHM&list=PLqinEaadXCHYW_1Z3W05rNx0skQIxrmQB)

<!--stackedit_data:
eyJoaXN0b3J5IjpbMzk3OTAwNzMzLC0zMTQ1MzY3NDFdfQ==
-->