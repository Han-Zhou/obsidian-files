
### Sequences

A sequence of $R$ is a function 
$$ \begin{gather} 
f:\mathbb{N} \rightarrow R \\
a_n = f(n) \ for \ each \ n=1,2,3,...
\\
\\
\{ a_1,a_2,... \} \qquad or \ \{ a_n \}_{n=0 } ^\infty \qquad or \ {a_n} 
\end{gather}$$

#### Examples:
![[Pasted image 20230929122502.png]]

### Limits

#### Definition
Let $\{ a_n \}$ be a sequence of reals;

$L \in \mathbb{R}$ is called the limit of the sequence $\{ a_n \}$ :
$$ \begin{align*}
if \qquad \forall  \varepsilon>0, \ \exists N \in \mathbb{N}, \ so \ that \\
|a_n-L|  <  \varepsilon \qquad & for \ n \ge N 
\end{align*} $$

If such limit exists, we say that $\{a_n\}$ is <u>convergent</u>;
If such limit doesn't exist, we say that $\{a_n\}$ is <u>divergent</u>

#### Proposition

If $\{a_n\}$ has limit then it's unique

Proof:
\[ \lim_{x \to 2} f(x) = 5 \]
let \ $\lim_{x \to \infty} a_n = L$ .


assume $\lim_{x \to \infty} a_n$ = $L_2$ s.t. $L_2=L1$

given  $\varepsilon > 0$,
$\qquad$ $\exists N_1 \in \mathbb{N} \ s.t. |a_n-L_1| < \frac{\varepsilon}{2}$
$\qquad \exists N_2 \in \mathbb{N} \ s.t. |a_n-L_2| < \frac{\varepsilon}{2}$

Consider
$\qquad |L_1 - L_2| = |L_1-a_n+a_n-L_2|$
By triangle inequality, [[Triangle Inequality]]
$\qquad \quad \le |L_1-a_n| + |a_n-L_2| \qquad \forall n \ge N$
(Take N:= $max \ \{N_1, N_2 \}$)
![[Pasted image 20230929173100.png]]





#### Examples

![[Pasted image 20230929123720.png]]

![[Pasted image 20230929123807.png]]



### Infinite limits

#### Definition

- $\{a_n \}$ diverges to $+ \infty$ ($\lim_{n \to \infty} a_n = + \infty$)
if $\forall M>0 \quad \exists N \in \mathbb{N} \qquad s.t. \ a_n > m \ \ \forall n \ge N$

- $\{a_n \}$ diverges to $- \infty$ ($\lim_{n \to \infty} a_n = - \infty$)
if $\forall M>0 \quad \exists N \in \mathbb{N} \qquad s.t. \ a_n < -m \ \ \forall n \ge N$

#### Example

![[Pasted image 20230929174952.png]]



### Limit rules

#### Prop:if has limit then bounded


if $\{a_n \}$ is bounded,
$\exists B>0 \qquad s.t. \ |a_n|<B \quad \forall n \in \mathbb{N}$

If $\lim a_n = L$ , then $\{a_n \}$ is bounded


##### Proof
![[Pasted image 20230929175459.png]]

##### Remarks
![[Pasted image 20230929175543.png]]

![[Pasted image 20230929175817.png]]


#### Theorems on limit calculations

##### Theorems
![[Pasted image 20230929175935.png]]
![[Pasted image 20230929175954.png]]

Thus all usual arithmetic rules hold for limits

##### Proof

(0 - 2), (5) in Forrest notes p106

(3)
![[Pasted image 20230929180119.png]]
![[Pasted image 20230929180142.png]]

(4)
![[Pasted image 20230929181016.png]]
![[Screenshot 2023-09-29 at 6.10.25 PM.png]]

##### Example
![[Pasted image 20230929181200.png]]



### Squeeze theorem

#### thm

Let $a_n \le b_n \le c_n$ for $n \in \mathbb{N}$ and
$$\lim_{n \to \infty} a_n = L = \lim_{n \to \infty} c_n$$
Then: $\{b_n\}$ is convergent and
$$\quad lim_{n \to \infty} b_n = L$$


#### Proof

![[Pasted image 20230929181745.png]]
![[Pasted image 20230929181809.png]]

