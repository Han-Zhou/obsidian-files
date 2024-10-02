Solves recurrences of the form:  
$T(n) = aT(n/b) + f(n)$


## Theorem 4.1 (master theorem)
$a \geq 1, b > 1$ cosntants, $f(n)$ funtion,  
T(n) defined $T(n) = aT(n/b) + f(n)$,  
then T(n) has the folowing asysmptotic bounds:

1. :wIf $f(n) = O(n^{log_ba-\epsilon})$ for some constant $\epsilon > 0$, then $T(n) = \Theta(n^{log_ba})$
2. If $f(n) = \Theta(n^{log_ba})$, $T(n) = \Theta(n^{log_ba}lgn)$
3. If $f(c) = \Omega(n^{log_ba + \epsilon}))$, and if $af(n/b) \leq cf(n))$ for some constant c < 1 and all syfficiently large n, then $T(n) = \Theta(f(n))$.a


> Key: difference of $n^\epsilon$ is *polynomially* larger/smaller

Exists times when we cant use the master method to solv the recurrence





