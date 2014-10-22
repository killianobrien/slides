% 6G4Z3001_1314 \\\\ Mathematics Fundamentals
% Killian O'Brien
% Oct 2013
# Series 02

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

And after doing lots of mathematics, watch Leonard Bernstein explain the harmonic series in the musical context.

<iframe width="640" height="480" src="http://www.youtube.com/embed/8n3qMB6AD_0" frameborder="0" allowfullscreen></iframe>

<iframe width="640" height="480" src="http://www.youtube.com/embed/iDTj6tBnHlA" frameborder="0" allowfullscreen></iframe>

And then enjoy Bernstein conducting Carreras, singing *Maria* from Sondheim & Bernstein's *West Side Story*.

<iframe width="640" height="480" src="http://www.youtube.com/embed/3ZPA8fwp7PE" frameborder="0" allowfullscreen></iframe>


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
