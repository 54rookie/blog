+++
title = '零知识证明'
date = 2024-04-05T11:16:56+08:00
draft = false
tags = ['密码学']
+++

> 这里给出零知识证明的详细内容

<a name="eS7nG"></a>
### 零知识证明的相关概念
<a name="AwO4B"></a>

#### 定义：
> - 证明者（prover）在不向验证者（verifier）提供任何有用的信息的情况下，使验证者（verifier）相信某个论断是正确的。

<a name="FbNF1"></a>

#### **需要满足的满足的条件：**
> 1. 完备性（Completeness）：只要证明者拥有相应的知识，那么就能通过验证者的验证，即证明者有足够大的概率使验证者确信。；
> 2. 可靠性（Soundness）：如果证明者没有相应的知识，则无法通过验证者的验证，即证明者欺骗验证者的概率可以忽略。
> 3. 零知识性（Zero-Knowledge）：证明者在交互过程中仅向验证者透露是否拥有相应知识的陈述，不会泄露任何关于知识的额外信息。

<a name="aqTda"></a>

### 直观举例
<a name="GveKT"></a>

#### 交互式零知识证明：
> - 交互式的零知识证明指的是：证明者（prover）与验证者（verifier）通过若干轮的交互，使得验证者相信证明者确实拥有某个秘密，且证明者不能得到这个秘密的任何信息。
> - 色盲游戏
>    - Alice是色盲，Bob不是色盲，在Bob手上有两个大小，形状完全一样的球，但这两个球的颜色不一样，一个球是蓝色的，另一个球是红色的，由于Alice是色盲，所以Alice无法分辨这两个球是否是一样的，Bob需要向Alice证明这两个球是不一样的。在这里，Alice被称为验证者，他需要验证Bob的陈述正确与否，Bob被称为证明者，他需要证明自己的陈述（存在两个颜色不一样的球），Bob需要在Alice不能获得两个球的颜色的情况下，向Alice证明这两个球的颜色是不一样的这个事实，这与零知识证明的定义是相符合的。
>    - Alice当Bob的面拿起两个球，左手拿蓝球，右手拿红球，然后将双手放到背后，这样Bob就看不到Alice手上的球了，Alice在背后随机交换左右手上的球，交换完成后Alice将手伸出，并询问Bob两个球是否交换过位置，如果Bob能看到球上的颜色，那么每次Alice换过球的位置后，Bob都能正确回答出Alice的问题。
>    - 第一次，Alice偷偷交换了手中球的位置，然后Alice问Bob是否交换了球的位置，如果Bob回答Yes，那么Alice有50%的概率相信Bob是可以区分这两个球的颜色，因为Bob有1/2的概率蒙对，所以Alice可以在进行一次测试。如果Bob回答No，那么Alice可以肯定Bob不能区分两个球的颜色。
>    - 第二次，Alice没有交换手中球的位置，然后Alice问Bob是否交换了球的位置。如果Bob回答No，那么Alice有75%的概率相信Bob是可以区分两个球的颜色。
>    - 第一次迭代后，Alice可以说Bob陈述的断言为真的概率为50％。如果Bob第二次回答正确，那么Alice可以说Bob陈述为真的概率达75％。在第三次迭代后，它将是87.5％。如果连续n次Bob都通过了检查，则Alice有1-(1/2)^n 的概率可以认为 Bob 说的是真的，这两个球的确是有红蓝两种颜色。
>    - 零知识证明是一种基于概率的验证方式，验证者（verifier）基于一定的随机性向证明者（prover)提出问题，如果证明者都能给出正确回答，则说明证明者大概率拥有他所声称的“知识”。零知识证明并不是数学意义上的证明，因为它存在小概率的误差，欺骗的证明者有可能通过虚假的陈诉骗过验证者。换句话说，零知识证明是概率证明而不是确定性证明，但是也存在技术能将误差降低到可以忽略的值。

<a name="Tkhsw"></a>

