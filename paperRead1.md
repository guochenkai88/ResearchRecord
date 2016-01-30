PAPERS1
===================


some papers have been read today, record them 

----------


Modelgen: Mining Explicit Information Flow Specifications from Concrete Executions（ISSTA2015）
-------------
提供一种生成摘要（model，specification）的方法，解决静态分析的不足：**不能处理动态结构如反射**，**不能识别人工语言**，**不能处理底层语言（JNI）**，**不能很好地扩展**。

> **Specification Example**

> - **a->b** indicates  that  there  is  a  possible  flow  from a  to b. Whatever information was accessible from a
before the call is now potentially accessible from b
after the call. If a is a reference, the information accessible from a includes all objects transitively reachable through other object references in fields.
> - **this** is the instance object for the modeled method.
> - **return** is the return value of the method.
arg#i is the i-th positional argument of the method.  For
a static method, argument indices begin at 0.  For instance  methods, arg#0 is  an  alias  for this and  positional arguments begin with arg#1.
> - **\$SOURCE** is a source of information flow and represents a resource, external to the program, from which the API method reads some sensitive information (e.g. \$CONTACTS, \$LOCATION ,$FILE).
> - **!SINK** is an information sink and represents a location outside of the program to which the information 
ows (e.g. !INTERNET, !FILE)

主要是设计了一套model语言,与显式的数据流有关，可以作为STAMP系统的输入，较之之前的人工model作为输入，效果大幅提高。最后分析了测试集的质量。

> 网址： [http://theory.stanford.edu/~aiken/publications/papers/issta15.pdf](http://theory.stanford.edu/~aiken/publications/papers/issta15.pdf)


----------
Static Control-Flow Analysis of User-Driven Callbacks in Android Applications（ICSE2015）
--

> 网址 [http://dacongy.github.io/papers/yang-icse15.pdf](http://dacongy.github.io/papers/yang-icse15.pdf)

提供上下文敏感的一种方法针对生成GUI的callback控制流图进行分析，并且为GUI驱动生成了一种静态的model，测试该驱动的可行性。


----------
Composite Constant Propagation: Application to Android Inter-Component Communication Analysis（icse2015）
--
> 网址 [http://www.patrickmcdaniel.org/pubs/icse15b.pdf](http://www.patrickmcdaniel.org/pubs/icse15b.pdf)

解决一种称为  (Multi-Valued Composite) MVC composite constant propagation的问题，在ICC上。该问题用COAL语言描述，然后用COAL solver去推测所有的ICC值，对于460个apps。与之前的方法相比有优势，且可以用于其他的程序分析。

其实主要处理implicit intent中的URI

---------------
GUITAR: Piecing Together Android App GUIs from Memory Images（ccs2015）
---
> 网址 [http://www.cs.wm.edu/~ksun/csci680-f15/papers/GUITAR_CCS_15.pdf](http://www.cs.wm.edu/~ksun/csci680-f15/papers/GUITAR_CCS_15.pdf)

主要是一种从memory image中重构GUI的方法，供犯罪取证。主要的挑战是，当app进入后台，则会释放资源，但是通过调查发现，即使进入后台，其40%到80%的资源还是会被保存下来，不影响恢复。

----
Towards Automatic Generation of Security-Centric Descriptions for Android Apps（ccs2015）
--
> 网址 [hhttp://delivery.acm.org/10.1145/2820000/2813669/p518-zhang.pdf?ip=137.132.250.12&id=2813669&acc=ACTIVE%20SERVICE&key=FF6731C4D3E3CFFF.BB5EB8D2067C1662.4D4702B0C3E38B35.4D4702B0C3E38B35&CFID=578899414&CFTOKEN=60967893&__acm__=1454133878_fd7c7d49c856df1dc34c1e6babd46c2e](http://delivery.acm.org/10.1145/2820000/2813669/p518-zhang.pdf?ip=137.132.250.12&id=2813669&acc=ACTIVE%20SERVICE&key=FF6731C4D3E3CFFF.BB5EB8D2067C1662.4D4702B0C3E38B35.4D4702B0C3E38B35&CFID=578899414&CFTOKEN=60967893&__acm__=1454133878_fd7c7d49c856df1dc34c1e6babd46c2e)

介绍了一种自动化生成permission与调用函数关系的描述，让用户更方便了解。

---
From System Services Freezing to System Server Shutdown in Android: All You Need Is a Loop in an App（ccs2015）
--
> 网址 [http://www.cse.psu.edu/~sxz16/papers/p1236-huang.pdf](http://www.cse.psu.edu/~sxz16/papers/p1236-huang.pdf)

对android中的system server进行dos攻击，找到一种称为 Android Stroke Vulnerabilities  (ASVs)的漏洞。利用ActivityManager以及WindowManager等对其进行循环的DOS攻击，因为system server在android系统中起关键作用，因此攻击更加有效。

----
Mining Apps for Abnormal Usage of Sensitive Data（icse2015）
--
> 网址 [https://www.st.cs.uni-saarland.de/appmining/mudflow/icse2015-mudflow.pdf](https://www.st.cs.uni-saarland.de/appmining/mudflow/icse2015-mudflow.pdf)

比较benign和malicious apps中每个从source出发的数据流，挖掘他们的不同，利用分类方法。挖掘的结果表明：**1** 这些数据流一般都流向了少量的sink，**2 **这些sink在benign和malicious中区分明显， **3**这种区分可用于标记malicious，**4** malicious根据他们的数据流即可认定

---
Jekyll ∗ on iOS: When Benign Apps Become Evil（usenix2013）
--
> 网址 [https://www.usenix.org/system/files/conference/usenixsecurity13/sec13-paper_wang-updated-8-23-13.pdf](https://www.usenix.org/system/files/conference/usenixsecurity13/sec13-paper_wang-updated-8-23-13.pdf)

为了躲避apple store的review，Jekyll在提交的时候是完全符合要求的，这样就可以顺利提交。但是可以远程操控，重新安排那些被“标记”的代码，让它们变的恶意。



----------





### Catalog


[TOC]


