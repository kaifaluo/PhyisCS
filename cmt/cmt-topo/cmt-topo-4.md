---
description: 磁场下的拓扑材料。
---

# 磁场下的能谱

> 创建: 2019/06/15-v1; 2019/08/20-v2; 2020/05/03-v3

## 朗道量子化

朗道量子化指的是将正则动量算符替换成产生湮灭算符:

$$
P_{x,y}=\sqrt{\frac{\hbar eB}{2}}(a^{\dagger}\pm a),
$$

其中正则动量算符为$$\vec{P}=-i\hbar\nabla + e\vec{A}$$，或者用动量空间中的波矢$$\vec{k}=-i\nabla + e\vec{A}/\hbar$$来替换：

$$
k_{x,y}=\sqrt{\frac{eB}{2\hbar}}(a^{\dagger}\pm a),
$$

等价地有

$$
k_{+}=\sqrt{\frac{2eB}{\hbar}}a^{\dagger}=\frac{\sqrt{2}a^{\dagger}}{l_{B}},
$$

其中$$l_{B}=\sqrt{\hbar/eB}\approx 260/\sqrt{B}$$是系统的磁长度。在自然单位制$$c=\hbar=1$$下，有$k\_{+}=\sqrt{2B}a^{\dagger}$.

## 外尔半金属

从带正手性的理想外尔哈密顿量出发，在波函数基矢$$(|\alpha\rangle,|\beta\rangle)^{T}$$下的表示为

$$
\begin{equation}
\hat{H}_{W}=
\begin{pmatrix}k_{z}&k_{-}\\k_{+}&-k_{z}
\end{pmatrix}
\rightarrow
\hat{H}_{W}^{LL}(k_{z})=
\begin{pmatrix}k_{z}&\sqrt{B}a\\\dagger&-k_{z}\end{pmatrix}
\end{equation}
$$

其中$$k_{\pm}=k_{x}\pm ik_{y}$$。朗道量子化后的波函数基矢: $$(|\beta,0\rangle,|\alpha,0\rangle,|\beta,1\rangle,|\alpha,1\rangle,|\beta,2\rangle,\cdots,|\alpha,N\rangle)^{T} \equiv (|\beta,0\rangle,|\psi_{0}\rangle,|\psi_{1}\rangle,\cdots,|\alpha,N\rangle)^{T}$$

有磁哈密顿量的矩阵表示为

$$
H_{W}^{LL}(k_{z})=\begin{pmatrix}
-k_{z}& 0 &0&\cdots&0\\
&\langle \psi_{0}|\hat{H}|\psi_{0}\rangle&0& \cdots&0\\
&&\langle \psi_{1}|\hat{H}|\psi_{1}\rangle& \cdots&0\\
&\dagger&&\ddots&0\\
&&&&k_{z}\\
\end{pmatrix}
$$

其中

$$
\langle \psi_{n}|\hat{H}|\psi_{n}\rangle 
=\begin{pmatrix}k_{z}&\sqrt{B}\sqrt{n+1}\\\dagger&-k_{z}
\end{pmatrix}
$$

解得朗道能带为

$$
E_{\pm n}=\pm\sqrt{B(n+1)+k_{z}^{2}}~~(n\geqslant 0)
$$

## 三维绝缘体

### T+P+M

### 能带绝缘体

考虑一个最简单的三维能带绝缘体(band insulator)：

$$
H_{BI} = \left(m_{0}+m\vec{k}^{2}\right)\sigma_{z},
$$

其中价带底和导带顶能量$m\_{0}$和各向同性有效质量$m$均是正的。考虑在$z$方向加一个磁场$\vec{B}=(0,0,B)$，可得到磁哈密顿量为

$$
H_{BI,mag}=\left(m_{0}-m k_{z}^{2}-ma^{\dagger}a\right)\sigma_{z}
$$

可解出第$n$个朗道能带为

$$
E_{BI,mag,\pm n}=\pm\left|m_{0}-mk_{z}^{2}-mn\right|
$$

### 结球半金属

## 三维拓扑半金属

### 结环

考虑一个最简单的二能带结环半金属:

