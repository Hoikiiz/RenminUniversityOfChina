## 一. 分布式系统特征
参考地址：https://mp.weixin.qq.com/s/On19LgaiiP6CkdXNGO3tQA
### 1. 什么叫分布式系统？ 举例说明现实生活中的分布式系统，阐述系统组成部分与功能特点。


答：分布式系统是一个硬件或软件组件分布在不同的网络计算机上，通过消息传递进行通信和协调的系统。
；

举例 - Web搜索

·        底层物理设施，它由超大数目的位于全世界多个数据中心的联网计算机组成；

·        分布式文件系统，支持超大文件，并根据搜索和其他应用的使用方式（特别是在文件中以快速而持久的速度读取）进行了深度优化；

·        相关的结构化分布式存储系统，它提供对超大数据集的快速访问；

·        锁服务，它提供诸如分布式加锁和协定等分布式系统功能；

·        编程模式，它支持对底层物理基础设施上的超大并行和分布式计算的管理。

### 2. 分布式系统的特征是什么？

答案来自课件+百度

答：

·        并发性 - 程序通过共享资源并行

·        缺乏全局时钟 - 分布式系统中的计算机只能通过本地时钟交换消息；不可预测的消息延迟限制了准确性；没有一个全局时钟的概念。

·        故障独立性 - 计算机中的故障或程序中的异常马上不能被与之通讯的其他组件感知；系统设计者需要为故障处理做计划。

### 3. 给出能被共享的5种类型的硬件资源和5种类型的数据或软件资源。给出它们在实际的分布式系统中发生共享的例子。

### 4. 在分布式系统中，常常说， “避免性能瓶颈” 。可否举例说明并谈谈你的观点。

我的观点就是没有观点

### 5. 在故障处理（Failure handling）中，什么叫容错？什么叫冗余？

答案来自百度

答：

冗余：指重复配置系统的一些部件,当系统发生故障时,冗余配置的部件介入并承担故障部件的工作,由此减少系统的故障时间。通常指通过多重备份来增加系统的可靠性。

容错：容错是用冗余的资源使计算机具有容忍故障的能力，即在产生故障的情况下，仍有能力将指定的算法继续完成。

容错技术是指在一定程度上容忍故障的技术，也称为故障掩盖技术（fault masking）。采用容错技术的系统称容错系统。

容错主要依靠冗余设计来实现，它以增加资源的办法换取可靠性。由于资源的不同，冗余技术分为硬件冗余、软件冗余、时间冗余和信息冗余。

### 6. 现今分布式操作系统的挑战有：Heterogeneity（异构性），Openness（开放性），Security（安全性），Scalability（可伸缩性），Failure handling（故障处理），Concurrency（并发性），Transparency（透明性），等。分别给出挑战的定义，举例与详细分析挑战涉及的关键技术。

答案来自百度

答：

一：异构性。网络、计算机硬件、操作系统、编程语言、由不同的开发者完成的软件实现都是造成异构性的主因。其中网络的异构通过互联网协议相互通信而被屏蔽；中间件的流行屏蔽的底层网络、硬件、操作系统和编程语言的异构，它为分布式应用和服务器提供了一直的计算模型，包括RPC、远程事件通知、远程SQL访问和分布式事物调用；虚拟机也是使代码到处运行的一种方法。

二：开放性。它取决于新的资源共享服务能被增加和供多种客户程序使用的程度。特征就是发布系统的关键接口，使其基于一致的通信机制，让不同提供商提供异构硬件和软件。

三：安全性。包括三个部分：机密性（防止泄露给未授权的个人）、完整性（防止被改变或被破坏）、可用性（防止对访问资源的手段的干扰）。其中有两个重要的安全问题：拒绝服务攻击和移动代码的安全性仍然没有得到圆满解决。

四：可伸缩性。顾名思义就是随着资源数量的增加和用户访问的增加，系统仍然能保持其有效性，该系统就被称为可伸缩的。其中有控制物理资源的开销、控制性能损失、防止软件资源用尽和避免性能瓶颈四大挑战。

五：故障处理。在一个分布式系统中，硬件或软件都会出现未知的故障或者不正常运行，因此故障处理是贯穿整个系统的难题。容错（设计容错机制如重传）、故障恢复（数据恢复或“回滚”保证一致性）、冗余（多条路由或者备份等技术）都是故障处理技术。

