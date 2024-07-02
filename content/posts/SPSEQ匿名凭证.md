+++
title = 'SPSEQ匿名凭证'
date = 2024-05-31T20:26:44+08:00
draft = false
tags = ['数字签名']
+++

这是一篇发表在亚密会上的文章，本文简单记录一下读后感觉。

## 什么是匿名凭证？
> 匿名凭证也可以称为匿名证书，用于在保护用户隐私的情况下实现身份认证和授权。
> - 匿名凭证中的匿名性并不是针对凭证的颁发者，而是针对凭证的持有者，凭证持有者可以向别人证明自己拥有凭证(证书)，同时不暴露凭证(证书)的内容。
> - 匿名凭证常见的实现方法是通过承诺-签名-证明的构造范式, 通常要求采用的签名算法具备重随机化特性, 如CL系列签名、PS系列签名及结构保持签名（SPS）。

## 匿名凭证有什么特征?
> 匿名凭证通常用来保护凭证持有者的隐私，或进行匿名身份认证等。以下给出匿名凭证的几个特性。
> - 隐私保护：用户可以证明其身份或某些属性，而不需要暴露其完整身份信息。例如，用户可以证明自己是某个俱乐部的成员，而不需要透露自己的名字。
> - 不可追踪性：当用户多次使用凭证时，凭证的使用记录是不可追踪的。即便是凭证签发机构也无法将多次使用行为关联到同一个用户。
>
## 集合承诺
> 集合承诺用来对一个集合中的元素进行承诺，非正式的对其过程进行如下的描述：
> - 假如Alice想要向Bob承诺一个集合中的元素，首先通过一个初始化算法生成"集合承诺"所需要的参数。
> - Alice发送集合A的"承诺C"给Bob。（作用是保证自己不会对集合A中的元素进行思考）
> - Alice发送集合A的"打开承诺"给Bob，证明自己没有更改集合A中的元素。
> - Bob通过"打开承诺验证"检验"打开承诺"的正确性，从而检验集合A没有被更改。
> - Alice发送集合A的子集T的"打开承诺"给Bob。
> - Bob通过"打开承诺验证"检验"打开承诺"的正确性，从而检验集合A的子集T没有被更改。
>
## 基于属性的凭证系统
> 基于属性的凭证系统(ABC)作用如下：一个用户可以选择一个属性集，请求可信机构为该用户的这些属性颁发凭证。收到凭证的用户可以匿名的向任意验证者自己拥有凭证并且不暴露凭证的内容。匿名凭证系统中，如果不能将多个匿名凭证链接到同一个用户，我们称该系统是multi-show的。
>