#### 非交互式零知识证明：
> - 交互式零知识证明协议依赖于验证者的随机尝试，需要证明者和验证者进行多次交互才能完成。非交互式零知识证明（Non-Interactive Zero-Knowledge, NIZK）将交互次数减少到一次，可实现离线证明和公开验证。在区块链等零知识证明应用场景中，非交互的性质是必须的，因为在区块链系统中，不能假设双方一直在线进行交互，在区块链网络上，证明者只要向全网广播一条证明交易，网络上的矿工在将这条交易打包到区块中的时候就帮验证者完成了零知识证明的校验。
> - 数独游戏
>    - 数独是源自18世纪瑞士的一种数学游戏，是一种运用纸、笔进行演算的逻辑游戏。玩家需要根据9×9盘面上的已知数字，推理出所有剩余空格的数字，并满足每一行、每一列、每一个粗线宫（3*3）内的数字均含1-9，不重复。【下图给出了一个数独游戏的题目，将空白部分填满即可赢得游戏】
![](https://image.54rookie.com/blog/171568876820240514201247.png)

>    - Alice为了向Bob证明他已经解决了一个数独难题，创建了一个防篡改的机器M。Alice将生成好的数独答案放入到机器M中，机器M可以向Bob发送证明。Alice的机器遵循以下公开可验证的协议：
>    - 首先，Alice在机器中放入尚未被解决的原始数独题目，数独中的谜题卡片三张正面朝上，例如，单元格C3具有3张正面朝上的9号卡片。【即，在3行9列的位置正面朝上放三张数字9的卡片】
>    - 则上述题目在机器M中的样子如下图：
![](https://image.54rookie.com/blog/171568879220240514201312.png)
>    - 机器中每个位置都放了三张卡片，这是因为最后验证的时候，每个位置需要验证“行，列，九宫格”，故需要三张卡片。
>    - 接下来，Alice上机器将他的答案正面朝下放置在相应的单元格上，同样也是每个单元格放三张。得到如下结果：
>    - ![](https://image.54rookie.com/blog/171568881320240514201333.png)
>    - 最后Bob向机器获取证明，机器返回给Bob27个袋子：
>       - 机器将数独中每一行9张卡片取出，并分别混淆后放入一个袋子中，一共有9行，所以9个袋子
>       - 机器将数独中每一列9张卡片取出，并分别混淆后放入一个袋子中，一共有9列，所以9个袋子
>       - 机器将数独中每个粗线宫（3*3）内卡片取出，并分别混淆后放入一个袋子中，一共有9个，所以9个袋子
>    - Bob分别对这27个袋子进行检查，如果每个袋子中的卡片都包含数字1到9，而且没有任何数字丢失或重复，那么Bob可以确认Alice的确解开了数独，并且Bob并没有从机器返回的证明中获取任何关于数独解的知识，因为机器返回给Bob袋子中的数据是被随机打乱的。

参考文献
> - [零知识证明介绍](https://zhuanlan.zhihu.com/p/152065162)

<a name="eLhox"></a>

### Sigma协议
<a name="B4dPK"></a>

#### 预备知识
> **Definition 1: (Effective relation)【有效关系】**
> -  指的是一组二元关系$R ⊆ X × Y$ 其中 $X,Y,R$ 为有效的可辨认的有限集合。 $Y$ 中的元素被称作statements【声明】。如果$(x,y) ⊆  R$，则称 x 为 y 的witness【证据】
> 
<br />
> **Definition 1: (homomorphisms maps)【同态映射】**
> ![](https://image.54rookie.com/blog/171568884420240514201404.png)
> 参考文献：[https://zhuanlan.zhihu.com/p/622105041](https://zhuanlan.zhihu.com/p/622105041)

<a name="fbqW7"></a>

#### Sigma的定义
> **Definition 2: (Sigma protocol)【Sigma协议】 **
> - 设 $R ⊆ X × Y$是一个effective relation。那么一对 $(P,V)$ 构建在 $R$ 上的一个Sigma protocol 为：
>    - P 是一个叫做 prover 的交互式协议，其输入为一个（witness，statement）对。即$(x,y) ⊆ R$
>    - V 是一个叫做 verifier 的交互式协议，其输入为一个 statement ，即 $y ⊆  Y$
>    - P 和 V 的三轮交互满足下面三个性质，即【正确性】【知识可靠性】和【HVZK】
> 
>    - P 和 V 的交互过程为：【如下图】
>       - 首先 P 计算一个**承诺(commitment) t** ，将其发送给 V ；
>       - 在收到了来自 P 的消息 t 后， V在有限的挑战空间C中随机选取一个**挑战(challenge) c**，并将其发送给 P ；
>       - 在接收到来自 V 的挑战 c 后， P 计算出一个**响应(response) z** ,将其发送给 V ；
>       - 在收到了来自 P 的消息 t 后,V 输出accept或者reject。 V 的输出由statement y 和交互中的消息 conversation$(t,c,z)$ 严格计算得出。
![](https://image.54rookie.com/blog/171568886320240514201423.png)
>    - 协议的要求是，对于所有的 $(x,y) \in R$ ，当$P(x,y) 与 V(y)$交互后， $V(y)$ 总是输出accept。为了系统的安全性，挑战空间的大小应该为sup-poly（超过多项式大小）。
> 
> **Definition 3: (Correctness)【正确性】**
> - 设$(P,V)$是关于关系$R ⊆ X × Y$ 的一个Sigma协议。如果对于任意的$(x,y)∈R$，验证者 V 都接受证明者 P 的证明，那么称这个Sigma协议具有正确性。
> 
> - 关于**Correctness**的一些说明：
>    - 正确性显然是一个协议应该满足的最基本的是性质，如果协议不满足正确性，那么就无法达成构造这个协议最初的目的--向别人证明自己拥有秘密。
> 
> **Definition 4: (Special honest verifier zero knowledge)【HVZK】**
> - 设 $(P,V)$是关于关系 $R ⊆ X × Y$ 的一个Sigma协议，且挑战空间为 C 。如果存在一个高效的概率性算法 $Sim(Y,C)$(称作simulator），其输入为 $(y,c) \in Y\times C$ 且满足：
>    1. 对于所有的输入$(y,c) \in Y\times C$，模拟器$Sim(Y,C)$ 能够输出一对 $(t,z)$使得$(t,c,z)$对于statement$Y$来说是一个被 accpeted 的 conversation。
>    2. 对于全体$(x,y) \in R$，我们随机选择$c'\stackrel{R}{\longleftarrow}C$，然后用模拟器计算$(t',z')\stackrel{}{\longleftarrow}Sim(y,c)$。使得**《模拟器产生的**$(t',c',z')$**的分布》**与**《正常运行Sigma协议**$(P,V)$**得到的**$(t,c,z)$**的分布》**相同，我们称Sigma协议$(P,V)$是 special HVZK 。Special的原因在于：
>       - 1） Sim 需要 c 作为额外输出；
>       - 2）就算 y 的 witness 不存在，**Sim** 也可以输出一个被 accepted 的 conversation。
> 
> - HVZK的一些说明:
>       - 由于** Sim **产生的$(t',c',z')$与正常运行Sigma协议产生的$(t,c,z)$在计算上不可区分,所有敌手不可能从$(t,c,z)$得知到任何关于秘密 x 的信息.  
>       - 这是因为, 如果敌手能从$(t,c,z)$中得到秘密 x 的信息 , 那么由于$(t,c,z)$和$(t',c',z')$不可区分,则这个敌手也能从$(t',c',z')$中得知秘密 x 的信息. 这是不可能的 , 因为$(t',c',z')$中根本不含由秘密 x .
>       -  上述模拟器$Sim(Y,C)$不具备秘密值 x ，但拥有一个能力 **决定或者预知 **验证者的挑战值 c  。
> 
>       - 如果能够构造出一个式Sim，它产生的三元组$(t,c,z)$与Sigma协议产生的三元组是不可区分的。由于Sim产生的三元组跟秘密并没有任何关系，且诚实的验证者不能区分两个二元组，所以诚实的验证者不能从Sigma协议的三元组中得到任何秘密的信息。【否则他可以根据这个秘密信息区分两个三元组】
> 
<br />
> **Definition 5: (Knowledge soundness)【知识可靠性】**
> - 设$(P,V)$是关于关系$R ⊆ X × Y$ 的一个Sigma协议。如果存在一个高效的确定性的算法$Ext$【称作一个witness extractor】使得：
>    - 给定一个statement $y$ ，以及两个关于 $y$ 被 accepted 的 conversation $(t,c,z) 和 (t,c',z')$，并且$c \ne c'$，存在**《提取器**$Ext$**》**能够输出 $x \in X$使得$(x,y) \in R$（ x 是 y 的witness）
>    - 即存在一个**《提取器**$Ext$**》**使得：$Ext((t,c,z),(t,c',z'))=x$；则我们称$(P,V)$提供 【知识可靠性】knowledge soundness。
> 
> - Knowledge soundness的一些说明：
>    - 如果协议具备这一性质，那么一个不诚实的证明者至多只能伪造一个可以被接受的响应。 因为，如果他能够伪造多于1个的响应，他必然知道秘密值 x  。
>    - 这是因为，不诚实的证明者不知道秘密 x ，而如果他伪造了两个被接受的响应，那么就可以使用上面所说的**《提取器**$Ext$**》**提取出秘密 x 。这与证明者不知道秘密 x 相矛盾。
>    - 上述性质说明，任何人都可以通过公开交互信息获取证明者的秘密 x 。
>    - 这个性质主要约束了恶意的prover P，保证verifier V能通过交互推出来 P 到底有没有骗自己；换句话说，如果证明方 P 没有witness $x$，那么P无法说服 V 相信他确实有证据$x$。所以可以理解为：它存在的意义就是让 P 不要说谎，否则作为验证者就能发现，可视为对 P 的约束。(【5】中大佬的观点 )
> 


<a name="WRwRa"></a>

#### Sigma协议的例子
> 说明：
> - 下面的协议中，只有Schnorr协议给出了三个性质的证明，其它证明可以去参考文献【5】中查看。
> 

> **Schnorr协议过程：**
> - 设 $\mathbb{G}$是一个阶为素数 q 的循环群，其生成元为$g \in \mathbb{G}$ 。设证明人 P 保存私钥$\alpha \in \mathbb{Z}_q$，对应的公钥匙为 $u = g^{\alpha} \in \mathbb{G}$ 。 P 需要向 V 证明其拥有$\alpha$。这里 $\alpha$是 witness， $u=g^{\alpha}$是 statement。Schnorr 身份认证协议过程为：【如下图】
>       - P 计算$\alpha_t \stackrel{R}{\longleftarrow}\mathbb{Z}_q,\ u_t\stackrel{R}{\longleftarrow}g^{α_t}$，并将 $u_t$发送给 V ;	【$commitment=u_t$】
>       - V 计算$c\stackrel{R}{\longleftarrow}C ,\ \ \  C \subset \mathbb{Z}_q$并将 c 发送给 P ；	    	【$challenge=c$】
>       - P 计算$\alpha_z \leftarrow \alpha_t + \alpha c$，并将$\alpha_z$发送给 V ；		【$response=\alpha_z$】
>       - V 检查如果 $g^{a_z} = u_t \cdot u^c$ ；V 输出accept，否则输出reject。
> 
![](https://image.54rookie.com/blog/171568891420240514201514.png)
> - 安全性：
>    - Schnorr's protocol 的安全性是构建在离散对数问题上的，其证明的方式为假设攻击者在不知道 $\alpha$ 可以构建对于一个 u 合法的 conversations，那么我们就可以利用攻击者的能力来解决离散对数问题。由于逆否命题是等价，如果离散对数问题无法攻破，那么Schorr's protocol 就是安全的。
>    - proof：
>       - 假设攻击者对于 u 可以产生两个被 accepted 的 conversation$(u_t,c,\alpha_z)$ 和 $(u_t,c',\alpha'_z)$且他们满足$c \neq c'$，则有$g^{\alpha_z}=u_t \cdot u^c$以及 $g^{\alpha'_z}=u_t \cdot u^{c'}$成立，将两式相除得 $g^{\Delta \alpha}= u^{\Delta c}$,其中 $\Delta \alpha = \alpha_z - \alpha'_{z}$；$\Delta c = c-c'$。由于$\Delta c \ne 0$ ，且群$\mathbb{G}$ 是素数阶得循环群，因此有$1/ \Delta c \in \mathbb{G}$，则有 $g^{\Delta z/\Delta c} = u$，故我们得到了离散对数问题$Dlog_gu$ 的解 $\Delta z/ \Delta c$。
> - HVZK：
>    - 证明 HVZK 在于如何构建一个产生 conversation 并被 verifier 接受的 **Sim(u)** ，且由 **Sim** 产生出来的conversation 中元素的分布和正常 P，V 交互产生的 conversation 中元素的概率分布相同。如果我们设 vk = u ，则 Sim 计算：$\begin{align}
&α_z \stackrel{R}{\leftarrow} Z_q
&c \stackrel{R}{\leftarrow} C \ \ \ 
&u_t ←g^{α_z}/u^c
\end{align}$
>    - 在真实的交互过程中， c 和 $\alpha_z$分别在挑战空间 C 和 $\mathbb{Z}_q$ 中服从均匀分布，且 $c,\alpha_z$ 相互独立。此外 $u_t$是由$g^{\alpha_z}=u_t \cdot u^c$唯一确定的，因此可以明显看出， **Sim** 产生的 conversation 中元素的概率分布同正常交互所产的 conversation 中元素的概率分布相同。
> - Knowledge soundness：
>    - 由Knowledge soundness 的定义以及Schnorr's protocol的安全性分析可知，Schnorr's protocol满足Knowledge soundness。
>    - <br />
> 
**Okamoto协议过程**
> - 设$\mathbb{G}$是一个阶为素数 q 的循环群，其生成元为 $g \in \mathbb{G}。 h \in \mathbb{G}$是群中任意一个元素。Okamoto’s protocol中的关系为：$R=\{ (\alpha,\beta),u) \in \mathbb{Z}^2_q \times \mathbb{G} : g^{\alpha}h^{\beta}=u \}$
> - 协议的过程如下图：【其中 $C \subset \mathbb{Z}_q$】
>       - 【$commitment=u_t$】
>       - 【$challenge=c$】
>       - 【$response=(\alpha_z,\beta_z)$】
> 
![](https://image.54rookie.com/blog/171568893320240514201533.png)
> 
> **The Chaum-Pedersen协议过程**
> - 该协议基于DH-triples。设$\mathbb{G}$是一个阶为素数 q 的循环群，其生成元为 $g \in \mathbb{G}$。对于 $(\alpha,\beta,\gamma) \in \mathbb{G}$如果$\alpha \beta = \gamma$我们就说$(g^\alpha,g^\beta,g^\gamma)$是一个DH-triples【DH三元组】。等价的，如果$(u,v,w)$是一个DH-tripes，当且仅当存在一个$\beta \in \mathbb{Z_q}$ 使得$v= g^\beta , w = u^\beta$ 。在Chaum-Pedersen 协议中的关系 **R**为：$R:= \{ (\ \beta,(u,v,w)\ ) \in \mathbb{Z}_q \times \mathbb{G}^3 : v=g^\beta ,w=u^\beta \}$; 
> - 协议的过程为：【其中$C \subset \mathbb{Z}_q$】
>       - 【$commitment=(w_t,v_t)$】
>       - 【$challenge=c$】
>       - 【$response=\beta_z$】
> 
![](https://image.54rookie.com/blog/171568897020240514201610.png)

<a name="YpAxu"></a>

#### 线性Sigma协议
> **线性Sigma协议：**
> - 上述Schnorr, Okamoto, 和 Chaum- Pedersen 协议都是一种更加一般的 Sigma protocol 的特例。这种更加一般的 Sigma protocol 是要证明元素之间的线性关系。设$\mathbb{G}$是一个阶为素数 q 的循环群，它的生成元为$g \in \mathbb{G}$我们考虑一个布尔函数 $\phi$：	
> 
$\phi (x_1,x_2,...,x_n):=\{u_1=\prod_{j=1}^{n}g_{1j}^{x_j}\  \wedge \ u_2=\prod_{j=1}^{n}g_{2j}^{x_j} \wedge ... \wedge 
u_m=\prod_{j=1}^{n}g_{mj}^{x_j} \}$
> - 在函数 $\phi$ 中， $g_{ij} ,u_i \in \mathbb{G}$。这些群元素一部分可以是系统参数甚至是常量，另一些元素是针对函数的特殊变量。$x_i \in \mathbb{Z}_q$是函数$\phi$的入参，当函数中的所有等式成立则$\phi$返回true。对于这样函数的一个特定的类 F ，我们可以定义一个关系：
>    - $R:= \{((\alpha_1,...,\alpha_n),\phi) \in \mathbb{Z}_q^n \times F: \phi(\alpha_1,...,\alpha_n)= true \}$ 
>    - 在** R** 中，一个**函数**$\phi$**是一个 statement**，而一个**使得这个函数**$\phi$**为 true 的 **$(\alpha_1,...,\alpha_n) \in \mathbb{Z}_q^n$** 是这个函数 **$\phi$** 的 witness** 。而我们称这样的协议为 linear protocols 的原因在于如果我们对函数$\phi$中的等式取对数可以得到：
> 
$Dlog_g({u_j})= \sum_{j=1}^n x_i \cdot Dlog_g(g_{ij}) \ \ \ \ \ (i=1,...,m)$
> - 对于一般 linear Sigma protocol 的过程为：
> 
![](https://image.54rookie.com/blog/171568899720240514201637.png)
> **补充：**
> - 在上述 Schnorr‘s protocol 中
>       - $P((\alpha_1,...,\alpha_n),\phi)$中，n = 1，$\phi(x):= \{u=g^x\}$
>       - $\alpha_{tj}$中，j = 1 ;
>       - $u_{tm}$中，m = 1 ; 			【$u_{tm}$事实上就是承诺$\phi(\alpha_{t1})$】
>       - 将上面的条件代入即可得到 Schnorr协议
> - 在上述 Okamoto's protocol 中
>       - $P((\alpha_1,...,\alpha_n),\phi)$中，n = 2 ; $\phi(x,y) := \{u=g^xh^y\}$
>       - $\alpha_{tj}$中，j = 2 ;
>       - $u_{tm}$中，m = 1 ;			【$u_{tm}$事实上就是承诺$\phi(\alpha_{t1},\alpha_{t2})$】
>       - 将上面的条件代入即可得到 Okamoto 协议
> - The Chaum-Pedersen protocol中
>       - $P((\alpha_1,...,\alpha_n),\phi)$中，n = 1 $\phi(x) := \{ v=g^x \wedge w=u^x\}$
>       - $\alpha_{tj}$中，j = 1 ;
>       - $u_{tm}$中，m = 2 ;			【$u_{tm}$事实上就是承诺$\phi(\alpha_{t1})$】
>       - 将上面的条件代入即可得到 The Chaum-Pedersen 协议
> 
> - 对于一般的 linear protocol 是一个关于关系 R 的 Sigma协议并且满足knowledge soundness以及special HVZK。

<a name="wOTPz"></a>

#### 基于同映射的Sigma协议
> **基于同态映射的Sigma协议**
> - 我们可以利用群同态来更加清晰高效的来描述到目前为止的介绍的所有Sigma协议。设$\mathbb{H}_1,\mathbb{H}_2$是两个不知道阶的交换群，以及一个同态映射$\varphi: \mathbb{H}_1 \to \mathbb{H}_2$。为了表达的方便， 群$\mathbb{H}_1$中的运算为群加法， 群$\mathbb{H}_2$中的运算为群乘法。设$u \in \mathbb{H}_2$，证明者需要向验证着证明他知道在映射$\varphi$下 u 的原象。在这种Sigma protocol中，关系为：
> 
$R:=\{(\alpha,(u,\varphi)) \in \mathbb{H}_1 \times (\mathbb{H}_2 \times F):\varphi(\alpha)=u\}$
> 其中$\alpha \in \mathbb{H}_1$是映射 $\varphi$ 对于 $u \in \mathbb{H}_2$ 的原象。协议的过程如下：
> ![](https://image.54rookie.com/blog/171568902020240514201659.png)
> - 在$|\mathbb{H}_1| \times |\mathbb{H}_2|$最小素因子至少为 |C| 的情况下，基于同态映射的Sigma protocol满足knowledge soundness以及special HVZK。
> 


> - Schnorr 协议中
>       - $\mathbb{H}_1 := \mathbb{Z}_q,\ \mathbb{H}_2 := \mathbb{G},and \ \ \ \ \varphi_1(x):=(g^x)$
>       - $R:=\{(\alpha,(u,\varphi)) \in \mathbb{H}_1 \times (\mathbb{H}_2 \times F):\varphi(\alpha)=u\}$
> 
> - Okamoto协议中
>       - $\mathbb{H}_1 := \mathbb{Z}_q^2,\ \mathbb{H}_2 := \mathbb{G},and \ \ \ \ \varphi_1(x,y):=(g^xh^y)$
>       - $R:=\{((\alpha,\beta),(u,\varphi)) \in \mathbb{H}_1^2 \times (\mathbb{H}_2 \times F):\varphi(\alpha,\beta)=u\}$
> 
> - The Chaum-Pedersen协议中
>       -  $\mathbb{H}_1 := \mathbb{Z}_q, \mathbb{H}_2 := \mathbb{G}^2,and \ \ \ \ \varphi_2(x):=(g^x,u^x)$
>       - $R:=\{(\alpha,(u_1,u_2,\varphi)) \in \mathbb{H}_1 \times (\mathbb{H}_2^2 \times F):\varphi(\alpha)=(u_1,u_2\}$
> 
> - 一般linear protocol中 $\mathbb{H}_1:= (\mathbb{Z}_q)^n, \ \mathbb{H}_2:=\mathbb{G}^m,and \ \ \ \ \varphi_3(x_1,...,x_n) := (\prod_{j=1}^ng_{1j}^{x_j},...,\prod_{j=1}^ng_{mj}^{x_j})$

<a name="IC97D"></a>

### Fait-Shamir启发式
<a name="TKx38"></a>

##### 定义
> ![](https://image.54rookie.com/blog/171568904520240514201724.png)

<a name="zLIdI"></a>

##### 知识签名【SoK】
**定义：**
> - 知识签名实际上就是零知识证明，这里给出一个知识签名的例子，该例子经常会用到，目前我遇到最多的是在群签名中使用。

**离散对数知识签名**：
> **基本形式：**
> - 离散对数的知识签名是针对这样一个问题：$y = g^x mod(n)$;  x 是私钥，y 是公钥，g 和 n 都是公开的系统参数，m是消息，现在需要让别别人证明自己拥有私钥 x，并且不泄露 x 的信息。
> - 符号表示为：
>    - ![](https://image.54rookie.com/blog/171568608020240514192800.png)
> - 这里只需要证明者给出一个（c，s）对，符合以下的等式要求即可：
>    - $c = H( m||y||g||(g^s) (y^c) )$
> - **知识签名生成：**
>       1. 选择一个随机数           $r$
>       2. 计算c：根据公式         $c=H(m||y||g||g^r)$
>       3. 计算s：根据公式         $s = r - c * x$
>       4. (c,s)即为知识签名。
> - **验证知识签名**：
>       1. 计算$c'=H( m||y||g||(g^s) (y^c) )$
>       2. 比较$c'=c$是否成立。
> - 解释说明
>    - ![](https://image.54rookie.com/blog/171568612420240514192844.png)
>       - 如果知道密钥x，执行通过上面操作过程中的四个步骤就可以轻松计算出(c,s)对的值，
>       - 如果不知道密钥x，而想算出(c,s)，只能通过3式计算，这在计算上是不可行的。
>       - 所以，如果能给出一个满足条件的（c,s）对，就能说明其拥有私钥x。
> 
<br />

> **拓展形式**：
> - 离散对数的知识签名是针对这样一个问题：$y_1 = g_1^x\ mod(n);y_2 = g_2^x\ mod(n)$;  x 是秘密值，$y_1,y_2$是公开的。$g_1,g_2$ 和 n 都是公开的系统参数，m是消息，现在需要向别人证明自己拥有秘密值 x ，且这个 x满足$y_1 = g_1^x\ mod(n);y_2 = g_2^x\ mod(n)$，并且证明过程中不泄露 x 的信息。
> - 这里只需要证明者给出一个（c，s）对，符合以下的等式要求即可：
>    - $c = H(\ m||y||g||g_1^s y_1^c||g_2^sy_2^c \ )$
> - 具体的操作过程如下：【证明过程如上】
>       1. 选择一个随机数           $r$
>       2. 计算c：根据公式         $c=H(\ m||y||g||g_1^r||g_2^r \ )$
>       3. 计算s：根据公式         $s = r - c * x$
>       4. (c,s)即为知识签名。
> 
<br />

> **更一般的形式：**
> - 离散对数的知识签名：$y_1 = g_1^{x_1} \ mod(n);\ ...\ ;y_m = g_m^{x_m} \ mod(n)$;  $x_i\ (i=1,2,...,m)$ 是秘密值，并且$y_i\ (i=1,2,...,m)$是公开的。$g_i\ (i=1,2,...,m)$ 和 n 都是公开的系统参数，m是消息，现在需要向别人证明自己拥有秘密值 $x_i\ (i=1,2,...,m)$ ，且$x_i$满足$y_i = g_i^{x_i} \ mod(n) \ (i=1,2,...,m)$，并且证明过程中不泄露$x_i\ (i=1,2,...,m)$ 的信息。
> - 这里只需要证明者给出一个$(c,s_1,s_2,...,s_m)$对，符合以下的等式要求即可：
>    - $c = H(\ m||y||g||g_1^s y_1^c||...||g_m^sy_m^c \ )$
> - 具体的操作过程如下：【证明过程如上】
>       1. 选择随机数                 $r_1,r_2,...,r_m$
>       2. 计算c：根据公式         $c=H(\ m||y||g||g_1^{r_1}||...||g_m^{r_m} \ )$
>       3. 计算s：根据公式         $s_i = r_i - c * x_i \ \  (i=1,2,...,m)$
>       4. 则$(c,s_1,s_2,...,s_m)$即为知识签名。
> - 说明：
>    - 在群签名中，经常用到这个知识签名。

<a name="yqh0E"></a>

### zk-SNARK
> 
> 参考文献：
> - [https://blog.csdn.net/qq_35739903/article/details/119455825](https://blog.csdn.net/qq_35739903/article/details/119455825)
> - [https://zhuanlan.zhihu.com/p/38205067](https://zhuanlan.zhihu.com/p/38205067)

<a name="fuMTK"></a>

### 参考文献

- 【1】[https://zhuanlan.zhihu.com/p/144899541](https://zhuanlan.zhihu.com/p/144899541)
- 【2】[https://zhuanlan.zhihu.com/p/622105041](https://zhuanlan.zhihu.com/p/622105041)
- 【3】[https://zhuanlan.zhihu.com/p/152065162](https://zhuanlan.zhihu.com/p/152065162)
- 【4】[http://blockchain.whu.edu.cn/uploads/soft/201105/1_1954088811.pdf](http://blockchain.whu.edu.cn/uploads/soft/201105/1_1954088811.pdf)【PDF】
- 【5】[https://zhuanlan.zhihu.com/p/343756241](https://zhuanlan.zhihu.com/p/343756241)【讲的很好】
- 【6】[https://zhuanlan.zhihu.com/p/144899541](https://zhuanlan.zhihu.com/p/144899541)【讲的较详细】
<a name="eJ4vk"></a>

### 补充：
<a name="IPBv4"></a>

#### Sigma协议在其它资料中的表述
> **Sigma协议簇：**
> Sigma协议簇是指一类的协议，这些协议满足一些指定的要求。值得注意的是，Sigma协议簇中的协议都是零知识证明。也就是满足Sigma协议簇的协议一定是一个零知识证明。
> 
> 1. **二元关系（预备知识）：**
> 
![](https://image.54rookie.com/blog/171568918820240514201947.png)
>    - 例如：实数中的关系“大于”可记作 $R=\{(x,y)|x,y是实数且x>y\}$
>       - 其中 R 表示这个关系，它是一个集合，集合中的元素有二元组（x,y）组成
>       - R 中的元素是所有满足 x,y 是实数且 x>y 的二元组 (x,y)
>    - 其它二元关系的例子（零知识证明常用到的）
> 
![](https://image.54rookie.com/blog/171568920420240514202004.png)
> 
> 2. **Sigma协议内容：**
> 
![](https://image.54rookie.com/blog/171568921620240514202016.png)

<a name="dlapG"></a>

#### 以Sigma协议为标准构造零知识证明
> ![](https://image.54rookie.com/blog/171568923220240514202032.png)
> 可以按照以下步骤证明该问题：
> ![](https://image.54rookie.com/blog/171568925020240514202050.png)
> ![](https://image.54rookie.com/blog/171568926420240514202104.png)
> 证明过程如图所示：
> ![](https://image.54rookie.com/blog/171568927620240514202116.png)
> 说明：
>    - 该协议是满足Sigma协议的三个性质的。因此他是一个零知识证明

<a name="n2zzO"></a>

#### Sigma协议的扩展
> **OR证明：**
> ![](https://image.54rookie.com/blog/171568929020240514202130.png)
> ![](https://image.54rookie.com/blog/171568931420240514202154.png)
> <br />
> **OR证明的性质：**
> ![](https://image.54rookie.com/blog/171568933320240514202213.png)

