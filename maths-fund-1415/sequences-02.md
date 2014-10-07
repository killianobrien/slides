% 6G4Z3001_1415 \\\\ Mathematics Fundamentals
% Killian O'Brien
% Oct 2014
# Sequences 02

## Sequences \\\\ Boundedness

Before getting on to the concept of convergence we define the concept of boundedness for a sequence. 

### Definition 1.4

A sequence $\left \{ x_n \right \}$ is said to be *bounded* if there exists some positive number $M$ such that for all $n$, the elements of the sequence satisfy the condition 
$$ \left | x_n \right | \leq M.$$ 
A sequence $\left \{ x_n \right \}$ is said to be *bounded above* if there exists some  number $M$ such that for all $n$, the elements of the sequence satisfy the condition 
$$ x_n  \leq M.$$ 
A sequence $\left \{ x_n \right \}$ is said to be *bounded below* if there exists some  number $M$ such that for all $n$, the elements of the sequence satisfy the condition 
$$ x_n  \geq M.$$ 
The number $M$ is called the (*upper / lower*) *bound*, as appropriate.

## Sequences \\\\ Convergence

### Definition 1.5 (*Informal def. of convergence*)
Let L be a number. A sequence $\left \{ x_n \right \}$ *converges* to the *limit* $L$ if as $n$ increases, the
elements of the sequence get closer and closer to the number $L$, or equivalently, the distance $\left | x_n - L \right |$ gets closer and closer to $0$. 

### Notation and phrasing 

Another way of saying that a sequence $\left \{ x_n \right \}$  converges to the limit $L$ is to say that $x_n$ tends to $L$ as $n$ tends to infinity, or in symbols
$$ x_n \to L \text{ as } n \to \infty,$$
or 
$$ \lim_{n\to \infty} x_n = L.$$
Such sequences are called *convergent* and if a sequence is not convergent then we call it
*divergent*.

Some sequences are divergent because their terms keep increasing in absolute value without any upper bound, in which case we can write
$$y_n \to \infty \text{ as } n \to \infty,$$
or
$$y_n \to -\infty \text{ as } n \to \infty.$$
The first of these says that the term $y_n$ increase in positive value without any upper bound, and the second says that the terms $y_n$ get large and negative without any lower bound.

Note that such sequences are still divergent. $\infty$ is not a real number!

### Example 1.7

It is not too hard to appreciate the convergence of some simple sequences, for instance
$$ \lim_{m \to \infty} \frac{1}{m} = 0 .$$
The numbers $\frac{1}{m}$ are getting smaller and smaller and moreover they are getting \textit{arbitrarily small}, i.e. given any small number $\epsilon$ > 0, eventually the fractions $\frac{1}{m}$ will get smaller than $\epsilon$. 

## Sequences \\\\ Properties of convergence

### Theorem 1.1 (Uniqueness of limits)
If a sequence converges then its limit is unique, i.e. if $x_n \to L$ and $x_n \to M$ as $n \to \infty$ then $L=M$.

### Theorem 1.2
Every convergent sequence is bounded.

### Theorem 1.3 (Monotone convergence theorem)

Every bounded monotonic sequence is convergent.

## Sequences \\\\ Properties of convergence

### Theorem 1.4 (Algebra of limits theorem)

Let $\left \{ a_n \right \}$ and $\left \{ b_n \right \}$ be two convergent sequences with 
$$\lim_{n \to \infty} a_n = a \text{ and } \lim_{n \to \infty} b_n = b .$$ 
New sequences can be formed from the elements $a_n$ and $b_n$ in many ways. The following new sequences are all convergent and have the expected limits:

1. **Linear Combinations:**
$$\lim_{n \to \infty} \left (  \alpha a_n + \beta b_n \right )= \alpha a + \beta b,$$
where $\alpha, \beta \in \mathbb{R}$ are any pair of coefficients,

2. **Products**
$$\lim_{n \to \infty} \left ( a_n b_n \right ) = ab,$$

3. **Quotients** 
(assuming that $b \neq 0$ and for all $n$, $b_n \neq 0$)
$$ \lim_{n \to \infty} \left ( \frac{a_n}{b_n} \right ) = \frac{a}{b}.$$

