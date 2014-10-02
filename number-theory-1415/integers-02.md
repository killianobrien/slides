% 6G5Z3006_1314 \\\\ Number Theory & Cryptography
% Killian O'Brien
% 04 October 2013

# NT&C \\\\ The integers (Ch.1)

## NT&C \\\\ The integers \\\\ Axioms 11a & 11b

We will prove the equivalence of the two versions of axiom 11. We'll quote the axioms now referring explicitly to the integers.

11a. (**Induction axiom**) If $J$ is a subset of the positive integers, i.e. $J \subset \mathbb{Z}^+$, and $J$ has the properties 
	
* $1 \in J$,
* $j \in J \Rightarrow j+1 \in J$,

then $J = \mathbb{Z}^+$. 

11b. (**Well-ordered axiom**) Every non empty subset of $\mathbb{Z}^+$ has a least element, i.e. if $Q \subset \mathbb{Z}^+$ is non-empty then there exists $q_{\text{min}} \in Q$ such that for all $q \in Q$ we have $q_{\text{min}} \leq q$.

We will see use of both forms of the axiom at some key points in the unit. 

## NT&C \\\\ The integers \\\\ Proofs by induction

In practice, we use axiom 11a in a form expressed in terms of statements indexed by the elements of $\mathbb{Z}^+$.

#### Usual phrasing of induction principle (axiom 11a)
Suppose that we have a statement $P(n)$ associated to every integer $n \geq 1$. If the following two statements hold:

* $P(1)$ is true,
* for all $k \geq 1$, $P(k) \Rightarrow P(k+1)$,

then we can conclude that $P(n)$ holds for every integer $n \geq 1$.

There are 7 proofs by induction for you to work with in Exercises 1.2 . You have seen the first one before I'm sure, but let's redo it as revision.

* Use induction to prove that $\forall \, n \geq 1 \, \, \displaystyle\sum_{j=1}^{n} j = \frac{1}{2} n (n+1)$.

As a further example let's seek a similar formula for $\sum_{j=1}^{n} j^4$. Intuition tells us that this should be a quintic (degree 5) polynomial in $n$ (think of summation as similar to integration). Use Sage to '*discover*' the correct polynomial and then prove the result using induction.

<div class="compute"><script type="text/x-sage">
# define the summation function f and a general quintic g
var('a0, a1, a2, a3, a4, a5')
def f(m):
    return sum(i^4 for i in range(1,m+1))
def g(m):
    return a0 + a1*m + a2*m^2 + a3*m^3 + a4*m^4 + a5*m^5

# generate 6 equations in the 6 unknowns a0,...,a5
Eqs=[f(m) == g(m) for m in range(1,7)]

# solve these equations
# (solution_dict=True is a technical option to
# enable the use of the subs below)
sol=solve(Eqs, a0, a1, a2, a3, a4, a5, solution_dict=True)

# see the equations and soltion
show(Eqs)
show(sol)

# substitute the solution into the 
# general quintic and display it.
var('n')
show(g(n))
show(g(n).subs(sol[0]))
</script></div> 

## NT&C \\\\ The integers

### Next week's tutorial on number theory

* First few problems in Exercises 1.1
* Prepare the induction problems in Exercises 1.2

### Further work
* Read Preface and Chapters 1 & 2 of [*Elementary Number Theory*](http://shell.cas.usf.edu/~wclark/elem_num_th_book.pdf) by Edwin Clark
* Use the Sage cell above to investigate the formulas for 
$$\sum_{j=1}^n j^a$$
for various positive integers $a$. Is there a pattern to the polynomial coefficients? Research this further. 


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
