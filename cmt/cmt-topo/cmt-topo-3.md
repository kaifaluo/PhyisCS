---
description: 什么？电容电感可以焊出一个拓扑绝缘体？
---

# 拓扑电路

> 创建: 2017/11/05-v1; 2020/03/03-v2

## 基尔霍夫定律

由基尔霍夫电流定律，无源和漏的结点上输入输出电流之和一定为零，对应电荷守恒定律。考虑LC电路，记电容上的电压降为$$U_i$$，电感上的电压降为$$U_j$$，有

$$
\sum_{i}I_{i}+\sum_{j}I_{j}=\sum_{i}C\dot{U}_{i}+\sum_{j}L\int U_{j}dt=0
$$

对时间求导得:

$$
\sum_{i}C\ddot{U}_i+\sum_{j}LU_j=0
$$

其中$$C,L$$为电容和电感，$$U$$为电压(电势差)。把每个附有三个电容的灰色三角$(m,n)$视为一个整体，其三个顶点上的电势对应三个自由度，用有三个分量的一维矢量$$\vec{\phi}_{m,n}=\left(\phi^{(0)}_{m,n},\phi^{(1)}_{m,n},\phi^{(2)}_{m,n}\right)^{T}$$表征(0,1,2的顺序参见FIG.1a).每个矢量内部分量之间由电容值为1/3(这里把量纲全部取为1)的电容连接，根据基尔霍夫电压定律，可以写出onsite interactive matrix：

$$
C_0=\frac{1}{3}
\begin{pmatrix}
    2 & -1 & -1 \\ -1 &2 &-1\\-1 &-1& 2\\
\end{pmatrix}
$$

相邻的灰色三角之间由电感值为1（量纲同样取为1）的电感相连，在m方向连接方式有且仅有一种，即$$\vec{\phi}_{m,n}$$与$$\vec{\phi}_{m+1,n}$$的三个分量按上标各自相连，intersite interactive矩阵可以写为

$$
V_x=
\begin{pmatrix}
    1 & 0 & 0 \\ 0 &1 &0\\0 &0& 1
\end{pmatrix}=\mathbb{I}_3
$$

在n方向上如FIG.1a所示有三种连接方式，从左往右分别可以写成

$$
V_{y1}=
    \begin{pmatrix}
    0 & 0 & 1 \\ 1 & 0 &0\\0 &1& 0
    \end{pmatrix},~~
V_{y2}=
    \begin{pmatrix}
    1 & 0 & 0 \\ 0 & 1 &0\\0 &0& 1
    \end{pmatrix},~~
V_{y3}=
    \begin{pmatrix}
    0 & 1 & 0 \\ 0 & 0 &1\\1 & 0 & 0
    \end{pmatrix}
$$

由于文中选择的特定连接方式，这三个矩阵基于矩阵乘法形成群：$$V_{y1}=V_{y3}^2=V_{y3}^{T}$$, $$V_{y2}=V_{y3}^3=\mathbb{I}_3$$。它们 构成$$C_{3}$$循环群的表示矩阵，只需取一个生成元$$V_y\equiv V_{y3}$$即可，也就是文中图FIG.1(a)中所示$$\vec{\phi}_{m,n}$$和$$\vec{\phi}_{m,n+1}$$之间的电感连接矩阵。

## 运动方程EOM

现在，我们从电路恒满足的EOM出发

$$
\sum_{i}C\ddot{U}_i+\sum_{j}LU_j=0
$$

$$i$$可以取(0,1,2)，对应每个灰色三角的三个顶点，$$j$$可以取(1,2,3,4)，对应每个三角的4个最近邻三角。现在考虑FIG.1a标记的那个$$\vec{\phi}_{m,n}$$，其顶点标记为0的电路网络方程为

$$
\begin{aligned}
&C_{01}\frac{d^2}{dt^2}\left(\phi_{m,n}^{(0)}-\phi_{m,n}^{(1)}\right)+C_{02}\frac{d^2}{dt^2}\left(\phi_{m,n}^{(0)}-\phi_{m,n}^{(2)}\right)\\
+&V_{x00}\left(\phi_{m,n}^{(0)}-\phi_{m+1,n}^{(0)}\right)+V_{x00}\left(\phi_{m,n}^{(0)}-\phi_{m-1,n}^{(0)}\right)\\
+&V_{y01}\left(\phi_{m,n}^{(0)}-\phi_{m,n+1}^{(1)}\right)+V_{y02}\left(\phi_{m,n}^{(0)}-\phi_{m,n-1}^{(2)}\right)=0
\end{aligned}
$$

稍加整理得：