The algebra of limits theorem can allow us to find the limits of sequences that are formed from sequences with known convergence properties. By referring to the theorem we can provide rigorous arguments to justify the limit of the sequence in question, based on limits of simpler sequences.

### Example 1.8 (Applying the algebra of limits theorem)

Consider the sequence $\{ x_n \}_{n=1}^\infty$ where 
$$ x_n = \frac{2}{3}\frac{2n^2 -n}{\left ( -3n^2 +2 \right )}.$$
By applying the various parts of the algebra of limits theorem we can see how to find the limit of this convergent theorem. 
$$\begin{align*}
\lim_{n \to \infty} x_n &= \lim_{n \to \infty} \frac{2}{3}\frac{2n^2 -n}{\left ( -3n^2 +2 \right )} \\
&= \frac{2}{3} \lim_{n \to \infty} \frac{2 - \frac{1}{n^2}}{\left ( -3 + \frac{2}{n^2} \right )}, \quad \text{linearity} \\
&= \frac{2}{3} \frac{\lim\limits_{n \to \infty} \left (2 - \frac{1}{n^2} \right )}{\lim\limits_{n \to \infty} \left ( -3 + \frac{2}{n^2} \right )}, \quad \text{quotient rule}\\
&= \frac{2}{3} \left ( \frac{2}{-3} \right ) = \frac{-4}{9}, \quad \text{linearity and known convergence of $\frac{1}{n^2}$}.
\end{align*}$$

## Sequences \\\\ Proving the properties

While the definition given above allows us to understand the idea of convergence, a more
rigorous formal definition is needed to prove results about the concept of convergence.

### Definition 1.6 (Formal definition of convergence)
The sequence $\left \{ x_n \right \}$ *converges* to the *limit* $L$ if given any $\epsilon > 0$ we can find a positive integer $N_\epsilon$ such that for all $n \geq N_\epsilon$ the inequality $\left | x_n - L \right | < \epsilon$ holds. 

This definition is saying that $\left \{ x_n \right \}$ converges to $L$ if for all small positive distances $\epsilon$, the sequence eventually (for all $n \geq N_\epsilon$ ) lies within a distance $\epsilon$ of the limit $L$.

Evaluate the [Sage](http://www.sagemath.org) cell below and use the resulting interact to visualize the way the definition works.

<div class="compute"><script type="text/x-sage">
html("<h2>Investigating sequence convergence</h2>")
html("<p>Use the boxes to define the sequence term $a_n$ in terms of the variabe $n$. Provide values for $\epsilon$ and the minimum and maximum Values of $n$ over which to plot the sequence.")
html("<p>The plot will show a shaded band extending a width of $\epsilon$ either side of the limit of $a_n$. By adjusting $n_{\mathrm{min}}$ and $n_{\mathrm{max}}$ try to see when the sequence lies within distance $\epsilon$ of $L$</p>")
n=var('n')
@interact
def delta_epsilon(an = input_box(label="\(a_n = \)",default=1/n), eps = input_box(label="\( \epsilon =\)",default=0.1), nm=input_box(label="\( n_{\mathrm{min}} = \)",default=1), nM=input_box(label="\( n_{\mathrm{max}} = \)",default=10)):
    L=an.limit(n=oo)

    html("<p>The limit of " + "$"+ latex(an) +"$" " is $" +latex(L) + "$</p>")
    html("<p>The value of $\epsilon$ is set at $"+latex(eps) +"$</p>")

    p=list_plot([an.subs(n=i) for i in range(nm,nM+1)])
    Lpoint=point((0,L),size=50)

    eps_region = polygon([(0,L-eps),(0,L+eps),(nM,L+eps),(nM,L-eps)], rgbcolor=(1,0.6,0.6), alpha=0.5)
    L_line = line([(0,L),(nM,L)], rgbcolor=(0.5,0.5,0.5),linestyle='--')

    show(p+Lpoint + eps_region + L_line, xmin=nm,xmax=nM, aspect_ratio='automatic')
</script></div>







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
 --->