六：并发性。多个用户对同一资源的使用，要保持操作的正确性就必须在数据保持一致的基础上同步。如使用操作系统的信号量。

七：透明性。

    1. 访问透明性：用相同的操作访问本地资源和远程资源（电子邮件）

    2. 位置透明性：不需要知道资源的物理位置或网络位置（电子邮件、URL）

3. 并发透明性：几个进程能并发的使用共享资源而不互相干扰

4. 复制透明性：使用资源的多个实例提升可靠性和性能，而用户和程序员无需知         道副本的相关信息

    5. 故障透明性：屏蔽错误

    6. 移动透明性：资源和客户能够在系统内移动而不受影响（移动电话）

    7. 性能透明性：负载变化时，系统能够被重新配置以提高性能

    8. 伸缩透明性：系统和应用能够进行扩展而不改变系统结构和应用算法

## 二. 系统模型
### 1.分布式系统模型设计时，设计者常常面对的分布式系统的困难与威胁问题有哪些？

答案来自课件

答：

1）  使用模式的多样性：

·        系统组件承受各种工作负载

例如：Web每天有几百万的访问量

·        系统断线或连接不稳定

例如：系统中包括移动计算机

·        系统对带宽与延迟的特殊要求

例如：多媒体应用

 2） 系统环境的多样性：

·        容纳异构硬件、操作系统和网络

·        网络在性能上有很大的不同

例如：无线网的速度只达到局域网的几分之一

·        支持不同规模的系统

从几十台计算机到几百万台计算机

3）   内部问题：

·        非同步时钟

·        冲突的数据更新

·        系统组件的软硬件故障

4）   外部问题：

·        数据完整性

·        保密性的攻击

·        服务拒绝攻击

### 2. 分布式系统体系结构元素包括：通信实体、通信范型、角色和责任、放置，以客户-服务器系统体系结构为例解释相应元素概念。

答案来自书《分布式系统：概念与设计（原书第5版）》

答：

通信实体 - 客户端与服务器端的通信（对象，组件，web服务），底层进程间的通信。

通信范型 - 分布式系统中实体如何通信。客户-服务器结构中最常见的通信范型是远程调用，如用于支持客户-服务器计算的请求-应答协议是一个有效的模式。

角色和责任 - 在客户-服务器结构中，进程扮演服务器和客户的角色。特别是，为了访问服务器管理的共享资源，客户进程可以与不同主机上的服务器进行交互。

放置 - 对象或服务这样的实体是怎样映射到底层的物理分布式基础设施上的，物理分布式基础设施由大量的机器组成，这些机器通过一个任意复杂的网络互联。从决定分布式系统特性的角度而言，放置是关键的，这些特性大多数与性能相关，也包括其他特性如可靠性和安全性。放置需要考虑实体间的通信模式、给定机器的可靠性和它们当前的负载、不同机器之间的通信质量等。

### 3. 什么叫层次化软件体系结构？举例说明。

### 4. 什么叫瘦客户？举例说明你的观点。

答案来自百度

答：瘦客户是指一个软件层，它支持用户端的计算机上基于窗口的用户界面，而在远程的计算机上执行应用程序。

### 5. 举例说明并图示异步分布式系统中，不同网络结点间进程的 “事件的实时排序” 。（参考图2-13）

### 6. 分布式系统的基础模型有哪些？分别可以解决哪些问题？

答案来自课件+百度

答：

1)   交互模型 - 交互模型处理分布式系统中性能以及设置时间限制的困难，例如对于消息传递。反映了进程交互的方式；

2)   故障模型 - 故障模型试图给出由进程和通信通道呈现出来的故障的一个精确的规格说明。它定义可靠的通信和正确的进程；

3)   安全模型 - 安全模型讨论对于进程和通信通道可能存在的威胁，它引入了安全通道的概念，以低于这些威胁。

 

## 三. 进程间通信
### 1. 线程与进程的区别？

答案来自上次考试知识点总结

答：线程是指进程内的一个执行单元，也是进程内的可调度实体。

与进程的区别 -

(1) 地址空间: 进程内的一个执行单元； 进程至少有一个线程； 它们共享进程的地址空间； 而进程有自己独立的地址空间；

