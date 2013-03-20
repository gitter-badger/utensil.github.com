--- 
title: 考完试后  
tags: 自学记录
---

终于考完试了！！！更可喜的是在考试结束之前，我已经把所有的课程设计、所有的作业做完交上去了，当其他人还在忙课程设计的时候，我已经玩完一天回来了。

列一下一些紧迫的任务：

前段时间以Thorqq的华为802.1x认证程序为蓝本，进行移植工作。主要是消除Dot1x类对libpcap以外的东西的依赖（对Windows API、MFC或Winpcap的依赖），修改了一些命名方式。消除依赖的过程中，运用了Bridge模式（疑似）和Template Method模式。这样这个类的重用性大大提高了。这个过程中，研究了Cisco关于802.1x的一些课件，Thorqq的文章，还有发现了远远好用过Sniffer的Wireshark，一只脚踏进了嗅包分析协议的大门。同时还发现了libnet（网上有两个libnet，是google搜不到的那个），这样，大多数的协议的帧的构建就变得易如反掌，了解其背后机理也不必苦啃RFC，啃它的头文件就好了，哈哈~

第一个任务就是将已经半成品（事实上已经可以用了，我现在上网就用它）的802.1x认证的类库，更深入地进行拆解，尤其是必须重写UserData这个Struct为一到两个类。工作的一个难点是MAC地址的获取、IP地址的获取，较难直接写成非平台、非类库依赖的，有了一些线索，但还有待实现。不知道是不是只要把网卡设在非混杂模式，就能不需要MAC地址（主要是过滤表达式要用）...目前的测试来看是可以不要的，但是无法了解会出什么意外。

第二个任务是整理Screenshot Generator的代码，针对gtk下的无法设透明度的情况，暂时采用DummyFrame，对截屏过程不进行视觉提示。实现延时截屏。上载对最新的发布。在三个平台下得到现有的截图，传给B。 第三个任务是整理这个学期下载到的类库、工具等，刻几张toolkit碟，使得我能够在其他电脑上建立起工作环境，因为我即将离开这台电脑。

光这些已经做死人了....还有：尽量多做几道Google Code Jam的题；研究python和translate库，看看实现doxygen2po的可能性大不大；研究spirit库和编译原理；最近终于琢磨清楚怎么使用wxWidgets的RegEx类了，也学会了怎么实现Search...

事实上，我还有三个突发奇想：

一个是实现一个wxLatexCtrl，可以解析一段Latex代码，并予以显示。想首先做数学公式显示方面的。

第二个是，受最近学到的一些知识的启发，觉得可以实现一种我叫做arp线扯线的病毒，使得网络上所有的电脑都把ip地址和MAC地址搞混，以致瘫痪，而我的电脑可以独享带宽。

第三个是，我认为之所以以前可以两个号（802.1x认证帐号）同时上（只要同时点），是因为微弱的时差形成了帧与帧的夹心饼状况，理论上可以人为制造同一网段的多台机器的认证帧的夹心饼，从而实现一个帐号多人上网。

一些近来关注的关键词：

* CURL
* wxSqlLite
* CppUnit
* FreeType

顺便庆祝一下，《C和指针》买回来了...