$$
\begin{aligned}
&(C_{01}+C_{02})\ddot{\phi}_{m,n}^{(0)}-C_{01}\ddot{\phi}_{m,n}^{(1)}-C_{02}\ddot{\phi}_{m,n}^{(2)}\\
+&\left(V_{x00}+V_{x00}+V_{y01}+V_{y02}\right)\phi_{m,n}^{(0)}\\
-&V_{x00}\phi_{m+1,n}^{(0)}-V_{x00}\phi_{m-1,n}^{(0)}-V_{y01}\phi_{m,n+1}^{(1)}-V_{y02}\phi_{m,n-1}^{(2)}=0
\end{aligned}
$$

注意：由于这里把所有的电感全部取为1，所以$$V_{x00}+V_{x00}+V_{y01}+V_{y02}=4$$。同样地，对另外两个顶点也有：

$$
\begin{aligned}
&(C_{10}+C_{12})\ddot{\phi}_{m,n}^{(1)}-C_{10}\ddot{\phi}_{m,n}^{(0)}-C_{12}\ddot{\phi}_{m,n}^{(2)}\\
+&\left(V_{x11}+V_{x11}+V_{y12}+V_{y10}\right)\phi_{m,n}^{(1)}\\
-&V_{x11}\phi_{m+1,n}^{(1)}-V_{x11}\phi_{m-1,n}^{(1)}-V_{y12}\phi_{m,n+1}^{(2)}-V_{y10}\phi_{m,n-1}^{(0)}=0
\end{aligned}
$$

$$
\begin{aligned}
&(C_{20}+C_{21})\ddot{\phi}_{m,n}^{(2)}-C_{20}\ddot{\phi}_{m,n}^{(0)}-C_{21}\ddot{\phi}_{m,n}^{(1)}\\
+&\left(V_{x22}+V_{x22}+V_{y20}+V_{y21}\right)\phi_{m,n}^{(2)}\\
-&V_{x22}\phi_{m+1,n}^{(2)}-V_{x22}\phi_{m-1,n}^{(2)}-V_{y20}\phi_{m,n+1}^{(0)}-V_{y21}\phi_{m,n-1}^{(1)}=0
\end{aligned}
$$

同样有：

$$
\begin{aligned}
&V_{x11}+V_{x11}+V_{y12}+V_{y10}=4\\
&V_{x22}+V_{x22}+V_{y20}+V_{y21}=4\\
\end{aligned}
$$

简写成矩阵形式后即：

$$
C_0\ddot{\vec{\phi}}_{m,n}+4\vec{\phi}_{m,n}-
\left(V_x\vec{\phi}_{m+1,n}+V_x\vec{\phi}_{m-1,n}+V_y\vec{\phi}_{m,n+1}+V_y^T\vec{\phi}_{m,n-1}\right)=0
$$

或移项写成：

$$
C_0\ddot{\vec{\phi}}_{m,n}=-4\vec{\phi}_{m,n}+
\left(V_x\vec{\phi}_{m+1,n}+V_x\vec{\phi}_{m-1,n}+V_y\vec{\phi}_{m,n+1}+V_y^T\vec{\phi}_{m,n-1}\right)
$$

按照同样的步骤，可以写出原胞内其它两个灰色三角的运动方程：

$$
C_0\ddot{\vec{\phi}}_{m-2,n}=-4\vec{\phi}_{m-2,n}+
\left(V_x\vec{\phi}_{m-1,n}+V_x\vec{\phi}_{m-3,n}+(V_y)^2\vec{\phi}_{m-2,n+1}+(V_y^T)^2\vec{\phi}_{m-2,n-1}\right)
$$

$$
C_0\ddot{\vec{\phi}}_{m-1,n}=-4\vec{\phi}_{m-1,n}+
\left(V_x\vec{\phi}_{m,n}+V_x\vec{\phi}_{m-2,n}+(V_y)^3\vec{\phi}_{m-1,n+1}+(V_y^T)^3\vec{\phi}_{m-1,n-1}\right)
$$

需要注意的是，文中(2)式其实是三个式子，因为在(2)中我们已经看到，矩阵$$V_y$$可以生成一个阶数为3的循环群，所以(2)式中出现的$$(V_y)^m$$在对$$m$$模3后，可得一个原胞内三个灰色三角的运动方程。 为形式简洁起见，如果我们记原胞内从左往右第三个灰色三角的脚标$$m(mod~3)=1$$，那么上述三个运动方程可以合写成文中(2)式的形式：

$$
C_0\ddot{\vec{\phi}}_{m,n}
=-4\vec{\phi}_{m,n}+
\left(V_x\vec{\phi}_{m+1,n}+V_x\vec{\phi}_{m-1,n}+(V_y)^{m}\vec{\phi}_{m,n+1}+(V_y^T)^{m}\vec{\phi}_{m,n-1}\right)
$$

## 线性变换

考虑到由于$$V_y$$的存在，$$\vec{\phi}_{m,n}$$的三个自由度耦合在一起，类似于经典力学中寻找简正坐标的做法，通过坐标变换，寻找这三个自由度的独立运动方程。由于耦合项源于$$V_y$$，只需要做线性变换，得到$$V_y$$为对角阵的表象即可。 求解$$V_y$$的本征值方程易得：

