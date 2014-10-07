% 6G4Z3001_1415 \\\\ Mathematics Fundamentals
% Killian O'Brien
% Oct 2014
# Sequences 03

## Sequences \\\\ Convergence

Recall the formal definition we met last time.

### Definition 1.6 (Formal definition of convergence)
The sequence $\left \{ x_n \right \}$ *converges* to the *limit* $L$ if given any $\epsilon > 0$ we can find a positive integer $N_\epsilon$ such that for all $n \geq N_\epsilon$ the inequality $\left | x_n - L \right | < \epsilon $ holds. 

This definition is saying that $\left \{ x_n \right \}$ converges to $L$ if for all small positive distances $\epsilon$, the sequence eventually (for all $n \geq N_\epsilon$ ) lies within a distance $\epsilon$ of the limit $L$.

We also consider the *negation* of the definition, i.e. the definition of non-convergence.

### Definition of non-convergence
The sequence $\left \{ x_n \right \}$ *does not converge* to the *limit* $L$ if there exists some $\epsilon > 0$ such that for every positive integer $N$ such there is some $n \geq N$ such that  $\left | x_n - L \right | \geq \epsilon $ holds. 

This definition is saying that that $\left \{ x_n \right \}$ does not converge to $L$ if there is some distance $\epsilon$ such that the sequence will always have terms beyond the distance $\epsilon$ of $L$.

Evaluate the [Sage](http://www.sagemath.org) cell below and use the resulting interact to visualize the way the definition works.



<div class="compute"><script type="text/x-sage">
html("<h2>Investigating sequence convergence</h2>")
html("<p>Use the boxes to define the sequence term $a_n$ in terms of the variabe $n$. Provide values for the limit candidate $L$, $\epsilon$ and the minimum and maximum values of $n$ over which to plot the sequence.")
html("<p>The plot will show a shaded band extending a width of $\epsilon$ either side of $L$. By adjusting $n_{\mathrm{min}}$ and $n_{\mathrm{max}}$ try to see whether or not the sequence eventually lies within distance $\epsilon$ of $L$ according to whether or not $L=\lim a_n$.</p>")
n=var('n')
@interact
def delta_epsilon(an = input_box(label="\(a_n = \)",default=1/n), eps = input_box(label="\( \epsilon =\)",default=1/10), L=input_box(label="\( L = \)",default=0), nm=input_box(label="\( n_{\mathrm{min}} = \)",default=1), nM=input_box(label="\( n_{\mathrm{max}} = \)",default=10)):
    Limit=an.limit(n=oo)

    html("<p>The limit of " + "$"+ latex(an) +"$" " is $" +latex(Limit) + "$ .</p>")
    html("<p>You have $L$ set as $"+latex(L) +"$ .</p>")
    html("<p>The value of $\epsilon$ is set at $"+latex(eps) +"$ .</p>")
	html("<p>The plot shows terms $a_n$ for $"+latex(nm)+" \leq n \leq "+latex(nM)+"$.</p>")

    p=point((0,L),size=50)

    for i in range(nm,nM+1):
        p+=point((i,an.subs(n=i)))

    eps_region = polygon([(0,L-eps),(0,L+eps),(nM,L+eps),(nM,L-eps)], rgbcolor=(1,0.6,0.6), alpha=0.5)
    L_line = line([(0,L),(nM,L)], rgbcolor=(0.5,0.5,0.5),linestyle='--')

    show(p + eps_region + L_line, xmin=nm,xmax=nM, aspect_ratio='automatic')
</script></div>

## Sequences \\\\ Properties of convergence

We'll go through the proofs of theorems 1.1, 1.2 & 1.4 on the visualizer.

### Theorem 1.1 (Uniqueness of limits)
If a sequence converges then its limit is unique, i.e. if $x_n \to L$ and $x_n \to M$ as $n \to \infty$ then $L=M$.

### Theorem 1.2
Every convergent sequence is bounded.

### Theorem 1.3 (Monotone convergence theorem)

Every bounded monotonic sequence is convergent.

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
