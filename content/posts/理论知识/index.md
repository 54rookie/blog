+++
title = '理论知识'
date = 2024-05-05T11:16:56+08:00
draft = false
tags = ['密码学']
+++

<a name="U4Tqw"></a>

### 密码学小常识：
> **什么是IACR：**
> - 密码学中最著名的学术会议当属国际密码学协会（IACR，International Association of Cryptological Research）所主办的三个⼤会了：Crypto、Eurocrypt、Asiacrypt，即美密会、欧密会、 亚密会，其中欧密会和美密会的⽔平最⾼（亚密会的资历最浅，虽然近⼏年上升很快，但要完全赶上还需要⼀定的时间）。密码学中最重要的⽂章⼀般都会在这三个会议中发布。
> 
> **什么是DBLP：**
> - **定义：** DBLP（DataBase systems and Logic Programming） 是计算机领域内对研究的成果以作者为核心的一个计算机类英文文献的集成数据库系统。
> - **简介：** DBLP按年代列出了作者的科研成果。包括国际期刊和会议等公开发表的论文。DBLP没有提供对中文文献的收录和检索功能，国内的权威期刊及重要会议的论文缺乏一个类似的集成检索系统。DBLP所收录的期刊和会议论文质量较高，DBLP的文献更新速度很快，很好地反应了国外学术研究的前沿方向。
> - **特征：** DBLP在学术界有很好的声誉，给人们带来了极大的便利，其权威性也得到了研究界的高度认可。但DBLP没有提供对中文文献的收录和检索功能，国内的权威期刊及重要会议的论文缺乏一个类似的集成检索系统。DBLP项目是德国特里尔大学的Michael Ley负责开发和维护。它提供计算机领域科学文献的搜索服务，但只储存这些文献的相关元数据，如标题，作者，发表日期等。截至2009年7月已经有超过1,200,000文献。和一般流行的情况不同，DBLP并没有使用数据库而是使用XML存储元数据。
> - **dblp地址：** [https://dblp.org/](https://link.zhihu.com/?target=https%3A//dblp.org/)
> 
> **参考文献：**
>    - IACR：[https://blog.csdn.net/A33280000f/article/details/117929248](https://blog.csdn.net/A33280000f/article/details/117929248)
>    - DBLP：[https://zhuanlan.zhihu.com/p/595538578](https://zhuanlan.zhihu.com/p/595538578)

<a name="cpPzU"></a>

#### CCF-A的会议和期刊（网络与信息安全）：
**三大顶会:**

| _EUROCRYPT  _ | International Conference on the Theory and Applications of Cryptographic Techniques  |
| --- | --- |
| _CRYPTO_ | International Cryptology Conference. |
| _ASIACRYPT_ | Annual International Conference on the Theory and Application of Cryptology and Information Security. |

**会议:**

| _CCS_ | ACM Conference on Computer and Communications Security   |
| --- | --- |
| _EUROCRYPT  _ | International Conference on the Theory and Applications of Cryptographic Techniques  |
| _CRYPTO_ | International Cryptology Conference. |
| _S&P_ | IEEE Symposium on Security and Privacy   |
| _USENIX Security  _ | USENIX Security Symposium   |

**期刊:**

| _ | IEEE Transactions on Dependable and Secure Computing   |
| --- | --- |
| _ | IEEE Transactions on Information Forensics and Security   |
| <br /> | Journal of Cryptology |

<a name="XXSbf"></a>

#### 论文中常用的符号
> **i.e.  ：**
> - 是**id est**（“that is” , "in other words"。进一步解释用，意为：也就是，换句话说）的缩写。目的是用来进一步解释前面所说的观点（不像后文的e.g.那样引入实例来形象化），意思是“那就是说，换句话说”。
> 
**e.g.  ：**
> - 是**exempli gratia**（"for example; for instance;such as"。举例用，意为：例如）的缩写，其目的用若干例子来让前面说法更具体，更易感知。
> 
**etc.  ：**
> - 是**et cetera**(“and so forth; and the others; and other things; and so on"。举例用，意为：等等)的缩写。它放在列表的最后，表示前面的例子还没列举完，最后加个词“等等”。
> 
**viz.  ：**
> - 是**videlicet**（ "namely", "towit", "precisely", "that is to say"。进一步解释用，意为：即）的缩写，与e.g.不同，viz位于同位列表之前，要把它前面单词所包含的项目全部列出。
> 
**et al.  ：**
> - 是**et alia**（"and others; and co-workers"。在引用文献作者时用，意为:等其他人）的缩写。它几乎都是在列文献作者时使用，即把主要作者列出后，其它作者全放在et al. 里面。
> 
**w.r.t.  ：**
> - 是**with respect to**（"with respect to"。在引用文献作者时用，意为:关于,谈到）的缩写。是 关于；谈及，谈到的意思。
> 
> 参考文献：
> - [https://zhuanlan.zhihu.com/p/63640148](https://zhuanlan.zhihu.com/p/63640148)

<a name="koNZT"></a>

#### 密码学常用名词介绍
> ![](https://image.54rookie.com/blog/171568576920240514192249.png)
> **PKI系统的介绍：**
> - 参考文献：[https://www.jianshu.com/p/c65fa3af1c01](https://www.jianshu.com/p/c65fa3af1c01)
> 
**半诚实的模型：**
> - 半诚实的参与方指的是**遵循了协议的执行，但保存了协议的中间计算状态**的参与方。实际上，半诚实的参与方需要做的是：保存内部的掷硬币过程（产生随机数的过程）和所有从其他参与方接收到的消息。特别的，一个半诚实的参与方会选择随机数和根据预定的程序进行操作，即根据预定的程序公平的产生随机数和执行输入与输出。值得注意的是，一个半诚实参与方相当于是零知识中的诚实验证者。
> - 既然积极的恶意敌手更有攻击能力，那么我们到底为什么还要考虑攻击能力更弱的半诚实模型？即半诚实的敌手模型的必要性在哪里？其实在一般情况下，发动主动攻击要比监听整个计算过程在攻击复杂的多，原因是，对于一个运行在计算机上程序，主动的攻击需要用一些非常复杂的程序去攻击他，但是对于单纯的获取计算过程中的数据而言，这是比较容易的，所以半诚实敌手模型在实际的生产生活中更加的普遍存在，就是单独考虑半诚实敌手的必要性。
> - 参考文献：
>    - [https://blog.csdn.net/zmrlinux/article/details/103068525](https://blog.csdn.net/zmrlinux/article/details/103068525)
> 
<br />

> **加盐哈希：**
> - 在密码学中，是指通过在密码任意固定位置插入特定的字符串，让散列后的结果和使用原始密码的散列结果不相符，这种过程称之为“加盐”。
> - 加盐哈希早用户名密码中应用非常广泛。
> - 参考文献：
>    - [https://zhuanlan.zhihu.com/p/22860282?from_voters_page=true](https://zhuanlan.zhihu.com/p/22860282?from_voters_page=true)

<a name="baRbQ"></a>

#### 数字签名的分类
> ![](https://image.54rookie.com/blog/171568579520240514192315.png)
> 参考文献:
> - [https://blog.csdn.net/weixin_43851783/article/details/110391153](https://blog.csdn.net/weixin_43851783/article/details/110391153)

<a name="KMBYH"></a>

### 双线性映射
<a name="vYz7T"></a>

#### 双线性映射的定义
> **一般的双线性映射定义如下：**
> ![](https://image.54rookie.com/blog/171568582520240514192345.png)
> - 注意：
>    - 现在的密码学相关论文中，习惯将G1,G2设置为乘法循环群。但是，基于椭圆曲线的双线性群构造中，G1,G2是加法群。在大约2005年以前的论文中，G1，G2是加法循环群。
>    - 双线性映射可以通过有限域上的超椭圆曲线上的Tate对或Weil对来构造。
> 
**现代习惯性的双线性映射定义：**
> ![](https://image.54rookie.com/blog/171568603820240514192718.png)

<a name="TxGPv"></a>

#### 双线性映射的分类
> 根据$\mathbb{G}_1$与$\mathbb{G}_2$是否为同一个群，可以划分为 对称式与非对称式。 最重要的还是双线性这条性质，几乎所有的构造都是依赖于此。
> - $G_1×G_1→G_T$：对称式双线性映射，即$G_1=G_2$。	【"Type-1型配对"：安全性最低】
> - $G_1×G_2→G_T$：存在一个$G_1到G_2$的同态映射。     	【"Type-2型配对"：安全性适中】
> - $G_1×G_2→G_T$：$G_1$和$G_2$之间不存在同态关系。  	【"Type-3型配对"：安全性较高】
> 
**注意：**
> - Type-3配对在带宽和计算效率方面提供了最有效的实现选择。
> - 非对称的双线性映射由于两个群$G_1,G_2$的大小可以取为不一样的，这样就会导致在两个群上计算点乘运算的计算开销不同。合理利用这一点，可以实现一些特殊的功能。【参考SM9算法】
> 
**假设加法循环群**$G_1$**的生成元为**$P$**，则双线性映射具有以下性质：**
> - $e(A+B,C)=e(A,C)*e(B,C)$
>    - 由于$A$和$B$是群$G_1$上的两个元素，故存在a,b满足 $A=aP，B=bP$；则
>    - $\begin{align}
&\ \ e(A+B,C)\\
&=e((a+b)P,C)\\
&=e(P,C)^{a+b}\\
&=e(P,C)^a*e(P,C)^b\\
&=e(aP,C)*e(bP,C)\\
&=e(A,C)*e(B,C)\\
\end{align}$
> - $e(A,B+C)=e(A,B)*e(A,C)$
>    - 证明同上
> - $e(xA,B)=e(A,xB)=e(A,B)^x$
> - $e(A+B,C+D)=e(A,C)*e(A,D)*e(B,C)*e(A,D)$
> - $e(A,B)^x*e(A,B)^y=e(A,B)^{x+y}$
> - $e(A,B)*e(C,D)=e(A+C,B+D)*e(A,D)^{-1}*e(B,C)^{-1}$
> 
补充：
> - 用上述的证明方法可以证明，在非对称的双线性映射中，上述性质也是成立的。即：
>    - $e(A+B,C)=e(A,C)*e(B,C)$
>    - $e(A,B+C)=e(A,B)*e(A,C)$
>    - $e(A^x,B)=e(A,B^x)=e(A,B)^x$
>    - $e(A+B,C+D)=e(A,C)*e(A,D)*e(B,C)*e(A,D)$
>    - $e(A,B)^x*e(A,B)^y=e(A,B)^{x+y}$
>    - $e(A,B)*e(C,D)=e(A+C,B+D)*e(A,D)^{-1}*e(B,C)^{-1}$
> - 乘法循环群下的性质为：
>    - $e(AB,C)=e(A,C)*e(B,C)$
>    - $e(A,BC)=e(A,B)*e(A,C)$
>    - $e(A^x,B)=e(A,B^x)=e(A,B)^x$
>    - $e(AB,CD)=e(A,C)*e(A,D)*e(B,C)*e(A,D)$
>    - $e(A,B)^x*e(A,B)^y=e(A,B)^{x+y}$
>    - $e(A,B)*e(C,D)=e(AC,BD)*e(A,D)^{-1}*e(B,C)^{-1}$
> - 注意：
>    - $e(A,C)^x*e(B,C)^y≠e(AB,C)^{x+y}$

<a name="PdNQz"></a>

### 零知识证明 与 Schnoor 签名：
<a name="osou3"></a>

#### 零知识签名的概念
> **定义：**
> - 零知识证明的定义为：证明者（prover）能够在不向验证者（verifier）提供任何有用的信息的情况下，使验证者（verifier）相信某个论断是正确的。
> 
**性质：**
> 1. 完备性（Completeness）：只要证明者拥有相应的知识，那么就能通过验证者的验证，即证明者有足够大的概率使验证者确信。；
> 2. 可靠性（Soundness）：如果证明者没有相应的知识，则无法通过验证者的验证，即证明者欺骗验证者的概率可以忽略。
> 3. 零知识性（Zero-Knowledge）：证明者在交互过程中仅向验证者透露是否拥有相应知识的陈述，不会泄露任何关于知识的额外信息。
> 
**举例说明：**
> - Alice是色盲，Bob不是色盲，在Bob手上有两个大小，形状完全一样的球，但这两个球的颜色不一样，一个球是蓝色的，另一个球是红色的，由于Alice是色盲，所以Alice无法分辨这两个球是否是一样的，Bob需要向Alice证明这两个球是不一样的。在这里，Alice被称为验证者，他需要验证Bob的陈述正确与否，Bob被称为证明者，他需要证明自己的陈述（存在两个颜色不一样的球），Bob需要在Alice不能获得两个球的颜色的情况下，向Alice证明这两个球的颜色是不一样的这个事实，这与零知识证明的定义是相符合的。
> - Alice当Bob的面拿起两个球，左手拿蓝球，右手拿红球，然后将双手放到背后，这样Bob就看不到Alice手上的球了，Alice在背后随机交换左右手上的球，交换完成后Alice将手伸出，并询问Bob两个球是否交换过位置，如果Bob能看到球上的颜色，那么每次Alice换过球的位置后，Bob都能正确回答出Alice的问题。
> - 第一次，Alice偷偷交换了手中球的位置，然后Alice问Bob是否交换了球的位置，如果Bob回答Yes，那么Alice有50%的概率相信Bob是可以区分这两个球的颜色，因为Bob有1/2的概率蒙对，所以Alice可以在进行一次测试。如果Bob回答No，那么Alice可以肯定Bob不能区分两个球的颜色。
> - 第二次，Alice没有交换手中球的位置，然后Alice问Bob是否交换了球的位置。如果Bob回答No，那么Alice有75%的概率相信Bob是可以区分两个球的颜色。
> - 第一次迭代后，Alice可以说Bob陈述的断言为真的概率为50％。如果Bob第二次回答正确，那么Alice可以说Bob陈述为真的概率达75％。在第三次迭代后，它将是87.5％。如果连续n次Bob都通过了检查，则Alice有1-(1/2)^n 的概率可以认为 Bob 说的是真的，这两个球的确是有红蓝两种颜色。
> - 零知识证明是一种基于概率的验证方式，验证者（verifier）基于一定的随机性向证明者（prover)提出问题，如果证明者都能给出正确回答，则说明证明者大概率拥有他所声称的“知识”。零知识证明并不是数学意义上的证明，因为它存在小概率的误差，欺骗的证明者有可能通过虚假的陈诉骗过验证者。换句话说，零知识证明是概率证明而不是确定性证明，但是也存在技术能将误差降低到可以忽略的值。
> 
> **知识签名：**
> 签名者利用数学知识和公共信息，非交互和不泄露某个秘密的情况下，向别人证明他知道这个秘密。
> - 常见的知识签名有三种：
>    - 离散对数的知识签名
>    - 双离散对数的知识签名
>    - 离散对数e次方根的知识签名
> 

**离散对数的知识签名：(零知识证明)**
> 符号表示为：<br>
>         ![](https://image.54rookie.com/blog/171568608020240514192800.png)
> - 离散对数的知识签名是针对这样一个问题：$y = g^x mod(n)$;  x 是私钥，y 是公钥，g 和 n 都是公开的系统参数，m是消息，现在需要让别别人证明自己拥有私钥 x，并且不泄露 x 的信息。
> - 这里只需要证明者给出一个（c，s）对，符合以下的等式要求即可：
>    - $c = H( m||y||g||(g^s) (y^c) )$
> 
具体的操作过程如下：
>       1. 选择一个随机数           $r$
>       2. 计算c：根据公式         $c=H(m||y||g||g^r)$
>       3. 计算s：根据公式         $s = r - c * x$
>       4. (c,s)即为知识签名。
>
> 解释说明 <br>
    ![](https://image.54rookie.com/blog/171568612420240514192844.png)
>    如果知道密钥x，执行通过上面操作过程中的四个步骤就可以轻松计算出(c,s)对的值，
>    如果不知道密钥x，而想算出(c,s)，只能通过3式计算，这在计算上是不可行的。
>    所以，如果能给出一个满足条件的（c,s）对，就能说明其拥有私钥x。

> **双离散对数的知识签名**
> ![](https://image.54rookie.com/blog/171568614220240514192902.png)
> - 详细见参考文献【1】
> 
离散对数e次方根的知识签名
> ![](https://image.54rookie.com/blog/171568615820240514192918.png)
> - 见参考文献【1】
> 
> **参考文章：**
> - 【1】[知识签名(signature of knowledge)_zhang-hui的博客-CSDN博客](https://blog.csdn.net/zhang_hui_cs/article/details/8964830)
> - 【2】[零知识证明介绍](https://zhuanlan.zhihu.com/p/152065162)

<a name="eUC8R"></a>

#### Schnorr协议
> **简介：**
> - Schnorr机制由德国数学家和密码学家Claus-Peter Schnorr在1990年提出，是一种基于离散对数难题的知识证明机制。
> - Schnorr本质上是一种零知识的技术，即Prover声称知道一个密钥x的值，通过使用Schnorr加密技术，可以在不揭露x的值情况下向Verifier证明对x的知情权。即可用于证明你有一个私钥。
> - Schnorr中涉及到的技术有哈希函数的性质、椭圆曲线的离线对数难题。椭圆曲线的离线对数难题：已知椭圆曲线E和点G，随机选择一个整数d，容易计算Q=d*G，但是给定的Q和G计算d就非常困难**。**
> - Schnorr协议分为交互式的和非交互式的。
> 
**<交互式的Schnorr协议>具体方案如图：**
> ![](https://image.54rookie.com/blog/171568620820240514193008.png)
> **解释上图如下：**
>    - Alice：随机地选择一个标量r，然后计算出R=r*G（椭圆曲线上的一点），将R发送给Bob；
>    - Bob：回应一个随机标量 c ；
>    - Alice：通过计算$z=r+c*sk$，将标量 z 回应给Bob；
>    - Bob：将s转换为椭圆曲线上的点，即z*G，然后验证$z*G=c*PK+R$。
> 
**说明：**
>    - 由于z=r+c*sk，等式两边同时添加相同的生成元可得：z*G=c*PK+R。即可验证Alice确实拥有私钥sk，但是验证者Bob并不能得到私钥sk的值，因此这个过程是零知识的，且是交互式的。**此协议也叫做Sigma protocol。**
> 
**安全性分析**
>    1. 由于椭圆曲线上的离散对数问题，知道R和G的情况下通过R=r*G解出r是不可能的，所以保证了r的私密性。但是，这也是在证明者和验证者在私有安全通道中执行的。这是由于此协议存在交互过程，此方案只对参与交互的验证者有效，参与交互的双方如果串通了随机数c，那么不参与交互的验证者也无法判断出 证明者是否真的拥有私钥。因此，是无法公开验证的。
>    2. 不妨来个数学理论推导：在公开验证的条件下，两个验证者分别提供两个不同的随机值c1和c2，并要求证明者计算z1 = r + c1*sk，z2 = r + c2*sk，即可计算出sk =（z1-z2）/（c1-c2）。因此，这个过程便无法公开验证。
>    3. 进一步分析，为什么需要验证者回复一个随机标量c呢？防止Alice造假！如果Bob不回复一个c，就变成如下一次性交互。由于椭圆曲线上的离散对数问题，知道PK和G的情况下通过PK = a * G 计算a是不可能的，所以保证了 a 的私密性。但是这种方案是存在问题的，a 和 r 都是Alice自己生成的，她知道Bob会用PK和 R 相加然后再与z * G进行比较。所以不知道a的攻击者可以进行以下构造：
>             - R = r * G - PK
>             - z = r。
>    - 这样Bob的验证过程就变成：z * G = r * G = PK + R。这是永远成立的，这就导致不知道私钥的人也能通过证明。
>    4. 加入随机数 c 之后可以完美的避免这个问题。因为如果敌手A想要在不知道 sk 的情况下以同样的方式欺骗Alice，需要构造：
>             - R = r * G - c * PK
>             - z = r。
>    - 由于A要首先把 R 发给 Bob，然后Bob才将 c 发给 A，而 R 需要 c 才能计算出来，故敌手不能成功。
> 
<br />

**非交互式的Schnorr协议具体方案：**

> - 将交互式的Schnorr协议改造为非交互式的非常简单。根据Fiat-Shamir启发式方法，改造如下：
>    - Alice：随机选择 r，计算$R=r*G$                              （椭圆曲线上的一点）；
>    - Alice：计算                    $c = H(R,PK)$；
>    - Alice：通过计算             $z=r+c*sk$，                      将$(R,c,z)$给Bob；
>    - Bob： Bob验证              $z*G = c*PK+R$。
> - 安全性分析：
>    1. 这里同理，敌手需要构造以下信息才能欺骗Bob
>             - $R = r * G - c * PK$
>             - $c = H(R,PK)$
>             - $z = r$。
>    - 由于计算 R 需要用到 c ，计算 c 需要用到 R ；故导致敌手无法完美构造满足条件的上式：
>       - 如果先构造R，需要先知道 c，由于 c 的计算需要用到 R ，且哈希函数是单向的，因此不可行。
>       - 先构造 c 同理.

Sigma协议和Fiat-Shamir启发式：
> - [https://www.yuque.com/xiaozeng-lhkfj/guc7a3/egsn1gzebrmkfcz1#fuMTK](https://www.yuque.com/xiaozeng-lhkfj/guc7a3/egsn1gzebrmkfcz1#fuMTK)【笔记】

**参考文献：**
> - [http://blockchain.whu.edu.cn/uploads/soft/201105/1_1954088811.pdf](http://blockchain.whu.edu.cn/uploads/soft/201105/1_1954088811.pdf)

<a name="aBIxk"></a>

### ECDSA签名
<a name="lzBEd"></a>

#### ECDSA简介：
> - 椭圆曲线数字签名算法（ECDSA）是使用椭圆曲线密码（ECC）对数字签名算法（DSA）的模拟。ECDSA于1999年成为ANSI标准，并于2000年成为IEEE和NIST标准。它在1998年既已为ISO所接受，并且包含它的其他一些标准亦在ISO的考虑之中。与普通的离散对数问题（discrete logarithm problem DLP）和大数分解问题（integer factorization problem IFP）不同，椭圆曲线离散对数问题（elliptic curve discrete logarithm problem ECDLP）没有亚指数时间的解决方法。因此椭圆曲线密码的单位比特强度要高于其他公钥体制。

<a name="p41fU"></a>

#### ECDSA具体方案：
> - **参数生成：**
>    - 选择有限域$F_p$上的一个椭圆曲线$E(a,b)：y^2=x^3+ax+b \ (mod \ p)$且对于$E(a,b)$来说，它满足$4a^3+27b^2≠0\ (mod \ p)$
>    - 选择$E(a,b)$上的一个点$P$作为基点，其中$P$的阶为$n$
>    - 选择随机数$sk$作为私钥(其中k<n)，计算公钥$P_{pub}=skP$
>    - 则最终的参数为$Params=\{E(a,b),P,P_{pub}\}$
> - **签名（假设要对消息m进行签名）：**
>    - 选择随机数$r$，计算$rP=（R,y）$
>    - 计算$h=H(m)$
>    - 计算$S = r^{-1}(h + skR)\ (mod\ n)$       （这里，$k^{-1}$是k在模n下的乘法逆元）
>    - 则最终签名为$σ=（R,S）$。（注意，如果r,s中任意一个为零，重新选择随机数计算签名）
> - **验签（收到了签名**$\{m,σ\}=\{m,R,S\}$**）**
>    - 计算$h = H(m)$
>    - 计算$S^{-1}hP+S^{-1}RP_{pub}=(x_1,y_1)$
>    - 计算$r_1≡x_1\ (mod\ p)$
>    - 比较$r_1=R$是否成立，如果成立，验签成功。否则，验签失败

<a name="UMjrV"></a>

### BLS短签名
<a name="MTA48"></a>

#### BLS签名简介
> BLS签名算法是斯坦福大学计算机系三人提出：Dan **B**oneh，Ben **L**ynn以及Hovav **S**hacham。BLS的主要思想是待签名的消息散列到一个椭圆曲线上的一个点，并利用双线性映射e函数的交换性质，在不泄露私钥的情况下，验证签名。BLS的算法在签名合并，多签，m/n多签有丰富的应用。

<a name="XFVPW"></a>

#### BLS具体方案
> **预备知识：**
> - **新型散列函数（Hash函数）：**
>    - 一般的hash（散列）函数的结果都是数值。在BLS签名算法中需要用的散列函数的结果是椭圆曲线上的一个点。也就是说，散列结果对应椭圆曲线上的一个点。以 ECC 和 SHA-256 为例。比特币用的椭圆曲线是secp256k1，也就是该曲线由2²⁵⁶个点组成。SHA-256普通Hash函数的结果也是256位。如果用Hash函数的数值结果，对应于椭圆曲线上点横坐标x，有两个点y和-y都在椭圆曲线y²=x³+ax+b上。说明SHA-256的结果，有50%的概率，要么找到两个点，要么找不到点。
>    - 为了解决这个问题，需要用到直接从消息计算到一个点的哈希，给定消息m，计算H(m)，使得H(m)∈ G，其中G是椭圆曲线点构成的群。Dan Boneh在文章中给出了一个具体的做法，例如采用的仍然是普通哈希，把结果（先看成一个数）当作是一个点的x坐标，然后带入椭圆曲线公式计算相应的y坐标。如果不存在，则把第一步的x坐标作为输入继续算哈希得到另一个x坐标，计算相应y坐标，直到求出y为止。根据二次剩余理论，平均算2次即可得出一个对应的y。这样确保首先是一个确定性的算法，可以在有限步骤内(数学期望为2次)完成计算；其次，如果采用的哈希函数本身是安全的，则整体的计算过程也是安全的。这样整个计算称为**Map-to-Point哈希**。
> - **双线性映射：**
>    - 本方案验证阶段用到了双线性映射，双线性映射的内容参考本文介绍___【在本文的上面】
> 
<br />

> **具体方案【概述】：**
> - 假设Alice的私钥为$pk$，公钥为$P = pk×G$，想对消息$m$签名，则：
> - 签名方案：
>    - 计算$S = pk×H(m)$作为签名
> - 验签方法：
>    - 判断$e(P, H(m)) = e(G, S)$是否成立，成立则验签成功。
> 
> 
> **具体方案【展开来说】：**
> 给定私钥$pk$，公钥$P = pk×G$，以及待签名的消息为$m$。签名的计算公式如下：
> - $S = pk×H(m)$   ； 其中$H(m)$是第一节中讲述的新型散列函数。
> 
上述过程如下图所示：
> ![](https://image.54rookie.com//blog/171568527120240514191431.png)
> 
> 验证过程涉及e函数，计算如下的等式是否成立：
> - $e(P, H(m)) = e(G, S)$
> 
证明过程如下：
> - $\begin{align}
& \ e(P, H(m)) \\
& = e(pk×G, H(m)) \\
& = e(G, pk×H(m)) \\
& = e(G, S)
\end{align}$
> 
证明过程示意如下：
> ![](https://image.54rookie.com/blog/171568637320240514193253.png)

<a name="WsHGe"></a>

#### BLS签名的应用【聚合签名】
> 签名合并：
> - BLS签名算法有很多应用，其中一个是签名的合并。想象一下，一个区块中有n个交易，每个交易都有独立的公钥$P_i$，签名$S_i$，以及交易内容$m_i$。如果需要知道区块中的交易的签名是否都正确，传统的方式，区块中的交易需要一个个的验证签名。
> - 然而，区块中需要存储所有交易的签名。用BLS算法进行签名的合并只需要存储一个33个字节的BLS签名。
>    - 合并签名为$S = S_1+S_2+…+S_n$
>    - 其中          $S_i = P_i×H(m_i)$ ； $i={1,2,...,n}$
> 
> - 验证过程是：
>    - $e(G, S) = e(P_1, H(m_1))⋅e(P_2, H(m_2))⋅…⋅e(P_{n}, H(m_{n}))$
> 
证明过程如下：

>    - $\begin{align}
&e(G, S) = e(G, S_1+S_2+…+S_{n}) \\
&= e(G, S_1)⋅e(G, S_2)⋅…⋅e(G, S_{n}) \\
&= e(G, pk_1×H(m_1))⋅…⋅e(G, pk_{n}×H(m_{n})) \\
&= e(pk_1×G, H(m_1))⋅…⋅e(pk_{n}×G, H(m_{n})) \\
&= e(P_1, H(m1))⋅e(P_2, H(m_2))⋅…⋅e(P_{n}, H(m_{n}))
\end{align}$
> 
从证明过程可见，主要是用了e函数的交换规则。BLS算法在多签以及m/n签名还有更多应用，这里不详细展开。

<a name="i3g3h"></a>

### 国密SM9算法
<a name="L5G5n"></a>

#### SM9简介
> 1. SM9 是和 SM2/RSA 类似的非对称加密算法。在传统的非对称加密算法中，密钥对的生成存在不少的限制如：RSA2048_SHA256和适用这个加密算法的密钥对是有适配关系的，特定的非对称加密算法是要用专门的手段生成密钥对。
> 2. 传统的非对称加密算法在政务或商业用途中需要一种叫CA（Certification Authority）的机构来做身份认证、颁发数字证书并管理这些数字证书。你以后的签名（就是用你的私钥来加密电子数据，比如签电子合同）需要用到数字证书以及密钥。
> 3. 在SM9算法中，用户将自己的公钥给KGC（Key Generating Centre），KGC为用户生成一个该公钥对应的私钥。
> 4. SM9算法特别的地方是：用易于记忆的用户特征字符串（如：邮箱地址、身份证号码等）来作为公钥，目的就是为了降低公钥系统中密钥和证书管理的复杂性。所以SM9算法不需要申请数字证书，如果国家统一管理私钥（相当于充当KGC），CA机构有可能要被干掉了。
> 5. SM是“商密”的拼音。SM9的家族里还有SM1/2/3/4等对称、非对称、摘要算法。是我国“自主知识产权”的算法。虽然只是ECC的一种实现，但是还是有很多创新的。RSA的应用太广泛啦，生态方面SM系列还有待努力。这个SM9用户体验好，应该是很好的助推工具。
> 6. 因为动了CA的蛋糕，广泛运用还需要一定时间。

<a name="w3Syx"></a>

#### SM9签名算法

> **预备知识：**

> - **H(A，q)**：表示一种哈希函数，对A进行哈希，得到一个小于 q 的哈希值。<br>
> - **KGC**：密钥生成中心，用户将自己的身份作为公钥传输给KGC，KGC为用户生成这个公钥对应的私钥。<br>
> - **双线性映射**: 本文使用$G_1×G_2→G_T$的双线性映射，其中$G_2$上的点的大小是$G_1$上的2倍。$G_1$和$G_2$是加法循环群，$G_T$是乘法循环群。<br>
> 
> **详细方案**
> - **密钥生成：**
>    - 在这个阶段，用户将自己的标识符 $ID$作为公钥发给KGC，KGC为其生成对应的私钥$D_{ID}$。除此之外，用户还会生成整个系统的公私钥对$(ks,P_{pub_s})$，并将公钥$P_{pub_s}$公开。
>    - 具体过程如下：

![](https://image.54rookie.com/blog/171568629020240514193130.png)

> - **SM9签名**
>    - 在这个阶段，Alice使用自己的私钥$D_{ID}$和系统公钥$P_{pub_s}$对消息进行签名,得到签名$(h,S)$
>    - 具体过程如下: <br>

![](https://image.54rookie.com/blog/171568631020240514193150.png)

> - **SM9验签:**
>    - 在这个阶段,任何人都可以使用Alice的公钥$ID$对他的签名$(h,S)$进行验签.
>    - 具体过程如下: <br>

![](https://image.54rookie.com/blog/171568641220240514193331.png)

>  **整个流程如下:**
> 

![](https://image.54rookie.com/blog/171568642920240514193349.png)

> 
> **参考资料：**
> - [国家标准全文阅读|标准检索](https://openstd.samr.gov.cn/bzgk/gb/std_list?p.p1=0&p.p90=circulation_date&p.p91=desc&p.p2=SM9)
> - [【区块链与密码学】第6-7讲：SM9数字签名算法](https://zhuanlan.zhihu.com/p/505405890)

<a name="v6L76"></a>

#### SM9加密算法
> **预备知识:**
> - **KDF($\cdot$)**：密钥导出函数，根据输入输出一个密钥　$K＝（K_1,K_2）$，
> - **MAC(K,M)**: 消息认证码，通过K认证消息M的完整性。
> - 注意：KDF在SM9中有专门的介绍，这里省略了这一部分。
> 
<br />

> **SM9加解密算法：**
![](https://image.54rookie.com/blog/171568644620240514193406.png)
> 
**正确性的证明：**
![](https://image.54rookie.com/blog/171568646020240514193419.png)

<a name="wdwwb"></a>

### 伪随机函数（PRF）与（OPRF）
<a name="fZCVa"></a>

#### 概念
> **简要介绍：**

![](https://image.54rookie.com/blog/171568647720240514193436.png)

> **正式定义：**

![](https://image.54rookie.com/blog/171568649220240514193451.png)

<a name="Y2zd4"></a>

#### 基于PRF的CPA加密方案
![](https://image.54rookie.com/blog/171568650620240514193506.png)
> 
> 
> **证明备注：**
> - 当D面对的是一个真随机函数时，A为了在游戏中获得优势，选择$m_0,m_1$之前一共进行了q(n)次Oracle查询，如果他这q(n)次全部查询的是$m_0$的密文，最好的情况是：A每次询问得到的密文$<r,y\oplus m>$中 r都不同，则他能获得$m_0$的q(n)个不同的密文。由于加密时选择的$r$一共有$2^n$种可能，也就是$m_0$至少有$2^n$个不同的密文。所以A区分$m_0$的密文成功率不超过$q(n)/2^n$,故             
![](https://image.54rookie.com/blog/171568652220240514193522.png)
> - 上面的$ε(n)$表示当D面对的是伪随机函数的时候，A赢得游戏的优势
> 
> **参考文献：**
> - [https://blog.csdn.net/weixin_39578432/article/details/120405776](https://blog.csdn.net/weixin_39578432/article/details/120405776)

<a name="wMscg"></a>

#### PRF的应用
> ![](https://image.54rookie.com/blog/171568654320240514193543.png)
> 参考文献：
> - [https://www.cnblogs.com/pam-sh/p/16216240.html](https://www.cnblogs.com/pam-sh/p/16216240.html)

<a name="gAzeK"></a>

### 盲签名算法【基于RSA的】
<a name="bv0mR"></a>

#### 盲签名(Blind Signature)
> 是由Chaum,David提出的一种数字签名方式，其中消息的内容在签名之前对签名者是不可见的（盲化）。经过盲签名得到的签名值可以使用原始的非盲消息使用常规数字签名验证的方式进行公开验证。盲签名可以有效的保护隐私，其中签名者和消息作者不同，在电子投票系统和数字现金系统中会被使用。
> 盲签名常常被类比成下面的场景：Alice想让Bob在自己的文件上签名，但是不希望Bob看到文件内容，于是Alice在文件上方叠放了一张复写纸，然后将文件和复写纸放入信封密封起来交给Bob。Bob再拿到信封后验证了Alice的身份后，直接在密封好的信封上签字，这样虽然Bob是对密封后的信封签字，但是Alice拿到签名后的信封后，拆开信封就可以拿到经过Bob签字的文件。

<a name="HKbXV"></a>

#### 基于RSA的盲签名实现

![](https://image.54rookie.com/blog/171568655720240514193556.png)

<a name="DQhwC"></a>

### 群签名
<a name="es2vj"></a>

#### 群签名的概念
> 群签名是这样一个数字签名：在一个群签名的方案中，一个群体中的任意一个成员可以代表这个群体对消息进行签名，并且其他人可以使用群公钥对这个签名进行公开验证。在验证时，验证者只能验证签名是来自这个群组的，但是无法知道到底是群中的哪个成员对消息进行了签名。
> 在群签名中，存在一个群管理员，该管理员可以通过对签名进行操作得到签名者的真实身份。

<a name="qNWFl"></a>

#### 群签名的步骤
> **一个群签名是一个包含下面过程的数字签名方案：** <br>
> （1）创建：一个用以产生群公钥和私钥的概率多项式时间算法。<br>
> （2）加入：一个用户和群管理员之间的使用户成为群管理员的交互式协议。执行该协议可以产生群员的私钥和成员证书，并使群管理员得到群成员的私有密钥。<br>
> （3）签名：一个概率算法，当输入一个消息和一个群成员的私钥后，输出对消息的签名。<br>
> （4）验证：一个概率算法，当输入一个群成员的签名和群公钥后，可以判断签名是否属于这个群。<br>
> （5）打开：一个在给定一个签名及群私钥的条件下确认签名人的合法身份的算法。 <br>
> 
> **群签名新的属性**：
> - 公钥大小固定：
>    - 公钥的大小和生成的签名可以不依赖于组的大小【CS97方案】，这一特性对于群签名方案的构建和应用是非常重要的，它避免了公钥和签名的大小随着有效组成员数量的增加而过度膨胀。
> - Opener和Manager分开：
>    - 将组管理员的权限稀释为两部分，Opener用来对群成员的签名进行追踪，得到群成员的真实身份乐；而Manager用来管理群成员的加入和撤销。
>    - 有些方案还存在一个Tracer，他可以判断两个群签名是否来自同一个群成员。通过这种权力的稀释，可以降低用户对群管理员信任程度。
> - 半动态模型：
>    - 允许用户再需要的时候动态的加入群组，或者允许群管理员动态的对群成员进行撤销。实现撤销常见的方法如下：
>       - ① 组管理员更新组公钥，并将其发送给为被撤销的用户
>       - ② 使用累加器：它可以高效的队组成员进行撤销和加入
>       - ③ 签名者在签署消息，或者根据组的变化更新自己的密钥时，需要提供合格的成员资格证明。常见的方法是把非法用户的id放入黑名单，在更新密钥的时候，将黑名单内的用户证书将面临除零异常
>       - ④ 验证者本地撤销：GM发现恶意用户的签名之后，将签名者的身份发给签名的验证者。这种撤销方式只有验证者拥有撤销列表。
> - 全动态模型：
>    - 允许动态注册用户，又允许动态撤销组成员，使得该算法具有更强的安全性和更高的实用性

<a name="rUOl2"></a>

#### 群签名的一个实例（基于RSA的群签名）
> **系统初始化：**
> - 群管理员选择RAS的公钥（n，e）
> - 群管理员选择生成元为g的循环群G，G的阶为n
> - 选择一个$a∈Z_n^*$，这里a对于n的两个素数因子p，q都有较大的乘法阶
> - 选择密钥长度的上界 λ ，和一个常数 ε ，其中 ε > 1
> - 该群的公共参数为 **params = {n，e，G，g，a，λ，ε}**
> 
> -  **成员加入：**
> - 假设Alice想要加入这个群组，她首先选择一个私钥 x ，
> - Alice计算:
>    - $y = a^x (mod\ n)$
>    - $z = g^y$（z作为成员密钥）
> - Alice发送 y，z 和自己对 z 的个人签名给群管理员GM，并使用知识签名证明自己知道满足$y=a^x(mod\ n)$的 x 。
> - GM验证y和z的合法性，验证知识签名从而确定Alice是知道 x 的。
> - GM保留（y，z）用于日后打开群签名。
> - GM生成Alice的群成员证书$v = (y + 1) ^ {1/e}\ (mod\ n)$,并将 v 发送给Alice。
> - Alice可以通过计算验证 v 的正确性。
> 
> - **成员进行群签名：**
> - 随机选择 $r∈Z_n^*$
> - 计算$\widetilde{g}=g^r$
> - 计算$\widetilde{z}=\widetilde{g}^{\ y}(mod \ n)$
> - 计算$v_1$ = SKLOGLOG[[ $x:\widetilde{z}=\widetilde{g}^{α^x}$ ]](m)
> - 计算$v_2$ = SKROOTLOG[[ $v:\widetilde{z}\widetilde{g}=\widetilde{g}^{v^e}$ ]](m)
> - 群签名的结果为$sig=\{\widetilde{g},\widetilde{z},v_1,v_2\}$
> 
> - **群签名的验证：**
> - 验证$v_1$即可证明签名者知道私钥 x，且验证者知道了$\widetilde{z}$是$\widetilde{g}^{α^x}$的形式。则$\widetilde{z}\widetilde{g}$是$\widetilde{g}^{\ a^x+1}$的形式。
> - 用知识证明验证$v_2$时可知：
>    - $\widetilde{z}\widetilde{g}$的结果的形式是$\widetilde{g}^{\ a^x+1}$
>    - 验证$v_2$如果成功，证明Alice知道$a^x+1$的e次根，即$(a^x+1)^{1/e}=v$这意味着Alice知道秘钥x和她的成员密钥的成员证书v。
> - 综上：只要验证了上述群签名就能验证签名 sig 确实来自这个群组的某个成员。（上述验证中验证了签名者群成员证书v的合法性）
> 
> - **打开群签名**
> - 当遇到特殊情况时，需要知道签名者的真实身份，这是群管理员可以做到这一点：
>    - 由于$\widetilde{z}=\widetilde{g}^{\ y}(mod \ n)$，且GM存储了每个群成员的（y，z）
>    - 所以，GM遍历所有的 y ，如果满足上述等式，就能找到签名者的真实身份。
> 
参考文献：
> - 97年发表的论文《 Efficient Group Signature Schemes for Large Groups 》
> - CSDN：[https://blog.csdn.net/zhang_hui_cs/article/details/8965338](https://blog.csdn.net/zhang_hui_cs/article/details/8965338)

<a name="WIiHn"></a>

#### 其他群签名实例
> - BBS签名方案
> - 基于ECDSA的群签名方案
> - CL群签名方案
> 
**具体内容见：**
> - [群签名方案](https://www.yuque.com/xiaozeng-lhkfj/guc7a3/db90kebght2ps6r2?view=doc_embed)

<a name="hsDT1"></a>

### 环签名
<a name="GZ9ZO"></a>

#### 环签名的概念
> **环签名的概述：**
> - 环签名(ring signature)是一种数字签名方案，最初由Rivest等人提出，环签名是一种简化的群签名,环签名中只有环成员没有管理者,不需要环成员间的合作。【在群签名中需要事先生成一个群，随后用户才能加入该群，从而代表该群进行签名】
> 
**环签名的定义：**
> - 假定有 n 个用户，每一个用户

![](https://image.54rookie.com/blog/171568659220240514193632.png)

和与之对应的私钥 

![](https://image.54rookie.com/blog/171568660420240514193644.png)

环签名是一个能够实现签名者无条件匿名的签名方案，它主要由下述算法组成：
>    - 1）**生成Gen**：一个概率多项式时间（PPT）算法，输入为安全参数k，输出为公钥和私钥。这里假定 Gen 为每一个用户

![](https://image.54rookie.com/blog/171568662020240514193700.png)

产生一个公钥![](https://cdn.nlark.com/yuque/0/2023/svg/33564410/1693730388152-96304564-876c-4ef5-952e-c30b9e2be18a.svg#clientId=uf8be357c-9109-4&from=paste&id=EQZuY&originHeight=16&originWidth=17&originalType=url&ratio=1.100000023841858&rotation=0&showTitle=false&status=done&style=none&taskId=u86427e5d-275f-422b-9f71-eb0a39ba9bf&title=)和私钥![](https://cdn.nlark.com/yuque/0/2023/svg/33564410/1693730388529-5d9c33ae-7606-4566-a284-995b3a163fcf.svg#clientId=uf8be357c-9109-4&from=paste&id=Am6us&originHeight=15&originWidth=18&originalType=url&ratio=1.100000023841858&rotation=0&showTitle=false&status=done&style=none&taskId=u01003acc-757f-4741-b317-74b79a579bc&title=) ，并且不同用户的公私钥可能来自不同的公钥体制，如有的来自RSA，有的来自DL。
>    - 2）**签名Sign**：一个PPT 算法，在输入消息m和 n 个环成员的公钥 L={ y1 , y2 ,⋯, yn }以及其中一个成员的私钥 xs 后，对消息 m 产生一个签名 R，其中R 中的某个参数根据一定的规则呈环状。
>    - 3）**验证Verify**：一个确定性算法，在输入(m,R)后，若 R 为m 的环签名则算法输出“True”，否则算法输出“False”。
> - 环签名因为其签名隐含的某个参数按照一定的规则组成环状而得名。而在之后提出的许多方案中不要求签名的构成结构成环形，只要签名的形成满足自发性、匿名性和群特性，也称之为环签名。
> 
**环签名的性质：**
> - 正确性：如果按照正确的签名步骤对消息进行签名，并且在传播过程中签名没被篡改，那么环签名满足签名验证等式。
> - 无条件匿名性：攻击者即使非法获取了所有可能签名者的私钥，他能确定出真正的签名者的概率不超过1/n这里n为所有可能签名者的个数。
> - 不可伪造性：外部攻击在不知道任何成员私钥的情况下，即使能从一个产生环签名的随机预言者那里得到任何消息m的签名，他成功伪造一个合法签名的概率也是可以忽略的。
> 
**环签名与群签名的比较：**
> - **一般形式比较：**
>    - 标准群签名分为5步：【创建】【加入】【签名】【验签】【打开】
>    - 标准环签名分3步：【选择环成员】【签名】【验签】
> - **相同点：**
>    - **都实现了匿名性**。
>       - 在群签名中，签名者代表这个群进行签名，任何人都可以使用群公钥对这个签名进行验证。在验证过程中，验证者只知道签名者来自这个群，但是不知道签名者是群中的哪一个成员。
>       - 在环签名中，签名者代表这个环进行签名，任何人都可以对这个环签名进行验证，在验证过程中，验证者只知道签名者来自这个环，但是不知道签名者具体是环中的哪一个成员。
> - **不同点**：
>    - **匿名性不同**：
>       - 群签名实现了有条件的隐私保护，群管理员可以从群签名中找出签名者的真实身份。
>       - 环签名是无条件的匿名性。没有任何人可以去除环签名的匿名性。
>    - **创建签名的难度方法不同：**
>       - 用户想要代表某个群对某个消息进行签名，必须由群管理员完成群的【创建】，然后用户【加入】该群后才能进行。
>       - 环签名中，用户可以将自己的身份添加到他选择的任何其他用户集合中，并在这个集合上生成一个环签名，该签名只显示出签名者属于该集合，而不暴露其他信息。特别是，未签名的成员甚至可能完全不知道他们参与了这样的签名。
>    - **签名长度不同：**
>       - 群签名的长度很多都是固定的，与群成员的个数无关
>       - 环签名中，大多数的环签名方案中，签名的长度随环成员个数的增加而增加。
>    - <br />

<a name="iELGe"></a>

#### 环签名方案
> **基于RSA的环签名方案【历史上第一个环签名方案】**
> 假设环签名中有n个人，则一个真实用户的签名泄露自己身份的概率是$1 / n$，为了简单起见，下面令n = 5 来举例说明RSA环签名方案。假设有5个用户，分别为1,2,3,4,5，且用户3要对消息m进行签名，则：
> - **Gen：**
>    - 为五个用户分别生成RSA公私钥对【（$e_i,n_i$）,（$d_i,n_i$）】。**（ i = 1,2,3,4,5 ）**
> 
![](https://image.54rookie.com/blog/171568662020240514193700.png)
> - **Sign：**
>    - 签名需要用到一个对称加密算法，这里使用AES算法。环签名的计算过程如下：
>       - ![](https://image.54rookie.com/blog/171568672620240514193846.png)
> 
>    - 为了简化上述过程，不妨设有一个操作$R_i(c_i)$如下:		
>          - $R_i(c_i)$=$c_{i+1}$，计算过程如下：
>          - 其中$x_i$为随机数，$\begin{align}
&y_i=RSA\_Enc_{pk_i}(x_i)=x_i^{e_i}\ mod \ n_i \\
&z_{i+1}=c_i \oplus y_i \\
&c_{i+1}=AES\_Enc_{key}(z_{i+1})
\end{align}$
>          - 为了展示计算过程，上述操作表示为：$R_i(c_i)=c_{i+1}$----**【**![](https://cdn.nlark.com/yuque/__latex/540463312c3698b0f926a3d2fa6ae39a.svg#from=url&id=kZLWz&originHeight=17&originWidth=130&originalType=binary&ratio=1.100000023841858&rotation=0&showTitle=false&status=done&style=none&title=)**】**
>    - 通过上述假设，上述的计算过程可以简化为：
>       - 签名者【用户3】选择随机数$c_4$，然后依次计算：
>          - $R_4(c_4)=c_5$ ----【**$x_4,y_4,z_{5},c_{5}$**】
>          - $R_5(c_5)=c_1$ ----【**$x_5,y_5,z_{1},c_{1}$**】
>          - $R_1(c_1)=c_2$ ----【**$x_1,y_1,z_{2},c_{2}$**】
>          - $R_2(c_2)=c_3$ ----【**$x_2,y_2,z_{3},c_{3}$**】
>          - $R_3(c_3)'=c_4'$ ----【**$x_3',y_3',z_{4}',c_{4}'$**】
>       - 上面计算的$R_3(c_3)'$=【$x_3',y_3',z_{4}',c_{4}'$】中，$c_4'$满足$c_4'=c_4$的概率可以忽略不计，因为上述等式成立的概率仅为为$1/2^{256}$（因为AES加密的输出是256比特）
>       - 为了使其相等，令$c_4‘=c_4$，反向计算出$z_4$,然后异或计算出$y_3$，随后【用户3】可以使用自己的私钥（$d_3,n_3$）解密$y_3$得到$x_3$；
>       - 将$R_3(c_3)'=c_4'$----【$x_3',y_3',z_{4}',c_{4}'$】替换为$R_3(c_3)=c_4$----【$x_3,y_3,z_{4},c_{4}$】;这样即可得到环签名$σ=\{(e_1,n_1),(e_2,n_2),(e_3,n_3),(e_4,n_4),(e_5,n_5),c_1,x_1,x_2,x_3,x_4,x_5\}$。
> 
>    - 上述签名者【用户3】通过将正向运算替换为反向运算，得到了一个$x_3$，从而得到了环签名 σ 。
>    - 环签名的计算过程正好形成一个环，如下图：
>    - ![](https://image.54rookie.com/blog/171568672620240514193846.png)
> - **Verify：**
>    - 验证者计算：
>       - $R_1(c_1)=c_2$  ----【**$x_1,y_1,z_{2},c_{2}$**】
>       - $R_2(c_2)=c_3$  ----【**$x_2,y_2,z_{3},c_{3}$**】
>       - $R_3(c_3)=c_4$  ----【**$x_3,y_3,z_{4},c_{4}$**】
>       - $R_4(c_4)=c_5$  ----【**$x_4,y_4,z_{5},c_{5}$**】
>       - $R_5(c_5)=c_1'$  ----【**$x_5,y_5,z_{1},c_{1}'$**】
>    - 检查 $c_1'=c_1$是否成立，如果成立，输出True ，否则输出 False
>    - 这里的解密的实质就是等式$R_5(R_4(R_3(R_2(R_1(c_1)))))=c_1$成立。
> 
> **参考文献：**
> - [https://zhuanlan.zhihu.com/p/450180396](https://zhuanlan.zhihu.com/p/450180396)
> - [https://zhuanlan.zhihu.com/p/510078836](https://zhuanlan.zhihu.com/p/510078836)
> - [基础密码学系列课程3: RSA、环签名、同态加密-p1_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1Nk4y1476t/?spm_id_from=333.337.search-card.all.click&vd_source=3a79ab0dccb84a67f6cb203dd111da3b)

<a name="wt68L"></a>

####  其它环签名
> - 基于RSA的环签名方案
> - 基于离散对数的环签名方案
> - 基于椭圆曲线的环签名方案

<a name="FjUTm"></a>

### 代理重加密
<a name="YSoRO"></a>

#### 什么是代理重加密（PRE）
> 代理重加密（Proxy re-encryption）
> - 主要是通过代理服务器将一个用户用自己公钥加密的密文转换为另一个用户可以用自己私钥解密的密文，且不泄露用户的私钥和明文信息，从而实现密码共享。
> - 基于用户数据隐私性考虑，用户存放在云端的数据都是加密形式存在的。而云环境中存在着大量数据共享的场景。由于数据拥有者对云服务提供商并不完全信任，不能将解密密文的密钥发送给云端，由云端来解密并分享出去。数据拥有者自己下载密文解密后，再用数据接收方的公钥加密并分享，无疑给数据拥有者带来很大的麻烦，同时也失去了云端数据共享的意义。代理重加密可以在不泄漏数据拥有者解密密钥的情况下，实现云端密文数据共享。

<a name="vGrxo"></a>

#### 具体过程
> **直观的理解:**
> 1. 将明文M用自己的公钥$PK_A$加密，得到$C_{PK_A}=E_{nc}(PK_A, M)$，其中的M就是A想要给B的明文内容。
> 2. A：将$C_{PK_A}$发给半诚实代理商，并为其生成转化密钥，它是由A为代理商计算好的生成密钥$RK_{A→B}$；
> 3. Proxy：用A生成的密钥 $RK_{A→B}$将密文$C_{PK_A}$转化为B的私钥能够解密的密文 $C_{PK_B}$<br />，其中Proxy只是提供计算转化服务，无法获取明文；
> 4. Proxy：将生成好的$C_{PK_B}$发给B；
> 5. B：解密获得A想要密钥共享的明文M；
> 
该过程主要解放了A，A只需生成代理密钥，具体文件的传输，文件的转化，文件的存放都是半诚实代理商完成的。
> **专业描述为：**
> ![](https://image.54rookie.com/blog/171568676020240514193919.png)
> 下面为图解：
> - ![](https://image.54rookie.com/blog/proxy2.gif)
<a name="wOsNw"></a>

#### 具体实例
> **基于随机预言机模型的PRE算法实现：**
> - 我们假设Alice和Bob已经生成了他们自己的密钥对（基于P256曲线），g是曲线G的生成器，p是一个大素数，也是G的阶。$H_i$，i=2,3,4是哈希函数。m是Alice想要共享的消息或明文。Server是第三方服务器。
> - 根据离散对数问题生成密钥的方法为Alice和Bob分别生成公私钥对：
> 
![](https://image.54rookie.com/blog/171568687420240514194114.png)
> - ![](https://image.54rookie.com/blog/171568688920240514194129.png)
> 
![](https://image.54rookie.com/blog/171568690320240514194143.png)
> ![](https://image.54rookie.com/blog/171568691720240514194157.png)
> ![](https://image.54rookie.com/blog/171568692820240514194208.png)
> 
> 
> **Github上有参考价值的实现：**
> - Java：PRE java-sdk，https://github.com/geghamjivanyan/java-sdk
> - Go：goRecrypt，https://github.com/SherLzp/goRecrypt

<a name="xNU8r"></a>

#### 代理重加密的优化
> 由于非对称公私钥加密的效率低下，对于较大文件的数据共享是不合适，所以需要对PRE流程进行优化。我们可以使用对称加密来保护数据，使用PRE来保护对称加密的密钥。详细流程如下所示。
> ![](https://image.54rookie.com/blog/171568694320240514194223.png)
> 解释如下：
> 1. Alice生成sk1, pk1，同时随机生成一个对称密钥k
> 2. Bob 生成sk2, pk2
> 3. Alice用自己的公钥pk1加密对称密钥k，得到密文c1；用k加密大文件M得到密文C；然后将（C，c1）发送给代理Proxy
> 4. 当Bob想要使用消息M时，他首先向Alice发送自己的公钥pk2
> 5. Alice根据Bob的公钥pk2和自己的私钥sk1生成重加密密钥delkey，并请求Proxy得到密文c1，解密c1得到对称密钥k，随后用pk2加密k得到c2发给Bob
> 6. proxy用delke重加密密文C。得到newC，并将newC发送给Bob
> 7. Bob用自己的私钥sk2分别解密newC和c2得到C和k，并用k解密C得到M

<a name="uKsxt"></a>

### 可证明安全理论
> 证明一个方案是安全的通常只需要证明敌手攻破这个方案的概率是可忽略的就行了。如果在实验中，任何PPT（PolynomialTime 多项式时间）敌手成功公婆方案的概率中，最大值高于1/2的部分可以忽略不记，那么就称这个加密方案是安全的。
> 这里提到了一个概念，“可忽略的概率”。那么到底什么样的概率是可以忽略的呢？

<a name="l03BU"></a>
#### 可忽略的概率
> 函数f是可忽略的，如果对于每个多项式p(·)，存在一个N，使得所有的整数n>N，都满足f(n)<(1/p(n))。
> 我们通常将一个可忽略函数称为negl。
> 对于可忽略的函数 negl1 和 negl2，他有如下性质“
> - 函数negl3被定义为negl3(n) = negl1(n) + negl2(n)，则函数是可忽略。
> - 对于任何多项式p，函数negl4(n)被定义为negl4(n) = p(n) · negl1(n)，则函数是可忽略的。
> 
第二点可以理解为一个事件发生的概率是多项式的，那么这个实验重复多项式次，依旧是可以忽略的。例如，中彩票的概率是忽略不计的，那么我们买n个多项式次彩票，依旧是可以忽略的。
> **参考文献：**
> - [https://blog.csdn.net/weixin_39032619/article/details/109569769](https://blog.csdn.net/weixin_39032619/article/details/109569769)

<a name="CSdOf"></a>
#### 基于模拟的安全
> 基于模拟的安全是指
> - 基于模拟的安全性的精髓在于, **模拟没有使用到需要保密的信息, 但是攻击者却无法区分模拟场景和真实场景**. 此时Experiment(无论是real还是ideal(即模拟的那个))中, 敌手到底输出什么已经不重要, 因为Experiment中的敌手只是个陪衬, 真正的敌手是两个Experiment的区分器. 根据定义, 区分器无法说出哪个Experiment是含有要保护的信息的, 那么自然也就不可能从真实的Experiment中拿到想要的信息了.
> - 个人理解，在**Simulation-based Security**中，敌手的**目标**没有被明确定义，仅仅可证模拟环境与真实环境不可区分，假设敌手从模拟脚本中学到的知识为 L\mathbb{L} （泄露量Leakage），那么敌手从真实脚本中学到的知识亦为 L\mathbb{L} ，否则敌手就可以区分模拟环境和真实环境。若敌手在真实环境中可以达成某种目标（对“攻破方案”的具体定义），那么敌手在模拟环境中同样可以达成该目标，我们可以在模拟环境中尝试分析泄漏量 L\mathbb{L} （这样就不用管实际应用中用户的密钥成分是什么）。
> 

