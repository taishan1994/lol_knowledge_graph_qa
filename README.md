# lol_knowledge_grapg_qa
基于英雄联盟知识图谱的问答

# 说明

- spider.py：爬取数据，可参考，但这里并没有使用。
- build_lol_graph.py：构建知识图谱
- question_classification：给定问题，识别里面的实体以及问题的类型。
- question_parser.py：根据问题类型生成neo4j的sql语句。
- answer_search.py：执行sql并构建返回的结果。
- chatbot_graph.py：程序的主入口。

# 依赖

```python
py2neo版本：py2neo-2021.2.3
neo4j版本：neo4j-4.4.5
```

# 运行

在安装好neo4j之后，运行以下指令构建图谱：

```python
python build_lol_graph.py
```

然后运行以下指令进行问答：

```python
python chatbot_graph.py
```

#### 结果

```python
咨询:盖伦的种族
客服机器人: 盖伦的种族是：人类
咨询:盖伦的角色
客服机器人: 盖伦的角色是：战士
咨询:盖伦的介绍
客服机器人: 盖伦的介绍是：身为一位自豪而且高贵的士兵，盖伦奋战在无畏先锋的最前沿。他深受战友们的爱戴，也受到敌人们的尊敬——同样重要地，他还是冕卫家族的名门之后，肩负着守卫德玛西亚及其理念的重任。他身披抵御魔法的重甲，手持阔剑，时刻准备着用正义的钢铁风暴在战场上正面迎战一切操纵魔法的狂人。
咨询:盖伦的别称
客服机器人: 盖伦的别称是：德玛西亚之力
咨询:孙悟空的徒弟是谁
客服机器人: 孙悟空的徒弟是：易
咨询:德玛西亚区域有哪些英雄
客服机器人: 德玛西亚包含的英雄有：薇恩；嘉文四世；塞拉斯；加里奥；盖伦；菲奥娜；奎因；娑娜；凯尔；赵信；波比；希瓦娜；拉克丝；莫甘娜
咨询:德玛西亚有哪些风景
客服机器人: 德玛西亚的景色有：光明使者神殿；德玛西亚城的宏伟广场；英勇之厅；密银城；黎明城堡
咨询:具有徒弟关系的有哪些
客服机器人: 具有徒弟关系的有：孙悟空|易；布兰德|瑞兹；塔莉垭|亚索
咨询:德玛西亚的介绍
客服机器人: 德玛西亚的介绍是：德玛西亚是一个法理至上的强大王国，战功赫赫，久负盛名。德玛西亚人自古崇尚正义、荣耀和责任，近乎狂热地以自身的传统及底蕴为豪。然而，尽管秉持着这些高尚的原则，在过去的几百年间，刚愎自用的德玛西亚越发与世隔绝，成为了孤立主义的代名词。然而现在，王国中已经出现了变数。德玛西亚雄都以禁魔石——一种可以抑制魔法能量的白色岩石——为基，起初是符文战争之后为了躲避魔法侵害的人们所建立的庇护地。王权由中心向外辐射，守护着边远的城镇、农田、森林和矿产丰饶的山脉。然而，自从嘉文三世国王突然驾崩，各大家族至今仍未赞同他唯一的继承人嘉文王子继位。在王国眼中，重兵把守的边境之外已经是异心遍起，许多原先的附庸在乱世来临之际开始寻求来自别处的庇护。有人私下妄言，德玛西亚的黄金时代已经一去不返，除非臣民能够上下一心，顺应时代的变化——许多人认为他们并没有这样的能力，否则王国的衰败在所难免。再多的禁魔石，也无法阻止德玛西亚由内而外的覆灭。
```

# 参考

> https://github.com/liuhuanyong/QASystemOnMedicalKG
>
> 数据来源：openkg
