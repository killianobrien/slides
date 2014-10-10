% 6G5Z3006_1314 \\\\ Number Theory & Cryptography
% Killian O'Brien
% October 2013

# NT&C \\\\ Integer divisibility (Ch. 2)

## NT&C \\\\ The Euclidean algorithm
Examining the working of the algorithm gives us the following result
$\newcommand{\lcm}{\mathrm{lcm}}$

### Theorem 2.5

If $m$ is a positive integer then 
$$
\gcd(ma,mb) = m \gcd(a,b),
$$
(where $a,b$  are not both zero).

*Proof*. This follows immediately from observing that the sequence of integer divisions that come about from applying the Euclidean Algorithm to the pair $ma,mb$ are simply the equations from applying the algorithm to the pair $a,b$, but multiplied through by $m$. For instance,
$$
\Big [ a=q_1 b + r_1, \, \, (0 \leq r_1 < b) \Big ] \, \Leftrightarrow
\, \Big [ma = q_1 mb + m r_1, \, \, (0 \leq m r_1 < mb) \Big ] .
$$

So if $\gcd(a,b) = r_n$, the final non-zero remainder, then $\gcd(ma,mb) = m r_n$, as required. $\square$

## NT&C \\\\ Least common multiple

Related to the concept of the greatest common divisor is that of the least common multiple. 

### Definition 2.6 (least common multiple)

Let $a,b \in \mathbb{Z}$ be both non-zero. The *least common multiple*, $\lcm(a,b)$, is the smallest positive integer that is a both a multiple of $a$ and a multiple of $b$.

There is a direct relationship between the greatest common divisor and the least common multiple of a pair of integers.

### Theorem 2.6

If $a,b \in \mathbb{Z}$ are both positive then 
$$
\gcd(a,b) \, \lcm(a,b) = ab.
$$

*Proof*. Let $d=\gcd(a,b)$. We prove the result directly by showing that the quantity $\frac{ab}{d}$ is equal to $\lcm(a,b)$.

Since $d$ divides $a$ and $b$ there exist $\alpha, \beta \in \mathbb{Z}$ such that 
$$
a= \alpha d , \, \, b = \beta d,
$$
and so 
$$
\frac{ab}{d} = \alpha b d= \beta a d.
$$
This shows that $\frac{ab}{d}$ is a positive common multiple of $a$ and $b$. Now we show it is the least such one. Suppose that $c$ is another common multiple of $a$ and $b$, say
$$
c = \lambda a = \mu b , \, \, (\lambda, \mu \in \mathbb{Z}).
$$
Now since $d=\gcd(a,b)$ we know there are $m,n \in \mathbb{Z}$ such that 
$$
d = ma + nb .
$$
Now we examine the quantity $c$ divided by the integer $\frac{ab}{d}$,
$$
\frac{c}{\frac{ab}{d}} = \frac{cd}{ab} = \frac{c (ma + nb)}{ab} 
= \frac{c}{b} m + \frac{c}{a} n = \mu m + \lambda n .
$$
This last expression shows that $c$ divided by the integer $\frac{ab}{d}$ , is an integer, or in other words, $\frac{ab}{d}$ divides $c$ and hence $\frac{ab}{d} \leq c$ as required.  $\square$

\begin{exer}
Here are some questions to help you practice using the Euclidean Algorithm. You should complete these and others until you are confident in using it to find both the gcd and a linear combination for the gcd. It is good practice to make a few notes as you go emphasizing how the pairs we apply the integer division process to all have the same gcd, by lemma \ref{L:eucalg}.
\begin{enumerate}
\item
Use the Euclidean algorithm to find $\gcd(143,227)$, $\gcd(306,657)$ and $\gcd(272,1479)$.
\item
Find integers $m,n$ that satisfy the following equations,
	\begin{enumerate}
	\item
	$\gcd(56,72) = 56 m + 72 n$,
	\item
	$\gcd(24,138) = 24m + 138n$,
	\item
	$\gcd(119, 272) = 119 m + 272 n$,
	\item
	$\gcd(1769, 2378) = 1769 m + 2378 n$.
	\end{enumerate}
\end{enumerate}
\end{exer}

## NT&C \\ Extending GCD

The concept of greatest common divisors extends to sets of three or more integers without difficulty. The Euclidean Algorithm can still be applied to find the gcd in these cases. This is done by finding the gcd of pairs of integers at a time and using results like the following (quoted for the triple of integers case).

### Theorem 2.7 (Greatest common divisor of three integers)
Let $d = \gcd(a,b,c)$ have the obvious definition. Then 
$$
d = \gcd \big( \gcd(a,b), c \big ) = \gcd \big( \gcd(a,c), b \big )
=\gcd \big( \gcd(b,c), a \big ).
$$
*Proof*. Exercise.


<!--- 
 <div class="compute"><script type="text/x-sage"><div class="compute"><script type="text/x-sage">
@interact
def tline(ep=slider(0.0001,4,0.1,0)):
          p=plot(sin(x), (x, 0, 2*pi));
          a=pi/2;
          u=a+ep;
          slope=(sin(u)-sin(a))/(u-a);
          q=plot(slope*(x-pi/2)+sin(pi/2), (x,0,2*pi), color='red');
          (p+q).show();
</script></div> </script></div> 




[`cloud.sagemath.com`](https://cloud.sagemath.com).
 --->
