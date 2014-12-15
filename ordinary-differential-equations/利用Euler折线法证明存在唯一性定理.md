[1]: https://lh4.googleusercontent.com/-KF1IQRoNOg0/UprrgeM8YPI/AAAAAAAAAIo/7S-a6ieRbxY/w702-h402-no/Picard%25E5%25AE%259A%25E7%2590%2586%25E4%25B8%25AD%25E5%25AD%2598%25E5%259C%25A8%25E6%2580%25A7%25E9%2583%25A8%25E5%2588%2586%25E7%259A%2584%25E8%25AF%2581%25E6%2598%258E1.png
[2]: https://lh6.googleusercontent.com/-bOuhCnF0GW8/UpsRTom7e3I/AAAAAAAAAJg/DV025Nvojyk/w701-h399-no/Picard%E5%AE%9A%E7%90%86%E4%B8%AD%E5%AD%98%E5%9C%A8%E6%80%A7%E9%83%A8%E5%88%86%E7%9A%84%E8%AF%81%E6%98%8E2.png 
 
[3]: https://lh6.googleusercontent.com/-TcHtgBHQBOM/UptwvfqELbI/AAAAAAAAAKU/nI8T_-qotXg/w1044-h441-no/Picard%25E5%25AE%259A%25E7%2590%2586%25E4%25B8%25AD%25E5%25AD%2598%25E5%259C%25A8%25E9%2583%25A8%25E5%2588%2586%25E7%259A%2584%25E8%25AF%2581%25E6%2598%258E3.png 
 
[4]: https://lh3.googleusercontent.com/-BowAAP3C-K4/UpuAihquNQI/AAAAAAAAALQ/OHt8StnlFTs/w1044-h465-no/Picard%25E5%25AE%259A%25E7%2590%2586%25E4%25B8%25AD%25E5%25AD%2598%25E5%259C%25A8%25E6%2580%25A7%25E9%2583%25A8%25E5%2588%2586%25E7%259A%2584%25E8%25AF%2581%25E6%2598%258E+%25281%2529.png 
 
[5]: https://lh4.googleusercontent.com/-c0A49hXSa3E/Upx0PmSsbCI/AAAAAAAAAL4/kIL5WXHmXxo/w701-h416-no/Picard%E5%AE%9A%E7%90%86%E4%B8%AD%E5%AD%98%E5%9C%A8%E6%80%A7%E9%83%A8%E5%88%86%E7%9A%84%E8%AF%81%E6%98%8E4.png
 
利用Euler折线法证明存在唯一性定理,以及误差估计
=====================
 
在这篇文章里,笔者利用Euler折线法证明存在唯一性定理,并给出误差估计.
 
----------
 
为了内容连贯起见,我们将存在唯一性定理叙述如下: 
 
> 设初值问题: $$ (E):\frac{dy}{dx}=f(x,y),y(x_0)=y_0, $$ 其中 $f(x,y)$ 在带状区域 $[x_0,x_0+t]$ 内连续,而且对 $y$ 满足李普希兹条件.则 (E) 在该带状区域上有且只有一个解.
 
 
在正式进行严格证明之前,我们先用通俗的语言来描述一下证明的整体思路.
 
证明思路 
---------
我们考虑该问题的物理意义.物理意义是质点的一维运动.其中$x$是时间,$y$是位移.$f(x,y)$ 是速度.质点的速度随时间的函数是连续的.质点在时间$x_0$从点 $y_0$ 出发,初始速度为 $f(x_0,y_0)$.
 
-------------- 
在接下来很短的时间 $[x_0,x_0+\Delta x)$里,让质点以速度 $f(x_0,y_0)$ 进行匀速直线运动.当质点走完时间 $\Delta x$ 后,我们继续为这个质点分配同样短的一段时间 $\Delta x$,质点在接下来的时间段 $[x_0+\Delta x,x_0+2\Delta x)$ 内以速度 $f(x_0+\Delta x,y_0+f(x_0,y_0)\Delta x)$ 进行匀速直线运动…… 
 
就这样不断地为质点分配相同短的运动时间 $\Delta x$,在每段很短的时间里,质点的运动都为匀速直线运动,且速度为质点在该段时间初始的速度.这样从总体上看来,质点就存在了一种折线运动方式. 以质点的位置为纵坐标,时间为横坐标,我们可以画出质点的 时间-位置 图像,以此来描述质点的运动.如图,我们发现每段时间为 $\Delta x$ 的时候,质点的运动从整体上呈现出一条折线. 
 
 
![图像1][1] 
 
 
易得,每给定一个 $\Delta x$,质点就存在唯一的一个相应运动方式.现在,我们将每小段的时间 $\Delta x$ 减半,变成 $\frac{\Delta x}{2}$,则质点的运动将呈现出如下图中虚线的状态: ![图像2][2] 