$$
V_y=T\Lambda T^{-1}
$$

其中

$$
T=\frac{1}{\sqrt{3}}\begin{pmatrix}
1& 1 &1\\1&e^{i2\pi/3}&e^{i4\pi/3}\\1&e^{-i2\pi/3}&e^{-i4\pi/3}
\end{pmatrix},~~
\widetilde{V}_y\equiv\Lambda=\begin{pmatrix}
1&0&0\\0&e^{i2\pi/3}&0\\0&0&e^{-i2\pi/3}
\end{pmatrix}
$$

接下来依次对$$C_0,V_x$$和$$\vec{\phi}_{m,n}$$进行线性变换，并采用张量的指标记法和爱因斯坦求和约定：

$$
\begin{aligned}
&\widetilde{C}_0=T^{-1}C_0T=diag(0,1,1)\\
&\widetilde{V}_x=T^{-1}V_xT=T^{-1}\mathbb{I}_3T=\mathbb{I}_3\\
&\vec{\xi}_{m,n}=T\vec{\phi}_{m,n}\equiv T_{\mu\nu}\phi_{m,n}^{(\nu)}=\frac{1}{\sqrt{3}}e^{i(2\pi/3)\mu\nu}\phi_{m,n}^{(\nu)}(\mu,\nu=0,1,2)
\end{aligned}
$$

到这里可以看出，由于矩阵$$\widetilde{C}_0,\widetilde{V}_x$$均为对角阵，$$\xi^{(i)}(i=0,1,2)$$对应的运动方程自然也就各自独立，于是就得到(3)式。

$$
\widetilde{C}_0\ddot{\vec{\xi}}_{m,n}=-4\vec{\xi}_{m,n}+
\left(\widetilde V_x\vec{\xi}_{m+1,n}+\widetilde V_x\vec{\xi}_{m-1,n}+(\widetilde V_y)^{m}\vec{\xi}_{m,n+1}+(\widetilde  V_y^T)^{m}\vec{\xi}_{m,n-1}\right)
$$

拆开成三个运动方程为：

$$$
\begin{aligned}
&0=-4\xi^{(0)}_{m-2,n}+\xi^{(0)}_{m-1,n}+\xi^{(0)}_{m-3,n}+\xi^{(0)}_{m-2,n+1}+\xi^{(0)}_{m-2,n-1}\\
&$$\ddot{\xi}_{m-1,n}^{(1)}=-4\xi^{(1)}_{m-1,n}+\xi^{(1)}_{m,n}+\xi^{(1)}_{m-2,n}+e^{i2\pi/3}\xi^{(1)}_{m-1,n+1}+e^{-i2\pi/3}\xi^{(1)}_{m-1,n-1}\\
&\ddot{\xi}_{m,n}^{(2)}=-4\xi^{(2)}_{m,n}+\xi^{(2)}_{m+1,n}+\xi^{(2)}_{m-1,n}+e^{i4\pi/3}\xi^{(2)}_{m,n+1}+e^{-i4\pi/3}\xi^{(2)}_{m,n-1}
\end{aligned}
$$$

* 正是$$V_y$$中非对角元的存在，导致坐标变换后，在新的坐标$$\vec{\xi}$$上引入了相位项;
* 由于这三个自由度相互独立，可以直接将它们所在的子空间正交分解$$\widetilde{\Omega}^2=\oplus_{\mu}\widetilde{\Omega}^2_{\mu}~(\mu=0,1,2)$$, 这里的平方是由于哈密顿量对应的本征值为频率的平方;
* 由于$$\widetilde{C}_0$$的第一个对角元为0，容易发现$$\xi^{(0)}$$对应的运动方程是一个代数方程，表明它的电势分布是一个常值函数。$$\xi^{(1,2)}$$的运动方程则是微分方程，刚好对应着赝自旋向上和赝自旋向下的两个自由度，各自均为加了等效通量的Hofstadter model，共同构成一个Time Reversal Invariant Double-Hofstadter model.这里实际上联系了$$C_{3}$$循环群和阿贝尔规范势。

## 一般的谐振子系统

考虑到这里的LC网络的电势分布函数由二阶常微分方程组描述，上述分析对一般的耦合谐振子系统都应当是适用的，只要自由度之间的耦合可以实现。例如弹簧-质点网络(Spring-mass network)，从牛顿第二定律出发

$$
M\ddot{\vec{x}}+\nabla V=0
$$

其中$$M$$为质量，$$V$$为质点所处场中的势能。于是有如下对应关系：

$$
\begin{aligned}
M(mass)&\leftrightarrow C(capacitance)\\
\vec{x}&\leftrightarrow U\\
\nabla V&\leftrightarrow LU
\end{aligned}
$$
