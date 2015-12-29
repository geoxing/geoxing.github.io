title: 2015 summary
date: 2015-12-08 09:42:39
categories: 
- All   
tags: 
- Summary
- Anniversary
- Prototype
- Commercial-Grade
- Product
---

![Einstein](https://raw.githubusercontent.com/geoxing/photos/master/Einstein.jpg)


## 工作

### 科研项目统计 

|模块数|开发代码数|测试用例数|培训积分|组织培训数|工会积分|
|----- |:------:|-------:|------:|--------:|------:|
|51|8000|333|56|1|15|

### 智能固话中的日历项目-人力外包

- 需求 - 没想透
 1. 让需求跑起来。
 2. 功能之间相互交叉影响到底怎么样的，每个功能与其他功能是否相互影响，比如默认日历与日历设置。
 3. 清晰的业务逻辑代表了清晰的代码，逻辑不闭合，必然引入更多的bug。
- 人员招聘 - 太难
 1. 总体：老手带新手，并制定一人负责。
 2. 测试：至少为开发人员的一半，最少两名。
- 迭代开发
 1. 分模块，边测边改。
 2. 每日站会，讨论实现细节。
 3. code review。
 
### 日历规范及扩展，29本

- CalDAV规范
- WebDAV规范
- iCalendar规范

### 后端开发

- 使用了Apple的开源项目[calendarserver](http://www.calendarserver.org/),http://www.calendarserver.org/
- 这是一个有着32万行代码，历时13年，还在现网运行的史前（oo）巨无霸项目
- 学会了Python的Twisted、协程等异步与并行

### Android端开发

- 使用开源的[davdroid](https://davdroid.bitfire.at/what-is-davdroid), 开发了日历同步插件
- From Eclipse to Android Studio
- 学会了gradle、lombok

### Web版开发

- 使用开源[caldavzap](http://www.inf-it.com/open-source/clients/caldavzap/)，开发了[日历Web版](http://211.136.90.50/) (http://211.136.90.50/)
- 学习、使用了WebApp开发中最新的框架React、VueJs、metero等
- Developer下一个大事，全新的开发模式  
![nextGenWebApp](https://raw.githubusercontent.com/geoxing/photos/master/nextgenwebpp.jpg)
- 学会了MarkDown排版，在GitHub建立了自己的[静态博客](http://geoxing.github.io/), http://geoxing.github.io/  
  1. 写给自己看，对知识进行沉淀、强化  。
  2. 分享？ 别人看不看没关系，自己爽了就够了。  
  3. 注意细节
     - 字体，什么是（无）衬线字体？什么字体适用于什么场景？ 什么是编程字体（等宽字体），都有哪些？
     - 标点符号
     ```
     error: Byte Press(née Tangcha ) is the best Chinese-language eBook app.Period.
     right: Byte Press (née Tangcha) is the best Chinese-language eBook app. Period.
     error: 13927396856
     right: (86) 139 2739 6856 or (86) 139-2739-6856
     ```
     - 大小写，APP的拼写对吗？应该是APP、App，它有复数形式吗，是什么？

### From Prototype to Commercial-Grade Product 
- 开发
 1. 每一行代码都可被Measure、Profiling、Tested。
 2. 工程化，阿里的「大中台，小前台」架构，让小白也能够写出高质量的代码。
 3. code review，可以统计每个开发人员的实际效率、代码贡献率，phabricator from facebook，google’s C++ coding style guide。
- 测试、集成、部署： 充分的解耦，并行   

 原型产品：开发=>提交=>打包=>测试=>开发。。。=>发布新版。  
![image](https://raw.githubusercontent.com/geoxing/photos/master/ci1.png)  
![image](https://raw.githubusercontent.com/geoxing/photos/master/ci1p.png)
 1. 提测和集成阶段混在一起，提测代码质量较差，开发人员不断的提交修改bug从而导致不断的集成包。
 2. 测试与开发相互影响：发布前回归如发现问题只能等待开发人员修改bug，然后重新出包，再进行一轮回归，如此反复工作量很大。
 2. 模块之间相互影响，一个模块的代码有问题就会影响整个项目的开发人员，任何一个编译不过的问题会造成整个团队在等待。
 3. 回滚只能做到代码级别的回滚。
 
 商业产品:  
![image](https://raw.githubusercontent.com/geoxing/photos/master/ci3.png)  
![image](https://raw.githubusercontent.com/geoxing/photos/master/ci3p.png)
 1. 各个bundle在有着自己的需求、开发、测试计划，相互独立。
 2. 制定发布计划，确定集成窗口和发布时间点, 在集成窗口时间bundle可以自主提交集成。
 3. 集成提交需要走流程，包括填写checklist、代码检查、bug统计、提前编译预集成包进行测试等。这就避免了明显的集成问题遗漏到集成环境中。
 4. 集成期间的集成包每天出一个或者两个，避免了测试人员不断拿包回归的情况。
 5. 集成窗口对于时间要求严格，赶不上计划或者质量不达标的bundle不予集成。
 6. **可以做到随时集成、随时发布、随时回滚**。
 7. **需要搭建代码审核、打包平台、发布平台、测试平台、舆情监控平台，自动化实现**。

- 运营
 1. 以指标驱动-Dashboard，可以发现到底是技术的问题、Marketing的问题。
 2. 每一个商业产品的后台监控管理系统的代码都是功能代码的两倍，甚至更高，为运营、决策、需求做出数字依据。
 3. 根据自己业务特点，CAP（Consistency，Availability，Partition tolerance）的优先级。

## 生活

- 瘦了，从150到140，减少6.7% (Quantified Self, QS)，彻底消除了脂肪肝 (Fatty Liver)

## 展望
 > 「我就是不喜歡舒舒服服的。」——古畑 (tian) 任三郎 
