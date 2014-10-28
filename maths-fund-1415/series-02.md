% 6G4Z3001_1314 \\\\ Mathematics Fundamentals
% Killian O'Brien
% Oct 2014
# Series 01

## Series \\\\ Introduction

Work through chapter 2 in the notes up to Example 2.3 on the harmonic series. 

## Series \\\\ Stacking blocks

![Fig. Block stacking](my_stack.jpg)

Let $h_n$ denote the overhang of this optimal simple stack of $n$ blocks, each of width $w$. The overhang $h_n$ is measured from the rightmost edge of the top block back to the rightmost edge of the bottom block.

![Fig. An optimal simple stack of blocks](stack.png)

To create the stack of $n$ blocks we place the optimal stack of $n-1$ blocks on top of the bottom block. The best way of doing this is to position the centre of gravity of the stack of $n-1$ blocks directly over the edge of the bottom block.

So we see that 
$$
\begin{align*}
h_n &= \text{ overhang obtained from optimal stack of $n$ blocks} \\
&= \text{ centre of gravity of the upper $n-1$ blocks}
\end{align*}
$$

Using this we can develop a recurrence relation for the value of $h_n$

$$
\begin{align*}
h_1 & = 0 , \\
h_n &= h_{n-1} + \frac{1}{n-1} \frac{w}{2}
\end{align*}
$$

The right hand side of the recurrence relation can be understood as a weighted averaging of the positions of the centres of gravity of the blocks in the stack.

Applying this recurrence relation to develop the sequence $\left \{ h_n \right \}$ will show the presence of the harmonic series more clearly.

$$
\begin{align*}
h_1 & = 0 , \\
h_2 &= \frac{w}{2}, \\
h_3 &= \frac{w}{2} + \frac{1}{2} \frac{w}{2} = \frac{w}{2} \left ( 1 + \frac{1}{2} \right ) , \\
h_4 &= \frac{w}{2} \left ( 1 + \frac{1}{2} \right ) + \frac{1}{3} \frac{w}{2} = \frac{w}{2} \left ( 1 + \frac{1}{2} + \frac{1}{3} \right ) \\
&\vdots \\
h_n &= \frac{w}{2} \left (  1 + \frac{1}{2} + \frac{1}{3} + \dots + \frac{1}{n-1} \right )
\end{align*}
$$
 
## Series \\\\ Stacking blocks

### Obtaining a value for $h_n$

$$h_n = \frac{w}{2} \left (  1 + \frac{1}{2} + \frac{1}{3} + \dots + \frac{1}{n-1} \right )$$

![Fig. An integral approximating the harmonic series](integralunfilled.png)

$$h_n \approx \frac{w}{2} \int_1^n \, \frac{1}{x} \, dx $$

![Fig. An integral approximating the harmonic series](integralfilled.png)

$$h_n = \frac{w}{2} \left ( \int_1^n \, \frac{1}{x} \, dx + \gamma_n \right ),$$
where 
$$\gamma_n = \text{ area of shaded regions }$$

![Fig. An integral approximating the harmonic series](integralfilledslid.png)

$$ \lim_{n \to \infty} \gamma_n = \gamma \approx 0.6$$

$\gamma$ is the Euler–Mascheroni constant.

So for large $n$ a very good approximation is 
$$
\begin{align*}
h_n &\approx \frac{w}{2} \left ( \int_1^n \, \frac{1}{x} \, dx + 0.6 \right ), \\
&= \frac{w}{2} \Big ( \log(n)+ 0.6 \Big ).
\end{align*}
$$

## Series \\\\ Stacking blocks

### An actual stack of Jenga blocks 

$$h_n \approx \frac{w}{2} \Big ( \log(n)+ 0.6 \Big )$$

#### How tall is a simple optimal stack with a $3$ metre overhang?

The Jenga block is $7.5$cm wide and $1.5$cm tall.

$$3 = \frac{0.075}{2} \Big ( \log(n) + 0.6 \Big )$$

Solve this to find number, $n$, of blocks required.

$$
\begin{align*}
n &= e^{\left ( \frac{3}{0.0375} - 0.6 \right )} \\
&\approx 3.0 \times 10^{34}, \text{ a LOT of bricks}
\end{align*}
$$

Such a stack would be $3.0 \times 10^{34} \times 0.015 \approx 4.6 \times 10^{32}$ metres tall.

### Now that's tall!

$4.6 \times 10^{32}$ metres is approximately $520 \, 000$ times the diameter of the observable universe.

### Further reading

Read more about better overhangs that can be achieved with more complicated stacking strategies in the article 

