% 6G5Z3006_1415 \\\\ Number Theory & Cryptography
% Killian O'Brien
% October 2014

# NT&C \\\\ Integer divisibility (Ch. 2)

## NT&C \\\\ Divisibility (sec. 2.1)

In this chapter we introduce the divisibility relation of the integers. It accords exactly with our primary-school notions of one number *evenly dividing* another.

### Definition 2.1 (Divisibility)

Let $a,b \in \mathbb{Z}$. We say that $b$ *divides* $a$ if and only if there exists an integer $c \in \mathbb{Z}$ such that 
$$ a = bc .$$
If this is so then $b$ and $c$ can be referred to as *factors* or *divisors* of $a$, 
and $a$ can be referred to as a (integer) multiple of $b$ and $c$. 

### Notation

We write $b | a$ to denote that $b$ divides $a$ and $b \! \! \not | a$ to denote that it does not. 

### Example 2.1

The integers $1$, $3$, $5$ and $15$ all divide $15$, whereas $10$ is not divisible by $3$.

## NT&C \\\\ Divisibility (sec. 2.1)

### Theorem 2.1 (Properties of divisibility)

The divisibility relation enjoys the following properties:

1. (*Reflexivity*) For all $a \in \mathbb{Z}$, $a | a$.

2. (*Transitivity*) For all $a,b,c \in \mathbb{Z}$, if $a|b$ and $b|c$ then $a | c $.

3. (*Divisibility of linear combinations*) For all  $a,b,c \in \mathbb{Z}$, if $a | b$ and $a | c$ then for all $n,m \in \mathbb{Z}$, $a | \left ( n b + m c \right )$.

4. (*$1$ divides everything*) For all $a \in \mathbb{Z}$, $1|a$.

5. (*everything divides $0$*) For all $a \in \mathbb{Z}$, $a | 0$.

6. (*$0$ divides only itself*) For all $a \in \mathbb{Z}$, if $0 | a$ then $a=0$.

7. For all $a,b,c \in \mathbb{Z}$, if $c \neq 0$ then $a | b$ if and only if $ac | bc$.

* We will prove all of these.
* Note that an integer $z$ has exactly the same divisors as its negative $-z$. In order to avoid duplication we normally confine our attention to the divisibility properties of the positive integers. 

## NT&C \\\\ Primes (sec. 2.2)

### Definition 2.2 (Prime, Composite)
An integer $p > 1$ is *prime* if it has no positive divisors other than itself and 1. An integer $n > 1$ which is not prime is called *composite*.

The list of prime numbers begins
$$
2, \, 3, \, 5 , \, 7 , \, 11 , \, 13 , \, 17, \, 19, \, 23, \dots 
$$

<div class="compute"><script type="text/x-sage">
P=primes(1,100)
show(P)
</script></div>

Also look at relevant Matlab commands

~~~
factor(n)
primes(n)
isprime(n)
~~~

We shall prove he following theorem later in the course. 

### Theorem (Fundamental Theorem of Arithmetic)

Every positive integer $n$ factors into a product of primes
$$
n = p_1^{\alpha_1} p_2^{\alpha_2} \dots p_r^{\alpha_r}, \quad \text{$p_i$ prime, $\alpha_i \in \mathbb{Z}^+$}
$$
and this factorisation is unique up to the order in which the primes are written down.

Most people's intuition about the integers agrees with this result and the existence of such prime factorisations can be proved now and follows by recursively applying the definition of prime/composite to $n$ and using the transitivity of divisibility. But the proof of the uniqueness of these factorisations requires some more theory to be developed. 

## NT&C \\\\ Common divisors (sec. 2.3)

Relationships between the divisibility of different integers is investigated using the concept of common divisors. 

### Definition 2.3 (Common divisor)
Let $a,b \in \mathbb{Z}$. An integer $c$ is a *common divisor* of $a$ and $b$ if and only if $c$ divides $a$ and $c$ divides $b$. 

### Definition 2.4 (Greatest common divisor)
By the well-orderedness of $\mathbb{Z}$ there exists a *greatest common divisor* of $a$ and $b$. This is denoted $\text{gcd}(a,b)$. Note that some authors use a minimalist notation of $(a,b)$ to denote the greatest common divisor. 

### Definition 2.5 (Coprime)
A pair of integers $a,b \in \mathbb{Z}$ are *coprime* (or *relatively prime*) if and only if $\gcd(a,b)=1$.

Note that as long as $a,b$ are not both zero then $\gcd(a,b)$ exists. This follows since all common divisors of $a$ and $b$ are bounded above by $\max(|a|,|b|)$ in this case, and so a greatest one exists by the well-orderedness of $\mathbb{Z}$

In the next section we will see the Euclidean Algorithm which calculates the gcd of a pair of integers.  It consists of repeatedly applying the process of *integer division with remainder*. Again, while we give a very rigorous treatment of this process here, the concept should be very familiar to you from your schoolwork with numbers. 

## NT&C \\\\ Common divisors (sec. 2.3)

### Theorem 2.2 (Integer division with remainder)

Let $a,b \in \mathbb{Z}$, $b \neq 0$. There exists a unique pair $q,r \in \mathbb{Z}$ such that
$$
a = qb + r , \quad \quad 0 \leq r < |b|.
$$

*Proof.* See notes. Notice that it uses axiom 11 of the integers, in the form 11 b. the well ordered property.

We finish with a characterisation of the gcd of two integers $a$ and $b$ in terms of linear combinations of $a$ and $b$. 

### Theorem 2.3 (Characterisation of greatest common divisor)

Suppose that $a,b \in \mathbb{Z}$ are not both zero and that $d=\gcd(a,b)$. Then there exists $n,m \in \mathbb{Z}$ such that 
$$
d = ma + nb,
$$
and moreover any common divisor of $a$ and $b$ divides $d$. 

*Proof*. Let $S$ be the set of all positive linear combinations of $a$ and $b$, i.e.
$$
S = \left \{ \alpha a + \beta b \, : \, \alpha, \beta \in \mathbb{Z} ,
 \, \alpha a + \beta b > 0 \right \}.
$$
By the well-ordered axiom $S$ has a least element $d$, which we can write as 
$$
0 < d = ma + nb ,
$$
for some pair of integers $m,n$. We claim that $d$ is a common divisor of $a$ and $b$.

Suppose that $d$ did not divide $a$. Then by the integer division theorem we could write
$$\begin{align}
&a = qd + r, \quad 0 < r < d, \\
\Rightarrow & r = a - qd , \\
& = a - q(ma +nb), \text{ (from above)} \\
&= (1-qm)a -qn b .
\end{align}
$$
So we see that $r$ would be a linear combination of $a$ and $b$, i.e. $r \in S$. But then this would contradict the fact that $d$ is the least element of $S$, since we have $r<d$ above. So we conclude that $d$ does indeed divide $a$. An argument along similar lines will show that $d$ also divides $b$. So we can conclude that $d$ is a common divisor of $a$ and $b$. 

Next we see that if $e$ is any other common divisor of $a$ and $b$ then $e| d$ by property 3 of theorem 2.1. Hence $d$ is the greatest common divisor and all other common divisors divide $d$. 
$\Box$

## NT&C \\\\ Activities

* Study the detail of these sections in Number Theory notes.
	* In particular, appreciate the role played by the well ordered axiom in the proofs of theorems about integer division with remainder and the characterisation of the gcd in terms of minimal linear combination.
* Begin work on the problems in Exercises 1.1 (we will consider some of these next week and in the tutorials in 2 weeks time)


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
