# WKB近似量子作业

物理二班 魏弘量

320180934321

## 1.

![image-20200621201500798](C:\Users\QQ\AppData\Roaming\Typora\typora-user-images\image-20200621201500798.png)

要解决这个问题，首先我们需要找到由特定势函数确定允许能量值的公式。在维基百科上，我们可以查看到：

![image-20200621201634635](C:\Users\QQ\AppData\Roaming\Typora\typora-user-images\image-20200621201634635.png)

![image-20200621201702226](C:\Users\QQ\AppData\Roaming\Typora\typora-user-images\image-20200621201702226.png)

![image-20200621201723960](C:\Users\QQ\AppData\Roaming\Typora\typora-user-images\image-20200621201723960.png)

![image-20200621201743452](C:\Users\QQ\AppData\Roaming\Typora\typora-user-images\image-20200621201743452.png)

![image-20200621201801839](C:\Users\QQ\AppData\Roaming\Typora\typora-user-images\image-20200621201801839.png)

![image-20200621201830433](C:\Users\QQ\AppData\Roaming\Typora\typora-user-images\image-20200621201830433.png)

![image-20200621201849054](C:\Users\QQ\AppData\Roaming\Typora\typora-user-images\image-20200621201849054.png)

通过以上这些步骤，我们得到量子化规则确定的允许能量值。

在我们今天这个问题里，
$$
\int_{0}^{a} p(x) d x=\sqrt{2 m E}\left(\frac{a}{2}\right)+\sqrt{2 m\left(E-V_{0}\right)}\left(\frac{a}{2}\right)=\sqrt{2 m}\left(\frac{a}{2}\right)(\sqrt{E}+\sqrt{E-V_{0}})=n \pi \hbar
$$
故，
$$
E+E-V_{0}+2 \sqrt{E\left(E-V_{0}\right)}=\frac{4}{2 m}\left(\frac{n \pi \hbar}{a}\right)^{2}=4 E_{n}^{0} ; \quad 2 \sqrt{E\left(E-V_{0}\right)}=\left(4 E_{n}^{0}-2 E+V_{0}\right)
$$
得，
$$
16 E E_{n}^{0}=16 E_{n}^{0^{2}}+8 E_{n}^{0} V_{0}+V_{0}^{2}
$$
得，
$$
E_{n}=E_{n}^{0}+\frac{V_{0}}{2}+\frac{V_{0}^{2}}{16 E_{n}^{0}}
$$

## 2.

![image-20200621202247621](C:\Users\QQ\AppData\Roaming\Typora\typora-user-images\image-20200621202247621.png)

我不会做。

但是我知道大概思路是求波函数透射率。在维基百科上可以查看到：

![image-20200621202511311](C:\Users\QQ\AppData\Roaming\Typora\typora-user-images\image-20200621202511311.png)

![image-20200621202522990](C:\Users\QQ\AppData\Roaming\Typora\typora-user-images\image-20200621202522990.png)

所以原则上我们可以求透射率（但是实际我不会算那个数）。

## 3.

![image-20200621202640694](C:\Users\QQ\AppData\Roaming\Typora\typora-user-images\image-20200621202640694.png)

这道题是我三道题之中最懂的一道。好简单，跟第一道题类似。运用公式：
$$
\int_{x_{1}}^{x_{2}} p(x) d x=(n-1 / 2) \pi \hbar, \quad n=1,2,3, \ldots
$$
假设经典限制点是$x_t$，那么：
$$
E=\frac{1}{2} m \omega^{2} x_{t}^{2}
$$

$$
x_{t}=\pm \sqrt{\frac{2 E}{m \omega^{2}}}
$$
粒子的动量是：
$$
p(x)=\sqrt{2 m\left(E-\frac{1}{2} m \omega^{2} x^{2}\right)}
$$
代入允许能量公式：
$$
\int_{-2 E / m \omega^{2}}^{2 E / m \omega^{2}} \sqrt{2 m\left(E-\frac{1}{2} m \omega^{2} x^{2}\right)} d x=(n-1 / 2) \pi \hbar, \quad n=1,2,3, \ldots
$$
积分出来得到：
$$
E_{n}=(n-1 / 2) \omega \hbar, \quad n=1,2,3, \dots
$$
恰好与严格解一致。