*Overhang*, by Mike Paterson and Uri Zwick, The American Mathematical Monthly , Vol. 116, No. 1 (Jan., 2009), pp. 19-44. Available from [JSTOR](http://www.jstor.org/stable/27642662)



## Series \\\\ Convergence

Recall from previous lecture ...

### Definition 2.3 (Convergence for series)

The series $\sum_{n=1}^\infty x_n$ *converges* to the limit (or sum) $L$ if the sequence of its partial sums, $\{ S_k \}_{k=1}^\infty$, is a convergent sequence and 
$$ \lim_{k \to \infty} S_k = L . $$
If this is the case then we can simply write
$$ \sum_{n=1}^\infty x_n = L .$$

A series is *divergent* if the sequence of its partial sums is a divergent sequence.

Interesting examples were:

* The sum of powers of $\frac{1}{2}$, 
$$
\sum_{n=1}^\infty \left ( \frac{1}{2} \right )^n = \frac{1}{2} + \frac{1}{4} + \frac{1}{8} + \frac{1}{16} + \dots ,
$$
which is convergent, with sum 1.

* The harmonic series 
$$
\sum_{n=1}^\infty \frac{1}{n} = 1 + \frac{1}{2} + \frac{1}{3} + \frac{1}{4} + \dots ,
$$
which is divergent, as it increases without upper bound.

We aim now to describe various results that can detect convergence/divergence for certain series.

## Series \\\\ Linear combinations

Thge following theorem provides a similar result to the linearity case of the algebra of limits theorem for sequences from Chapter 1.

### Theorem 2.2 (Linear combinations of convergent series)

Suppose that we have two convergent series $\sum_{m=1}^\infty  a_m$ and $\sum_{m=1}^\infty b_m$ such that
$$ \sum_{m=1}^\infty a_m = A , \text{ and } \sum_{m=1}^\infty b_m = B .$$
Then for any pair $\alpha, \beta \in \mathbb{R}$ we have a new series 
$$ \sum_{m=1}^\infty \left ( \alpha a_m + \beta b_m \right ) ,$$
which is convergent and satisfies
$$ \sum_{m=1}^\infty \left ( \alpha a_m + \beta b_m \right ) = \alpha A + \beta B.$$

*Proof*. See visualizer.

## Series \\\\ Convergence tests (sec. 2.3)

### Theorem 2.3 (General term test)

If a sequence has a non-zero limit (or no limit at all) then the associated series will
diverge. 

Equivalently, by forming the contra-positive we can quote this test as: 

If a series
converges then the associated sequence of terms converges to zero. 

Symbolically these two statements are

1. $$\lim_{m \to \infty} a_m  \neq 0 \, \Rightarrow \, \sum_{m=1}^\infty a_m \text{ diverges,}$$

2. $$ \sum_{m=1}^\infty a_m \text{ converges} \, \Rightarrow \, \lim_{m \to \infty} a_m = 0.$$

$Proof$. See visualizer.

## Series \\\\ Convergence tests (sec. 2.3)

### Theorem 2.4 (Geometric series test)

The geometric series $\sum_{n=1}^\infty a r^{n-1}$ converges trivially if $a=0$. If $a \neq 0$ then it converges if and only if $|r| < 1$, in which case 
$$ \sum_{n=1}^\infty a r^{n-1} = \frac{a}{1-r} .$$

*Proof*. See visualizer.

Use the following [Sage](http://www.sagemath.org) cell to experiment with some geometric series. 

<div class="compute"><script type="text/x-sage">
n=var('n') #defines n to be a symbolic variable
html('<h2>Geometric Series plotter</h2>')
html('<p>Enter the parameters $a$ and $r$ for the series $\sum_{n=1}^\infty ar^{n-1}$ and the number $N$ of partial sums to plot.</p>')
@interact
def geometric_series_plotter(a = input_box(label="\(a = \)",default=5), r = input_box(label="\( r =\)",default=1/3), N=input_box(label="\( N = \)",default=100)):
    x(n) = a*r^(n-1) #defines the sequence terms
    html('The geometric series $\sum_{n=1}^\infty x_n$ is $\sum_{n=1}^\infty '+latex(x(n))+'$.') #displays x(n)

    if a==0:
        html('<p>This series is trivially convergent to $0$.</p>');
    elif abs(r)<1:
        html('<p>This series is convergent with sum $'+latex(a/(1-r))+'$.</p>')
    else:
        html('<p>This series is divergent. </p>')


    X=[a] #initialize the list X of partial sums

    for i in range(2,N):
        X.append(X[i-2]+x(i)); #this loop extends X

    P=list_plot(X) #defines the plot P

    if abs(r)<1: #if the geometric series converges then add a line showing the position of the limit
        P=P+line([(0,a/(1-r)),(N,a/(1-r))], color='red',linestyle='--')

    show(P) #displays the plot
</script></div>

## Series \\\\ Your work on this topic

* Read through the notes - Chapter 2 up to theorem 2.4 (Geometric Series Test)
* Prepare the tutorial exercises - Questions 1,2,3,4,6 from Exercises 2.1 (if not already done so)
* Study Chapter 43 on Infinite Series in [Schaum's Outline of Calculus](http://capitadiscovery.co.uk/mmu/items/1954431) by Ayres & Mendelson

For a musical perspective on the harmonic series, watch Leonard Bernstein at the piano explaining harmonics. 

<iframe width="640" height="480" src="http://www.youtube.com/embed/8n3qMB6AD_0" frameborder="0" allowfullscreen></iframe>

<iframe width="640" height="480" src="http://www.youtube.com/embed/iDTj6tBnHlA" frameborder="0" allowfullscreen></iframe>



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
</script></div> </script></div>  --->
