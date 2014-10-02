% 6G5Z3006_1314 \\\\ Number Theory & Cryptography
% Killian O'Brien
% Oct 2014

# NT&C \\\\ Introduction

## NT&C \\\\ Introduction
See the info page on the unit's Moodle area for information on 

* Teaching team & pattern
* Unit syllabus
* Assessment
* Resources

## NT&C \\\\ What is number theory?

* Number Theory is the study of the positive integers and the operations of addition and multiplication and their properties.
* Of particular importance are the *prime numbers*, those positive integers $p>1$ whose only factors are 1 and $p$. 
* NT has a long history and the earliest mathematicians considered problems in this area. 

NT is a central area in pure mathematics and has several sub-fields including

* Analytic number theory -- where tools from analysis (real and complex valued functions) are used to study properties of the integers
* Algebraic number theory -- studies questions surrounding other algebraic structures related to the integers and rational numbers. 

NT used to be seen as *purely* pure mathematics, with little or no application to the practical world. However since the mid 20th Century it plays an important role in the study of algorithms in computer science and in the generation of cryptographic systems for secure communication.

Two sources for further information about the history of number theory are

* [*History of the theory of numbers*](http://openlibrary.org/books/OL6616242M/History_of_the_theory_of_numbers_...) (1919) by Leonard Eugene Dickson.
* [*Number theory and its history*](http://capitadiscovery.co.uk/mmu/items/1539085) by Oystein Ore (link to MMU library)


Coming up to date, the leaked documents from Edward Snowden contain allegations that place mathematics at the heart of one of the central political, legal and human rights issues of the day. Read about Snowden's revelations from 

* [The Guardian](http://www.theguardian.com/world/edward-snowden)
* [ProPublica](http://www.propublica.org/series/surveillance)

## NT&C \\\\ The integers (Ch. 1)
To put things on a firm foundation we need a rigorous description of the integers,
$$\mathbb{Z} = \left \{ \dots, -3, -2, -1, 0 , 1 , 2, 3, \dots \right \}.$$

The need to take such care at his initial stage can be appreciated by considering all the other mathematical systems that have addition-like and multiplication-like operations, such as the natural numbers ($\mathbb{N}$), the rationals ($\mathbb{Q}$), the real numbers ($\mathbb{R}$), the complex numbers ($\mathbb{C}$), matrices, functions, $\dots$ , to name but a few.

The integers can be uniquely defined (up to isomorphism) by a system of 11 axioms.

The first set of axioms concern the addition operation.

1. (**Assosiativity of addition**) For all $x,y,z \in S$, $(x+y)+z = x+ (y+z)$.
2. (**Existense of additive identity**) There exists $0 \in S$ with the property that for all $x \in S$, $x+0=0+x =x$.
3. (**Existence of additive inverses**) For all $x \in S$, there exists $-x \in S$ such that $x + (-x) = (-x) + x = 0$.
4. (**Commutativity of addition**) For all $x,y \in S$, $x+y = y+x$.

These axioms characterise such a system $(S, +)$ as a *commutative group*. The next set of axioms concern the multiplication operation.

5. (**Associativity of multiplication**) For all $x,y,z \in S$, $x(yz) = (xy)z$.
6. (**Existence of multiplicative identity**) There exists $1 \in S$ with the property that for all $x \in S$, $1x = x1 = x$. 
7. (**Commutativity of multiplication**) For all $x,y \in S$, $xy = yx$. 
8. (**Distributivity between addition and multiplication**) For all $x,y,z \in S$, $(x+y)z = xz + yz$.

These eight axioms characterise the system $(S, + , \cdot)$ as a *commutative ring with identity*. 

The next set of axioms concern the concept of the ordering of the elements of $S$. The ordering $>$ is defined in terms of a set of *positive* elements $P$. We will write $x>0$ to mean that $x \in P$, and write $x>y$ to mean that $x-y \in P$.

The system $(S, + , \cdot)$ is an *ordered* ring if there exists a subset $P \subset S$, (think of $P$ as containing all the 'positive' elements) satisfying the following three axioms.

9. (**Trichotomy**) $S$ is a disjoint union 
$$
S= -P \cup \{ 0 \} \cup P,
$$
where $-P=\{ -x : x \in P \}$.
10. (**Positivity preserved by sums and products**) For all $x,y \in P$ we have $x+y \in P$ and $xy \in P$.

A system $(S,+,\cdot,>)$ satisfying the above axioms is called a *commutative ordered ring*. All other properties of the order relation can be derived from the above axioms. $\mathbb{Z}$, $\mathbb{Q}$ and $\mathbb{R}$ are all examples of commutative ordered rings. 

The final step in characterizing the integers, the one that discriminates them from other commutative ordered rings is the notion that the elements $1$, $1+1$, $1+1+1$, \dots etc are *all* of the positive integers. This notion is captured by either of the following two logically equivalent axioms.

11a. (**Induction axiom**) If $J$ is a subset of the positive elements of $S$, i.e. $J \subset P \subset S$, and $J$ has the properties 
	
* $1 \in J$,
* $j \in J \Rightarrow j+1 \in J$,

then $J = P$. 

11b. (**Well-ordered axiom**) Every non empty subset of $P$ has a least element, i.e. if $Q \subset P$ is non-empty then there exists $q_{\text{min}} \in Q$ such that for all $q \in Q$ we have $q_{\text{min}} \leq q$.

Moreover the least element $q_{\text{min}}$ referred to in axiom (11b.) is unique, this following from the trichotomy axiom.

## NT&C \\\\ The integers 

### Proofs by induction (sec. 1.3)

Many important results in number theory are proved using proof by induction (or the well-ordered axiom). The induction axiom was expressed in terms of elements of a set. However proofs by induction are more usually presented by associating a statement with each positive integer and making use of the following version of the axiom.

#### Usual phrasing of induction principle
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