$$
\hat{H}_{NL}=\begin{pmatrix}k_{z}&m-(k_{x}^{2}+k_{y}^{2})\\ \dagger&-k_{z}\end{pmatrix}
=\begin{pmatrix}k_{z}&m-k_{+}k_{-}\\\dagger&-k_{z}\end{pmatrix}.
$$

### 结链

#### 垂直磁场

由磁哈密顿量

$$
\hat{H}_{NL,mag}(k_{z})=\begin{pmatrix}k_{z}&m-Ba^{\dagger}a\\\dagger&-k_{z}\end{pmatrix}
$$

可得表示矩阵

$$
\langle a,n|\hat{H}|a,n\rangle 
=\begin{pmatrix}
  k_{z}&m-Bn\\\dagger&-k_{z}
 \end{pmatrix}
$$

$$
H_{NL,mag}(k_{z})
=\begin{pmatrix}
    \langle \psi_{0}|\hat{H}|\psi_{0}\rangle&0& \cdots\\
    &\langle \psi_{1}|\hat{H}|\psi_{1}\rangle& \cdots\\
    \dagger&&\ddots\\
 \end{pmatrix}
$$

解得朗道能带为

$$
E_{n\pm n}=\pm\sqrt{\left(m-Bn\right)^{2}+k_{z}^{2}}~(n\geqslant 0)
$$

#### 面内磁场

$$
\hat{H}_{NL,mag}(k_{x})=\begin{pmatrix}\frac{\sqrt{B}}{\sqrt{2}i}(a^{\dagger}-a)&m-k_{x}^{2}-\frac{B}{2}(a^{\dagger}+a)^{2}\\\dagger&-\frac{\sqrt{B}}{\sqrt{2}i}(a^{\dagger}-a)\end{pmatrix}
$$

在朗道波函数基矢$$(|\alpha,0\rangle,|\beta,0\rangle,|\alpha,1\rangle,|\beta,1\rangle,\cdots)^{T} \equiv (|\psi_{0}\rangle,|\psi_{1}\rangle,\cdots)^{T}$$下可写出表示矩阵

$$
\begin{aligned}
&\langle\psi_{n}|\hat{H}|\psi_{n}\rangle 
  =\begin{pmatrix}0&m-k_{x}^{2}-\frac{B}{2}(2n+1)\\ \dagger&0
  \end{pmatrix}\\
&\langle\psi_{n}|\hat{H}|\psi_{n+1}\rangle 
  =\begin{pmatrix}-\frac{\sqrt{B}}{\sqrt{2}i}\sqrt{n+1}&0\\ 0&-\frac{\sqrt{B}}{\sqrt{2}i}\sqrt{n+1}
  \end{pmatrix}\\
&\langle\psi_{n}|\hat{H}|\psi_{n+2}\rangle 
  =\begin{pmatrix}0&-\frac{B}{2}\sqrt{(n+2)(n+1)}\\ -\frac{B}{2}\sqrt{(n+2)(n+1)}&0
  \end{pmatrix}\\
\end{aligned}
$$

当磁场足够强时，最低朗道能级与高朗道能级之间的能隙较大，在零阶近似下，取出最低朗道能级的二带哈密顿量

$$
H_{LL}^{(0)}(k_{x})
=\begin{pmatrix}0&m-k_{x}^{2}-\frac{B}{2}\\ \dagger&0
\end{pmatrix}
$$

在$$k_{x}=\pm Q$$附近进行小量展开:

$$
H_{LL}^{(0)}(\pm Q+\delta k_{x})
=\left[\left(m-\frac{B}{2}+Q^{2}\right)\mp 2Q\delta k_{x}\right]\sigma_{x}+O(\delta k_{x})
$$

得到低能哈密顿量

$$
H_{LL}^{Q}(\delta k_{x})\equiv \mp 2Q\delta k_{x}\sigma_{x}
$$

## 拓扑绝缘体

### 二维：T

### 三维：T+P

### 磁场

考虑由时间反演对称性保护的拓扑绝缘体

$$
H_{TI}=\sum_{i=1}^{3}k_{i}\Gamma_{i}+\left(m_{0}-m\vec{k}^{2}\right)\Gamma_{4}
$$