## CL签名和PS签名
> ### CL签名：
> 
> **CL03签名(基于离散对数的)**
> 
> **对单个消息进行签名**
>
> > **系统初始化**：选择两个大素数p,q满足p=2p'+1和q=2q'+1，然后计算 n=pq
> > 
> > **密钥生成**：随机生成三个随机数 $(a,b,c)\in_R QR_n$ ;则私钥sk=p，公钥pk=(n,a,b,c).
> > 
> > **签名**：生成随机数 e,s 计算v 使其满足等式$v^e=a^mb^sc \ \ mod\ n$，返回签名 $\sigma=(e,s,v)$ 
> > - 注：表面上看，这里的签名好像没有使用到私钥，貌似谁都可以签名。事实上，令$M=a^mb^sc$，则$v=M^{1/e} \ mod\ n$,令$ed \equiv1 \ mod\ \varphi(n)$，则有$v=M^d \ mod\ n$。可以看出、求满足条件的v的过程实际上就是使用RSA算法对消息M进行签名的过程，且签名使用的私钥$d=1/e\ mod\ \varphi(n)$。显然想要通过随机选择的e求出"私钥d"需要首先计算$\varphi(n)=(p-1)(q-1)$，这需要使用p和q，因此只有知道私钥sk=p的人才能求出v，从而对消息进行签名。这里之所以私钥sk中只包含p是因为通过p和n可以计算出q。（我在原论文中没有找到为什么签名需要用到私钥，上述内容纯属本人猜测）
> > 
> > **验签**： 检查等式 $v^e=a^mb^sc$ 是否成立：
> 
> **对多个消息进行签名**
>
> > **系统初始化**：同上
> > 
> > **密钥生成**：随机生成三个随机数$(a_1,...,a_L,b,c)$ 则私钥sk=p，公钥pk=$(a_1,...,a_L,b,c,n)$.
> > 
> > **签名**：生成随机数 e,s 计算v 使其满足等式$v^e=a_1^{m_1}a_2^{m_2}·...·a_L^{m_L}b^sc$，返回签名 $\sigma=(e,s,v)$
> > 
> > **验签**：检查等式 $v^e=a_1^{m_1}a_2^{m_2}·...·a_L^{m_L}b^sc$ 是否成立
>
> **通过承诺值对消息进行签名**（我看起来像是盲签名）
>
> > **密钥生成**：选择两个大素数p,q满足p=2p'+1和q=2q'+1，然后计算 n=pq。随机生成三个随机数 $(a,b,c)\in_R QR_n$ ;则私钥sk=p，公钥pk=(n,a,b,c).
> 
> > 假设用户Alice想要获得Bob对消息x的签名,并且不想让Bob知道消息x是什么，则：
> > - Alice首先生成随机数r，然后计算承诺$C=a^xb^r \ mod \ n$ 并将C发送给Bob
> > - Bob生成随机数r'并选择一个素数e，然后计算$v=(C \cdot b^{r'} \cdot c)^{1/e}$，发送(r',e,v)给Alice
> > - Alice计算s=r+r'，则签名$\sigma=(s,e,v)$就是Bob对消息x的签名。
>
> 对签名的知识证明：
> > 略，参考原论文: [A Signature Scheme with Efficient Protocols](https://scholar.google.com/scholar?hl=zh-CN&as_sdt=0%2C5&q=A+Signature+Scheme+with+Efficient+Protocols&btnG=)
>
> **CL04签名(基于配对的)**
> 
> **对单个消息进行签名**
>
> > **系统初始化**：BGGen($1^\lambda$) $\rightarrow (p,G_1,G_2,G_T,e,P_1,P_2)$ 
> > 
> > **密钥生成**：随机生成三个随机数(x,y,z)作为私钥sk,然后计算pk=($X=xP_1,Y=yP_1,Z=zP_1$).
> > 
> > **签名**：生成随机数 $r\in_RZ_p$ 计算 $R=rP_2$，并计算 
> > - $\sigma_1=zR$  ;  $\sigma_1=yR$  ;  $\sigma_3=yZ_2$;
> > - $C=(x+xym+xyrz)R$
> > - 输出签名$\sigma=(R,\sigma_1,\sigma_2,\sigma_3,C)$
> > 
> > **验签**：检查以下等式是否成立：
> > - $e(X,R)=e(P_1,\sigma_1)$  ;  $e(Y,R)=e(P_1,\sigma_2)$;
> > - $e(Y,R)=e(P_1,\sigma_3)$;
> > - $e(X,R) + e(\sigma_2,X)^m+e(X,\sigma_3)^r=e(P_1,C)$;
> 
> 对多个消息进行签名
>
> > **系统初始化**：BGGen($1^\lambda$) $\rightarrow (p,G_1,G_2,G_T,e,P_1,P_2)$ 
> > 
> > **密钥生成**：随机生成三个随机数$(x,y,{z_1,...,z_l})$作为私钥sk,然后计算pk=$(X=xP_1,Y=yP_1,Z_i=z_iP_1)$.
> > 
> -> **签名**：生成随机数 $r\in_RZ_p$ 计算 $R=rP_2$; 计算
> > - $\sigma_{1,i}=z_iR$ ; $\sigma_1=yR$ ; $\sigma_{3,i}=yZ_{2,i}$;
> > - $C=xR+xym_1R+xym_iz_iR$;
> > - 输出签名$\sigma=(R,\sigma_1,\sigma_2,\sigma_3,C)$;
> > 
> > **验签**：检查以下等式是否成立：
> > - $e(Z_i,R)=e(P_1,\sigma_{1,i})$ ; $e(Y,R)=e(P_1,\sigma_2)$;
> > - $e(Y,Z_{2,i})=e(P_1,\sigma_{3,i})$;
> > - $e(X,R) + e(X,\sigma_2)^{m_1}+e(X,\sigma_{3,i})^{\sum_{i=2}^mm_i}=e(P_1,C)$;
> 
> 对承诺消息进行签名
> > 略，参考原论文：[Signature schemes and anonymous credentials from bilinear maps](https://scholar.google.com/scholar?hl=zh-CN&as_sdt=0%2C5&q=Signature+Schemes+and+Anonymous+Credentials+from+Bilinear+Maps&btnG=)
> 
> 对签名的知识证明
> > 略，参考原论文：[Signature schemes and anonymous credentials from bilinear maps](https://scholar.google.com/scholar?hl=zh-CN&as_sdt=0%2C5&q=Signature+Schemes+and+Anonymous+Credentials+from+Bilinear+Maps&btnG=)
>
> **PS签名**：
> 
> 对单个消息进行签名
>
> > **系统初始化**：BGGen($1^\lambda$) $\rightarrow (p,G_1,G_2,G_T,e,g,\widetilde g)$,定义$G_1^*=G_1\{1_{G_1}\}$
> > 
> > **密钥生成**：随机生成立两个随机数(x,y)作为私钥sk,然后计算pk=($\widetilde X=\widetilde g^x,\widetilde Y=\widetilde g^y$).
> > 
> > **签名**：随机生成 $h\in_RG_1^*$ 计算 $\sigma_1=h,\sigma_2=h^{x+ym}$，输出签名$\sigma=(\sigma_1,\sigma_2)$
> > 
> > **验签**：检查是否$\sigma_1 \neq 1_{G_1}$；检查等式$e(\sigma_1,\widetilde X\cdot \widetilde Y^m)=e(\sigma_2,\widetilde g)$是否成立。
> >
> > **签名的随机化**：随机生成$t \in_R Z_p^*$，计算$\sigma'=(\sigma_1',\sigma_2')=(\sigma_1^t,\sigma_2^t)$为随机化之后的签名。
> 
> 对多个消息进行签名
>
> > **系统初始化**：BGGen($1^\lambda$) $\rightarrow (p,G_1,G_2,G_T,e,g,\widetilde g)$,定义$G_1^*=G_1\{1_{G_1}\}$
> > 
> > **密钥生成**：随机生成立两个随机数$(x,y_1,...,y_r)$作为私钥sk,然后计算pk=($\widetilde X=\widetilde g^x,\widetilde Y_1=\widetilde g^{y_1},...,\widetilde Y_r=\widetilde g^{y_r}$).
> > 
> > **签名**：随机生成 $h\in_RG_1^*$ 计算 $\sigma_1=h,\sigma_2=h^{x+\sum_{1}^r y_im_i}$；输出签名$\sigma=(\sigma_1,\sigma_2)$
> > 
> > **验签**：检查是否$\sigma_1 \neq 1_{G_1}$；检查等式$e(\sigma_1,\widetilde X\cdot \prod_{1}^r\widetilde Y^m)=e(\sigma_2,\widetilde g)$是否成立。
> >
> > **签名的随机化**：随机生成$t \in_R Z_p^*$，计算$\sigma'=(\sigma_1',\sigma_2')=(\sigma_1^t,\sigma_2^t)$为随机化之后的签名。
> 
> **对承诺进行签名**
>
> > - Alice想要获得Bob对消息m的签名，但是不想让Bob知道m的值。他发送$g^m$给Bob
> > - Bob选择$u\in_R Z_p$，然后计算 $\sigma_1=g^u,\sigma_2=(g^x (g^m)^y)^u$，将签名$\sigma=(\sigma_1,\sigma_2)$发送给Alice
> > - Alice验证等式$e(\sigma_1,\widetilde X\cdot \widetilde Y^m)=e(\sigma_2,\widetilde g)$是否成立，成立则获得了Bob对m的签名。
> > 
> > 这里的承诺存在一个小问题，Alice如果已经通过$g^m$让Bob对消息m进行了签名，如果下次她又想获得m的不同签名，Bob通过$g^m$会发现自己已经对该消息进行了签名，从而在一定程度上泄露消息m的隐私。为了解决这问题，下面的给出一个改进的PS盲签名。
> 
> PS对承诺签名的改进
>
> > **系统初始化**：BGGen($1^\lambda$) $\rightarrow (p,G_1,G_2,G_T,e,g,\widetilde g)$,定义$G_1^*=G_1\{1_{G_1}\}$；$G_2^*=G_2\{1_{G_2}\}$
> > **密钥生成**：随机生成两个随机数$(x,y)\in_RZ_P^2,g\in_RG_1^*,\widetilde g\in_RG_2^*$,然后计算$X=g^x,Y=g^y \widetilde X=\widetilde g^x,\widetilde Y=\widetilde g^y$。令密钥对$sk=X,pk=(g,Y,\widetilde g,\widetilde X,\widetilde Y)$
> >
> > 协议内容
> > - Alice想要获得Bob对消息m的签名，但是不想让Bob知道m的值。他选择$t\in_R Z_p$，然后计算 $C=g^tY^m$
> > - Bob选择$u\in_R Z_p$，然后计算 $\sigma_1'=g^u,\sigma_2'=(XC)^u$，将签名$\sigma'=(\sigma_1',\sigma_2')$发送给Alice
> > - Alice计算$\sigma=(\sigma_1,sigma_2)=(\sigma_1',\sigma_2'/\sigma_1'^t)$。随后，Alice验证等式$e(\sigma_1,\widetilde X\cdot \widetilde Y^m)=e(\sigma_2,\widetilde g)$是否成立，成立则获得了Bob对m的签名。
> > 
> 上述协议也可对多个消息进行签名，具体过程参考论文。。。
> 
> **群签名**
> > PS签名还可用于构造群签名，这是因为PS签名是可随机化的签名，并且可以提供签名的知识证明，具体过程参考论文，敲起来太累了、


## 等价类上的结构保持签名（SPS-EQ）

**$Setup(1^k) \rightarrow pp$**：运行双线性参数生成函数：BGGen($1^\lambda$) $\rightarrow (p,G_1,G_2,G_T,e,P,\widetilde P)$

**$KeyGen(pp,1^k) \rightarrow (sk,pk)$**：随机生成$(x_1,...,x_l)\in_RZ_P^l$，计算$(\widetilde X_1=x_1\widetilde P,...,\widetilde X_l= x_l\widetilde P$。输出密钥对$sk=(x_1,...,x_l)$,$pk=(\widetilde X_1,...,\widetilde X_1)$

**$Sign(M,sk) \rightarrow \sigma$**：对于待签名消息集$M=(m_1,...,m_l)$，签名者首先生成一个随机数$r\in_R Z_p^*$，然后计算$Z=r\sum_{i\in[l]}x_iM_i$ ; $R=\frac{1}{y}P$ ; $\widetilde R=\frac{1}{y} \widetilde P$。输出签名$\sigma = (Z,R,\widetilde R)$

**$Verify(M,\sigma,pk) \rightarrow 1/0$**：验证: $\prod_{i\in[l]}e(M_i,X_i)=e(Z,\widetilde Y)$ 和 $e(R,\widetilde P)=e(P,\widetilde R)$

**$ChgRep(M,\sigma,\mu,pk) \rightarrow \sigma'$**：给定一个随机化因子$\mu$，选择随机数$\psi\in_RZ_p^*$，返回：$\sigma'=(\psi\mu Z,\frac{1}{\psi}R,\frac{1}{\psi} \widetilde R)$

**$Vkey(sk,pk) \rightarrow 1/0$**：给定密钥对$sk=(x_1,...,x_l),pk=(\widetilde X_1,...,\widetilde X_1)$，验证公钥是否是对应私钥对应的公钥。



## 集合承诺，ABC系统的具体过程。

![](https://image.54rookie.com/blog/17176554361.jpg)

![](https://image.54rookie.com/blog/17176554702.jpg)

![](https://image.54rookie.com/blog/17176554913.jpg)