(2) 资源拥有: 进程是资源分配和拥有的单位， 同一个进程内的线程共享进程的资源

(3) 线程是处理器调度的基本单位， 但进程不是。

(4) 二者均可并发执行。

进程和线程都是由操作系统所体会的程序运行的基本单元，系统利用该基本单元实现系统对应用的并发性

进程和线程的区别在于：

简而言之，一个程序至少有一个进程，一个进程至少有一个线程。

线程的划分尺度小于进程，使得多线程程序的并发性高。

另外，进程在执行过程中拥有独立的内存单元，而多个线程共享内存，从而极大地提高了程序的运行效率。

线程在执行过程中与进程还是有区别的。每个独立的线程有一个程序运行的入口、顺序执行序列和程序的出口。但是线程不能够独立执行，必须依存在应用程序中，由应用程序提供多个线程执行控制。

从逻辑角度来看，多线程的意义在于一个应用程序中，有多个执行部分可以同时执行。但操作系统并没有将多个线程看做多个独立的应用，来实现进程的调度和管理以及资源分配。这就是进程和线程的重要区别。

进程是具有一定独立功能的程序关于某个数据集合上的一次运行活动，进程是系统进行资源分配和调度的一个独立单位。

线程是进程的一个实体，是CPU调度和分派的基本单位，它是比进程更小的能独立运行的基本单位。线程自己基本上不拥有系统资源， 只拥有一点在运行中必不可少的资源 (如程序计数器， 一组寄存器和栈)， 但是它可与同属一个进程的其他的线程共享进程所拥有的全部资源。

一个线程可以创建和撤销另一个线程；同一个进程中的多个线程之间可以并发执行。

### 2. 什么是进程、线程的并发控制与调度？什么是多线程并发控制？

答案来自百度

答：进程调度 - 操作系统管理了系统有限资源，当有多个进程（或多个进程发出的请求）要使用这些资源时，因为资源有限性，必须按照一定的原则选择进程（请求）来占用资源，这就是调度。

线程调度 - 指按照特定机制为多个线程分配CPU的使用权。

多线程并发控制 -是指从软件或者硬件上实现多个线程并发执行的技术。具有多线程能力的计算机因有硬件支持而能够在同一时间执行多于一个线程，进而提升整体处理性能。

### 3. 什么是进程间通信？什么是管道通信、消息队列、信号量机制、共享内存？给出定义并查阅资料举例说明。

答案来自百度

答：进程间通信 - 指进程间的信息交换，其所交换的信息量，少则只是一个状态或一个数值，多则可能是成千上万个字节。

管道通信 - 即发送进程以字符流形式将大量数据送入管道，接收进程可从管道接收数据，二者利用管道进行通信。

消息队列 - 是在消息的传输过程中保存消息的容器。

信号量机制 - 即利用PV操作来对信号量进行处理。

共享内存 - 在多处理器的计算机系统中，可以被不同中央处理器（CPU）访问的大容量内存。

### 4. 利用线程通信机制的系统调用，实现操作系统经典的 “生产者-消费者”RPC问题的程序设计，要求写出详细的系统调用。

### 5. 什么是客户/服务器编程？如何进行客户端编程设计？如何进行服务器端编程设计？如何设计服务器与客户的通信？给出基于Socket的客户/服务器，面向UDP和TCP网络编程的详细说明，同时给出一个UNIX/Linux的Client/Sever的程序设计算法流程图。

答案来自百度

答：

什么是客户/服务器编程

从硬件角度看，客户/服务器体系结构是指将某项任务在两台或多台机器之间进行分配，其中客户机（Client）用来运行提供用户接口和前端处理的应用程序，服务器机（Server）提供客户机使用的各种资源和服务。

从软件角度看，客户/服务器体系结构是把某项应用或软件系统按逻辑功能划分为客户软件部分和服务器软件部分。客户软件部分一般负责数据的表示和应用，处理用户界面，用以接收用户的数据处理请求并将之转换为对服务器的请求，要求服务器为其提供数据的存储和检索服务；服务器端软件负责接收客户端软件发来的请求并提供相应服务。
客户/服务器融合了大型机的强大功能和中央控制以及PC机的低成本和较好的处理平衡。客户/服务器为任务的集中/局部分布提供了一种新的方法，这种体系能够使用户对数据完整性、管理和安全性进行集中控制。在缓解网络交通和主机负荷以及满足用户需要方面，客户/服务器体系提供了良好的解决方案。
总之，客户/服务器的工作模式是：客户与服务器之间采用网络协议（如TCP/IP、IPX/SPX）进行连接和通讯，由客户端向服务器发出请求，服务器端响应请求，并进行相应服务。



