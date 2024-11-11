---
up: 
aliases: 
tags:
  - econometrics
  - example
---

Let $\{ X_{n} \},\ \{ Y_{n} \}$, $X$ and $Y$ be random variables distributed, 
$$
\begin{pmatrix}
X_{n} \\
Y_{n} 
\end{pmatrix}
\overset{iid}{\sim} \mathcal{N}
\left( \begin{pmatrix}
0 \\
0
\end{pmatrix},\  
\begin{pmatrix}
1 & \rho \\
\rho & 1
\end{pmatrix}
\right) \ \text{and}\ 
\begin{pmatrix}
X \\
Y
\end{pmatrix}
\sim \mathcal{N}\left( 
\begin{pmatrix}
0 \\
0
\end{pmatrix}, 
\begin{pmatrix}
1 & r \\
r & 1
\end{pmatrix}
\right) 
$$
The marginal distributions of $X_{n},\ Y_{n}$, $X$ and $Y$ are all $\mathcal{N}(0,1)$. Hence (trivially), we have that $X_{n}\xrightarrow{d} X$ and $Y_{n}\xrightarrow{d} Y$. But, 
$$
X_{n} + Y_{n} \sim N(0, 2(1+\rho)) \text{ and }X + Y \sim \mathcal{N}(0, 2(1+r))
$$
So it is generally not the case that $X_{n} + Y_{n}\xrightarrow{d}X+Y!$ 

The reason for this is that, although the marginal distributions converge weakly, the joint distribution does not, as evidenced by the fact that $\rho$ may differ from $r$. 

Note however, if $X_{n},\ Y_{n}$ are **Independent** then we have that $\rho =0$ and also $X$ and $Y$ are independent with $r=0$. Then, in this case, we do have that $X_{n} + Y_{n}\xrightarrow{d} X+ Y$. 

This is true in general, since then
$$
\phi_{X_{n}+Y_{n}}(t) = \phi_{X_{n}}(t)\phi_{Y_{n}}(t)\to \phi_{X}(t)\phi_{Y}(t) = \phi_{X+Y}(t)
$$
whence $X_{n}+Y_{n}\xrightarrow{d}X+Y$ follows by [[Levy's Continuity Theorem]]

