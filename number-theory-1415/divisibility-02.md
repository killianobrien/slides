% 6G5Z3006_1314 \\\\ Number Theory & Cryptography
% Killian O'Brien
% October 2013

# NT&C \\\\ Integer divisibility (Ch. 2)

## NT&C \\\\ The Euclidean algorithm (sec. 2.4)

The Euclidean algorithm calculates the gcd of two integers $a,b$ and coefficients $n,m$ such that 
$$\gcd(a,b) = na + mb.$$

The following lemma relates gcds to integer division with remainder.

### Lemma 2.4
If $a=qb+r$ then the common divisors of $a$ and $b$ are exactly the common divisors of $b$ and $r$, in particular
$$
\gcd(a,b) = \gcd(b,r) .
$$

### Example 2.2 (Illustrative Example of Euclidean Algorithm)
Find $\gcd(525,90)$.

$$
\begin{align}
525 & = 5 \times 90 + 75 , \quad \Rightarrow \quad \gcd(525,90)=\gcd(90,75), \\
90 & = 1 \times 75 + \underline{15}, \quad \Rightarrow \quad \gcd(90,75)=\gcd(75,15),\\
75 & = 5 \times 15 + 0, \quad \Rightarrow \quad \gcd(75,15)=\gcd(15,0) = 15.
\end{align}
$$

Combining the gcd equations shows that $\gcd(525,90)=15$. We notice that we repeat the integer divisions until we reach a remainder of zero. The last non-zero remainder obtained is the greatest common divisor of the original pair $a,b$.

In addition to finding the gcd, the algorithm also provides the linear combination yielding the gcd. This is found by working through the integer division equations backwards, starting with the second-last one, i.e. the one featuring the gcd as the remainder. We then work our way back through the equations until we have the gcd $d$ expressed as a linear combination of the initial $a$ and $b$. 

$$
\begin{align}
\underline{15} & = 90 - 1 \times 75, \text{ from above}\\
&= 90 - (525 - 5 \times 90), \text{ from above}\\
&= -1 \times 525 + 6 \times 90.
\end{align}
$$

### Example 2.3 (A longer example)

Find $\gcd(12378, 3054)$.
$$
\begin{align}
12378 &= 4 \times 3054 + 162 , \\
3054 &= 18 \times 162 + 138, \\
162 &= 1 \times 138 + 24 ,\\
138 &= 5 \times 24 + 18 , \\
24 &= 1 \times 18 + \underline{6}
\end{align}
$$
So $\gcd(12378,3054) = 6$. Working backwards, as described in the previous example, will eventually produce 6 as a linear combination of 12378 and 3054.
$$
\begin{align}
6 &= 24 - 18 , \text{ from above} \\
&= 24 - (138 - 5 \times 24), \text{ from above}\\
&= 6 \times 24 - 138 , \\
&= 6 \times (162 - 138) - 138 , \\
&= 6 \times 162 - 7 \times 138 ,\\
& \vdots \\
&= 132 \times 12378 - 535 \times 3054,
\end{align}
$$
which is the desired linear combination.

## NT&C \\\\ The Euclidean algorithm (sec. 2.4)

### Formally describing the algorithm (Alg. 2.1)

The following procedure is an algorithm for determining $\gcd(a,b)$ and obtaining the integer coefficients $m,n$ for an expression
$$
\gcd(a,b) = ma + nb .
$$
We assume that $a \geq b > 0$ (this is sufficient for the general case by earlier comments). Consider the sequence of integer divisions that are carried out until a remainder of zero is obtained:
$$
\begin{align}
a & = q_1 b + r_1 , \quad 0 < r_1 < b \\
b &= q_2 r_1 + r_2, \quad 0 < r_2 < r_1 \\
r_1 &= q_3 r_2 + r_3 , \quad 0 < r_3 < r_2 \\
 & \, \, \, \vdots \nonumber \\
 r_{n-2} &= q_n r_{n-1} + r_n , \quad 0 < r_n < r_{n-1} \\
 r_{n-1} &=q_{n+1} r_n .
\end{align}
$$
The last non-zero remainder $r_n$ obtained in these equations is the required greatest common divisor $r_n=gcd(a,b)$. 

From the penultimate of these we get an expression for $r_n$ as a linear combination of $r_{n-1}$ and $r_{n-2}$,
$$
r_n = r_{n-2} - q_n r_{n-1} .
$$
Working backwards through these equations we replace each intermediate remainder $r_j$ ($1 \leq j < n$) with linear combinations of earlier remainders until we arrive at a linear combination for $r_n$ in terms of $a$ and $b$, as required.

### Justification

The justification for the conclusions of the algorithm follow from theorem 2.2 and lemma 2.4. The fact that the algorithm will terminate (i.e. stop after a finite number of steps) follows from the fact that the remainders $r_i$ constitute a strictly decreasing sequence of non-negative integers and hence this sequence must arrive at zero after a finite number of steps.

### Links

A nice javascript [Euclidean Algorithm Calculator](http://www.math.sc.edu/~sumner/numbertheory/euclidean/euclidean.html) by [David Sumner](http://www.math.sc.edu/~sumner/) from University of South Carolina.

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