## 四. 操作系统支持
### 1. 什么叫虚拟机？什么叫虚拟化？举例说明。

答案来自百度

答：虚拟机指通过软件模拟的具有完整硬件系统功能的、运行在一个完全隔离环境中的完整计算机系统。

虚拟化就是将事物从一种形式转变成另一种形式，最常用的虚拟化技术有操作系统中内存的虚拟化，实际运行时用户需要的内存空间可能远远大于物理机器的内存大小，利用内存的虚拟化技术，用户可以将一部分硬盘虚拟化为内存，而这对用户是透明的。又如，可以利用虚拟专用网技术（VPN）在公共网络中虚拟化一条安全，稳定的“隧道”，用户感觉像是使用私有网络一样。

### 2. 什么叫保护？举例说明。

### 3. 什么叫进程调度？什么叫线程调度？多线程并发处理？

答案见三. 3

### 4. 什么叫临界区？什么叫临界资源？如何解释线程同步？

答案来自百度

答：

临界区 - 指的是一个访问共用资源（例如：共用设备或是共用存储器）的程序片段，而这些共用资源又无法同时被多个线程访问的特性。当有线程进入临界区段时，其他线程或是进程必须等待（例如：bounded waiting 等待法），有一些同步的机制必须在临界区段的进入点与离开点实现，以确保这些共用资源是被互斥获得使用。

临界资源 - 一次仅允许一个进程使用的资源称为临界资源。

线程同步 - 在一般情况下，创建一个线程是不能提高程序的执行效率的，所以要创建多个线程。但是多个线程同时运行的时候可能调用线程函数，在多个线程同时对同一个内存地址进行写入，由于CPU时间调度上的问题，写入数据会被多次的覆盖，所以就要使线程同步。线程同步即当有一个线程在对内存进行操作时，其他线程都不可以对这个内存地址进行操作，直到该线程完成操作， 其他线程才能对该内存地址进行操作，而其他线程又处于等待状态，目前实现线程同步的方法有很多，临界区对象就是其中一种。

·        线程同步就是线程排队。同步就是排队。线程同步的目的就是避免线程“同步”执行。

·        只有共享资源的读写访问才需要同步。如果不是共享资源，那么就根本没有同步的必要。 

·        只有“变量”才需要同步访问。如果共享的资源是固定不变的，那么就相当于“常量”，线程同时读取常量也不需要同步。

·        多个线程访问共享资源的代码有可能是同一份代码，也有可能是不同的代码；论是否执行同一份代码，只要这些线程的代码访问同一份可变的共享资源，这些线程之间就需要同步。

### 5. 影响远程调用的哪些因素会影响消息传递？

 

## 五. 对等系统
### 1. 什么叫对等系统？对等系统具有的特点？

答案来自百度

答：对等网络，即对等计算机网络，是一种在对等者（Peer）之间分配任务和工作负载的分布式应用架构，是对等计算模型在应用层形成的一种组网或网络形式。其可以定义为：网络的参与者共享他们所拥有的一部分硬件资源（处理能力、存储能力、网络连接能力、打印机等），这些共享资源通过网络提供服务和内容，能被其它对等节点（Peer）直接访问而无需经过中间实体。在此网络中的参与者既是资源、服务和内容的提供者（Server），又是资源、服务和内容的获取者（Client） 。

特点 -

1)   非中心化：网络中的资源和服务分散在所有节点上，信息的传输和服务的实现都直接在节点之间进行，可以无需中间环节和服务器的介入，避免了可能的瓶颈。P2P的非中心化基本特点，带来了其在可扩展性、健壮性等方面的优势。

2)   可扩展性：在P2P网络中，随着用户的加入，不仅服务的需求增加了，系统整体的资源和服务能力也在同步地扩充，始终能比较容易地满足用户的需要。理论上其可扩展性几乎可以认为是无限的。例如：在传统的通过FTP的文件下载方式中，当下载用户增加之后，下载速度会变得越来越慢，然而P2P网络正好相反，加入的用户越多，P2P网络中提供的资源就越多，下载的速度反而越快。