以此类推,可见,当我们不断地将质点的匀速运动时间 $\Delta x$ 二等分,质点的运动将会越来越精细.现在我们来看序列 $$ \Delta x,\frac{\Delta x}{2},\frac{\Delta x}{4},\cdots,\frac{\Delta x}{2^n},\cdots $$ 该序列中的每一个数都对应着质点的唯一一种折线运动状态.质点的每个运动状态都是质点的位置关于时间的函数,因此上面的序列依次对应一列函数 $$ f_1(x),f_2(x),\cdots,f_n(x),\cdots $$ 由于在微分方程 $\frac{dy}{dx}=f(x,y)$ 中质点的运动速度是时间的连续函数,因此当 $n$ 足够大时,质点在相邻时间段内的运动发生的偏折不会太大,也即在相邻时间段,质点的速度的差距不会太大.更精确地来讲,对于任意给定的正实数 $\varepsilon$,都存在相应的正整数 $N$,使得对于一切 $n>N$,当质点按照数 $\frac{\Delta x}{2^n}$ 对应的运动方式进行折线运动时,对于任意两个相邻的时间段来说,质点的速度差都会控制在 $\varepsilon$ 以内.这根据闭区间上的连续函数一致连续是很容易证明的. 
 
现在,我们证明,当 $n\to\infty$ 时,数 $\frac{\Delta x}{2^n}$ 对应的运动方式存在,且此时很可能已经不再是折线运动,而可能是一条光滑的曲线.更加详细地说,我们要证明的是,函数列 $$ f_1(x),f_2(x),\cdots,f_n(x) $$ 一致收敛于某个函数 $f(x)$.
 
------------------------ 
 
