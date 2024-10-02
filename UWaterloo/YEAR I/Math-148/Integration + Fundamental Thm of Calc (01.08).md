
![[Pasted image 20240108121000.png]]

Consider function
A(x) = Area enclosed above
	= -ln(1-x)

Why?

<i>Step 1</i>
$$\begin{align} 
A'(x) &= \frac{1}{1-x} \\
A(0) &= 0
\end{align}$$ 0 < x < 1

![[Pasted image 20240108121359.png]]

Some caveats to this approach:
1. Definition of area?
2. Why A' exists?

Nonetheless, assume this, we know A(x) and $-ln(1-x)$ both solves
$$\begin{align}
F' &= \frac{1}{1-x} \\
F(0) &= 0
\end{align}
$$

Hence $$\begin{align}
(A- (-ln(1-x)))' = 0 \\
A(0) - (-ln(1-x)) = 0 \\
\implies A = -ln(1-x)
\end{align}$$


# Intro to ODE

$$\begin{align}
y = \frac{1}{1-x}\ near\ x=0 ?
\end{align}$$
$$\begin{align}
&y(1-x) = 1 \\
&\implies y'(1-x) - y=0 \ \& \ y(0)=1 \\
&\implies  y' - y^{2}= 0 \ \& \ y(0)=1
\end{align}$$
$$\begin{align}
y'-y^{2}&= 0 \\
& \implies \frac{dx}{dy}= \frac{1}{y^{2}}\\
& \implies x = \frac{-1}{y}+C \\ 
& \implies 0 = -1+C \ \text{(since x(1)=0)} \\
& \implies x = - \frac{1}{y}+1
\end{align}$$

![[Pasted image 20240108123354.png]]



# $\frac{1}{1-x}$ in taylor series & more

![[Pasted image 20240108123503.png]]
![[Pasted image 20240108123638.png]]
![[Pasted image 20240108123709.png]]