3)   健壮性：P2P架构天生具有耐攻击、高容错的优点。由于服务是分散在各个节点之间进行的，部分节点或网络遭到破坏对其它部分的影响很小。P2P网络一般在部分节点失效时能够自动调整整体拓扑，保持其它节点的连通性。P2P网络通常都是以自组织的方式建立起来的，并允许节点自由地加入和离开。

4)   高性价比：性能优势是P2P被广泛关注的一个重要原因。随着硬件技术的发展，个人计算机的计算和存储能力以及网络带宽等性能依照摩尔定理高速增长。采用P2P架构可以有效地利用互联网中散布的大量普通结点，将计算任务或存储资料分布到所有节点上。利用其中闲置的计算能力或存储空间，达到高性能计算和海量存储的目的。目前，P2P在这方面的应用多在学术研究方面，一旦技术成熟，能够在工业领域推广，则可以为许多企业节省购买大型服务器的成本。

5)   隐私保护：在P2P网络中，由于信息的传输分散在各节点之间进行而无需经过某个集中环节，用户的隐私信息被窃听和泄漏的可能性大大缩小。此外，目前解决Internet隐私问题主要采用中继转发的技术方法，从而将通信的参与者隐藏在众多的网络实体之中。在传统的一些匿名通信系统中，实现这一机制依赖于某些中继服务器节点。而在P2P中，所有参与者都可以提供中继转发的功能，因而大大提高了匿名通讯的灵活性和可靠性，能够为用户提供更好的隐私保护。

6)   负载均衡：P2P网络环境下由于每个节点既是服务器又是客户机，减少了对传统C/S结构服务器计算能力、存储能力的要求，同时因为资源分布在多个节点，更好的实现了整个网络的负载均衡

### 2. 对等系统中常讨论负载平衡问题？举例说明你的理解。

答案来自百度

答：负载均衡是由多台服务器以对称的方式组成一个服务器集合，每台服务器都

具有等价的地位，都可以单独对外提供服务而无须其他服务器的辅助。通过某

种负载分担技术，将外部发送来的请求均匀分配到对称结构中的某一台服务器

上，而接收到请求的服务器独立地回应客户的请求。

均衡负载能够平均分配客户请求到服务器列阵，籍此提供快速获取重要数据，

解决大量并发访问服务问题。这种群集技术可以用最少的投资获得接近于大型

主机的性能。

负载均衡是分布式系统架构设计中必须考虑的因素之一，它通常是指，将请求/数据【均匀】分摊到多个操作单元上执行，负载均衡的关键在于【均匀】。

(1) 【客户端层】到【反向代理层】的负载均衡，是通过 “DNS轮询” 实现的

(2) 【反向代理层】到【站点层】的负载均衡，是通过 “nginx” 实现的

(3) 【站点层】到【服务层】的负载均衡，是通过 “服务连接池” 实现的

(4) 【数据层】的负载均衡，要考虑 “数据的均衡” 与 “请求的均衡” 两个点，常见的方式有 “按照范围水平切分” 与 “hash水平切分”

### 3. 分析结构化对等系统与非结构化对等系统的优势与不足。

答案来自google

答：

结构化对等系统 -

点对点之间互有连结资讯，彼此形成特定规则拓扑结构。

需要请求某资源时，依该拓扑结构规则寻找，若存在则一定找得到。

·        优点 - 高效，查询结果有保障，资源可有效被检索

·        缺点 - 发现资源成本高，静态和动态负载不平衡，面对高速大量的对等体流入流出不可靠

非结构化对等系统 -

点对点之间互有连结资讯，彼此形成无规则网状拓扑结构。

需要请求某资源点时，以广播方式寻找，通常会设TTL，即使存在也不一定找得到。

·        优点 - 易于构建，允许对不同的区域覆盖进行本地化优化，能够面对高速大量的对等体流入流出

·        缺点 - 缺乏结构，查询消耗大，不能保证查询结果

### 4. 对等系统中有效的文件搜索策略有哪些？

答案来自google

答：

1)   文件分割策略