我们来看数 $\frac{\Delta x}{2^n}$ 对应的质点折线运动路径和 $\frac{\Delta x}{2^{n+1}}$ 对应的质点折线运动路径.在时间 $[x_0,x_0+\frac{\Delta x}{2^{n+1}}]$ 里,两种运动方式完全重合,因此没有造成路程差. 在时间 $[x_0+\frac{\Delta x}{2^{n+1}},x_0+2\frac{\Delta x}{2^{n+1}}]$里,两种运动方式有可能造成距离差异.不妨设此时数 $\frac{\Delta x}{2^{n+1}}$ 对应的运动方式在时间 $[x_0+\frac{\Delta x}{2^{n+1}},x_0+2\frac{\Delta x}{2^{n+1}}]$ 与数 $\frac{\Delta x}{2^n}$ 对应的运动方式造成了距离 $G$.然后在时间段 $[x_0+2\frac{\Delta x}{2^{n+1}},x_0+3\frac{\Delta x}{2^{n+1}}]$ 里,根据 Lipchitz条件,我们知道,两种运动方式速度顶多相差 $Gh$,其中 $h$ 是某个固定常数.因此两种运动方式在经过了时间段 $[x_0+2\frac{\Delta x}{2^{n+1}},x_0+3\frac{\Delta x}{2^{n+1}}]$ 后的总路程差至多为 $$ G+Gh\frac{\Delta x}{2^{n+1}}. $$ 然后质点继续在时间段 $[x_0+3\frac{\Delta x}{2^{n+1}},x_0+4\frac{\Delta x}{2^{n+1}}]$ 里运动.由于当 $n$ 足够大时,质点在每个相邻的时间段内速度差都会足够小,不妨设 $n>N$,且质点在每个相邻时间段内的速度差都小于 $\varepsilon(n)$(这是由速度的连续性保证的,闭区间上的连续函数一致连续).则质点在经过时间段 $[x_0+3\frac{\Delta x}{2^{n+1}},x_0+4\frac{\Delta x}{2^{n+1}}]$ 后,两种运动方式造成的总路程差至多为 $$ G+Gh\frac{\Delta x}{2^{n+1}}+(Gh+\varepsilon(n))\frac{\Delta x}{2^{n+1}}. $$ 然后,质点继续运动,开始经历时间段 $[x_0+4\frac{\Delta x}{2^{n+1}},x_0+5\frac{\Delta x}{2^{n+1}}]$,在这段时间里,根据 Lipchitz条件,质点按照两种运动方式最大的速度差为 $$ (G+Gh\frac{\Delta x}{2^{n+1}}+(Gh+\varepsilon(n))\frac{\Delta x}{2^{n+1}})h, $$ 因此质点在经过时间段$[x_0+4\frac{\Delta x}{2^{n+1}},x_0+5\frac{\Delta x}{2^{n+1}}]$后,按照两种运动方式造成的总路程差最大为 $$ G+Gh\frac{\Delta x}{2^{n+1}}+(Gh+\varepsilon(n))\frac{\Delta x}{2^{n+1}}+(G+Gh\frac{\Delta x}{2^{n+1}}+(Gh+\varepsilon(n))\frac{\Delta x}{2^{n+1}})h\frac{\Delta x}{2^{n+1}}. $$ $$ \vdots $$ 然后就这样不断地迭代下去.这真是有点复杂啊,我得整理一下. 我们面对的是这样的情形,首先,我们有一个数 $G$,然后将 $G$ 经过函数 $T$ 的作用变成 $$ G+Gh\frac{\Delta x}{2^{n+1}}+(Gh+\varepsilon(n))\frac{\Delta x}{2^{n+1}}, $$ 也即, $$ T(G)=G+Gh\frac{\Delta x}{2^{n+1}}+(Gh+\varepsilon(n))\frac{\Delta x}{2^{n+1}}. $$ 然后不断迭代 $$ T^{(k)}(G)=T(T(T(T(T(\cdots T(G)))))). $$ 这里迭代了 $k$ 次.我们将 $T(G)$ 整理成 $$ T(G)=G+Gh\frac{\Delta x}{2^{n}}+\frac{\varepsilon(n)\Delta x}{2^{n+1}}. $$ 其中 $h,\Delta x,\varepsilon(n),n$ 都给定.我们来看迭代足够多次后,$T^{(2^n)}(G)$ 会不会趋于无界.为此我们准备求出 $T^{(2^n)}(G)$ 的表达式.令 $1+h\frac{\Delta x}{2^n}=P,\frac{\varepsilon(n)\Delta x}{2^{n+1}}=Q$,易得 \begin{equation} T^{(2^n)}(G)=P^{2^n+1}G+P^ {2^n}Q+\cdots+PQ+Q=P^{2^n+1}G+Q(\frac{1-P^{2^n+2}}{1-P}). \end{equation} 下面我们来看 $P^{2^n}$,易得 $$ \lim_{n\to\infty}P^{2^n}=\lim_{n\to\infty}(1+\frac{h\Delta x}{2^n})^{2^n}=e^{h\Delta x}. $$ 因此可得 $$ \lim_{n\to\infty}T^{(2^n)}(G)=Pe^{h\Delta x}G+Q(\frac{1-P^2e^{h\Delta x}}{1-P})=\lim_{n\to\infty}(e^{h\Delta x}G+\frac{\varepsilon(n)}{2}(e^{h\Delta x}-1))=0. $$ 不过,证到这里,并没有结束.我们发现我们的证明方向出现了偏差．到目前为止,其实我们只是证明了当 $\Delta x$ 给定,且 $n$ 无论多大的时候,质点按照数 $\frac{\Delta x}{2^n}$ 和 $\frac{\Delta x}{2^{n+1}}$两种运动方式走完 $[x_0,x_0+\Delta x]$ 这段时间所造成的路程差都是有界的,且当 $n\to\infty$ 时 , 造成的路程差也趋于0.光凭这一点,还不能判断质点所有的路径最后会一致收敛于某条较为光滑的路径.虽然如此,我们仍然可以继续做下去. 我们已经知道, \begin{equation} T^{(2^n)}(G)=P^{2^n+1}G+P^ {2^n}Q+\cdots+PQ+Q=P^{2^n+1}G+Q(\frac{1-P^{2^n+2}}{1-P}). \end{equation} 将其化简,可得 $$ T^{2^n}(G)=P^{2^n+1}G+\frac{\varepsilon(n)}{2h}(P^{2^n+2}-1)\leq P^{2^n+1}\frac{\varepsilon(n)\Delta x}{2^{n+1}}+\frac{\varepsilon}{2h}(P^{2^n+2}-1) $$ 易得 $$ \limsup_{n\to\infty}\varepsilon(n) \leq \frac{U(n)}{2^n}, 其中 U 是某个关于 n 的有界函数.$$ 
因此
$$
T^{(2^n)}(G)\leq P^{2^n+1}\frac{\varepsilon(n)\Delta x}{2^{n+1}}+\frac{U(n)}{2^{n+1}h}(P^{2^n+2}-1)
$$
因此对于任意给定的正实数 $\delta$,都存在相应的足够大的正整数 $N$,使得对于任意的 $m,n > N $ , 当 质点按照数 $\frac{\Delta x}{2^m}$ 和数 $\frac{\Delta x}{2^n}$ 对应 的运动方式运动时,两种运动方式在时间 $[x_0,x_0+\Delta x]$造成的 路程 差 会小于 $\delta$.因此
$$
f_1(x),f_2(x),\cdots,f_n(x),\cdots
$$
一致收敛于某函数 $f(x)$.
$\Box$