为了加快资源文件的分发，大多数对等系统将文件分为固定大小的片，除了最后一片，使得P2P客户端能够同时从多个对等体下载数据。在这里，“片”是共享数据的最小单位，这意味着一个对等体必须至少有一个提供给其他对等体的上传服务。

不同的P2P系统具有不同的术语表示“片”，并且还设置不同的片段大小。为了有效的传输调度，每个片段进一步分为多个子片，“子片”是在对等体之间进行数据传输的最小单元。换句话说，当一个片段可以从多个远程对等体获得时，本地对等体可以决定哪个远程对等体下载文件。一旦决定，它必须从同一个远程对等体下载该片的所有子片。

2)   片选选择策略

当本地对等体需要多个文件，并且这些片段可从其对等体集中的远程对等体获得时，片段选择策略给出了首先确定应该请求哪个片段的问题的解决方案。

3)   对等选择策略

在本地对等体Pi发送一个消息给远程对等体Pj后，Pj可以决定是否向Pi提供上传服务。 这种对等体对问题作出决策的策略称为对等选择策略。

 

## 六. 分布式文件系统
### 1. 分布式文件系统的特点与需求是什么？

答案来自百度

答：

特点 - 可扩展性，高可用性，协议和接口多样性，弹性存储

### 2. Sun网络文件系统（NFS）的自动安装器是如何改进NFS的性能和可伸缩性的？

 

## 七. 分布式系统前沿
### 1. 什么是大数据？什么是云平台？举例说明它们的关系。

答案来自百度

答：

大数据 - 研究机构Gartner给出了这样的定义。“大数据”是需要新处理模式才能具有更强的决策力、洞察发现力和流程优化能力来适应海量、高增长率和多样化的信息资产。

麦肯锡全球研究所给出的定义是：一种规模大到在获取、存储、管理、分析方面大大超出了传统数据库软件工具能力范围的数据集合，具有海量的数据规模、快速的数据流转、多样的数据类型和价值密度低四大特征。

云平台 - 提供基于“云”的服务，供开发者创建应用时采用。可以划分为3类：以数据存储为主的存储型云平台，以数据处理为主的计算型云平台以及计算和数据存储处理兼顾的综合云计算平台。

关系 - 从技术上看，大数据与云计算的关系就像一枚硬币的正反面一样密不可分。大数据必然无法用单台的计算机进行处理，必须采用分布式架构。它的特色在于对海量数据进行分布式数据挖掘。但它必须依托云计算的分布式处理、分布式数据库和云存储、虚拟化技术。

随着云时代的来临，大数据也吸引了越来越多的关注。分析师团队认为，大数据通常用来形容一个公司创造的大量非结构化数据和半结构化数据，这些数据在下载到关系型数据库用于分析时会花费过多时间和金钱。大数据分析常和云计算联系到一起，因为实时的大型数据集分析需要像MapReduce一样的框架来向数十、数百或甚至数千的电脑分配工作。

大数据需要特殊的技术，以有效地处理大量的容忍经过时间内的数据。适用于大数据的技术，包括大规模并行处理（MPP）数据库、数据挖掘、分布式文件系统、分布式数据库、云计算平台、互联网和可扩展的存储系统。

### 2. 什么是网格？网格平台与云平台的联系与区别？

答案来自课件

答：

网格是信息社会的网络基础设施，它把整个因特网整合成一台巨大的超级虚拟计算机，实现互联网上所有资源的互联互通，完成计算资源、存储资源、通信资源、软件资源、信息资源、知识资源等智能共享的一种新兴的技术。

 

联系与区别 - 云计算和网格彼此相关，但又有不同。网格计算强调资源共享，任何人都可以做为请求者使用其它节点的资源，任何人都需要贡献一定资源给其他节点。网

格计算强调将工作量转移到远程的可用计算资源上。云计算强调专有，任何人都可以获取自己的专有资源，并且这些资源是由少数团体提供的，使用者不需要贡献自己的资源。在云计算中，计算资源被转换形式去适应工作负载，它支持网格类型应用，也支持非网格环境，比如运行传统或Web2.0应用的三层网络架构。网格计算侧重并行的计算集中性需求，并且难以自动扩展。云计算侧重事务性应用，大量的单独的请求，可以实现自动或半自动的扩展。