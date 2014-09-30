% 6G4Z3001_1415 \\\\ Mathematics Fundamentals
% Killian O'Brien
% Oct 2014
# Introduction

## A quick trip through the unit

See the unit's Moodle area for info on:

* Syllabus
* Teaching team & pattern
* Assessment
* Resources

# Some motivation

## Motivation \\\\ Convergence and divergence in applied mathematics

* **Convergence** is the concept of an (infinite) process getting closer and closer to some limiting state.
* **Divergence** is where the process does not converge.

This is important to understand as it is fundamental to much of applied mathematics, e.g.

* Mathematical models of the real world are almost always only approximations and so only offer approximations to the truth. 
* This is ok as long as we can in principle make the approximations as good as we want, i.e. make them *converge* to the actual truth.

![Fig. Increasing resolutions of the IPCC reports](http://nas-sites.org/climatemodeling/common/images/image_page_3_2_resolution.png)

Figure taken from *[A National Strategy for Advancing Climate Modeling](http://www.nap.edu/catalog.php?record_id=13430)* by US National Academy of Sciences

In addition ...

* The mathematical problems set up on these already approximate models are almost always impossible to solve *exactly* ...
* ... and we can only find approximate solutions to them (so called *numerical* solutions).
* This is ok as long as we can in principle make the approximations as good as we want, i.e. make them *converge* to the actual solution.
* For time based models, such as weather/climate, these approximations get poorer and poorer as we look into the future, i.e. they *diverge* from the actual solution.

## Motivation \\\\ Convergence and divergence in pure mathematics

* The integers $\mathbb{Z}$ and rationals $\mathbb{Q}$ can be rigorously described without too much trouble,
$$ \mathbb{Z} = \left \{ \dots, -3, -2, -1, 0 , 1, 2, 3, \dots \right \} \textit{ positive and negative whole numbers},$$
$$ \mathbb{Q} = \left \{ \, \frac{n}{m} \, : \, n,m \in \mathbb{Z}, m \neq 0 \right \} \textit{ ratios of integers} .$$

(*See Saeed's Set Theory lectures for explanation of this $\{ \quad \}$notation.*)

* Non-rational numbers (so called *irrationals*) are harder to describe rigorously and precisely, e.g.
$$\sqrt{2} , \, \pi , \, e $$

* One way to do so is to describe them as the limits of infinite sequences or infinite sums of rational numbers, e.g.
$$ \frac{\pi}{4} = \sum_{n=1}^\infty \frac{(-1)^{n+1}}{2n-1} = 1 - \frac{1}{3} + \frac{1}{5} - \frac{1}{7} + \dots $$
Many such interesting summation formulas exist for $\pi$.

* Infinite sequences and sums of mathematical objects and their convergence / divergence properties are a fundamental part of calculus and analysis: the study of the number line (2-d plane, 3-d space, ...) and functions defined on them. 

## Motivation \\\\ Convergence and divergence in pure & applied mathematics

* So there is lots of convergence & divergence going on 
* This needs to be studied and understood
* We will study sequences and series and their convergence/divergence.

## Sequences \\\\ Definitions and notation

**Definition** (1.1) A *sequence* is a list of elements (usually numbers) indexed by the positive integers. We usually use a single letter, with subscript, to denote the elements of a sequence, as in
$$x_1 , x_2 , x_3 , x_4, \dots .$$
We can represent the sequence $x_1 , x_2 , x_3 , x_4, \dots$ using the compact notation $\left \{ x_n \right \}_{n=1}^\infty$  or just simply $\left \{ x_n \right \}$ if the $n$ indexing is understood. 

**Example** (1.1)

* The sequence of positive integers $1,2,3, \dots $, or $\left \{ z_m \right \}$, where the rule is 
$$z_m = m . $$

* The Fibonacci sequence: $1, 1, 2, 3, 5, 8, 13, ...$ or $\left \{f_n \right \}$ , where the rule is
$$f_1 = 1, f_2 = 1 \text{ and } f_m = f_{m-1}+f_{m-2} \text{ for all } m \geq 2, $$  i.e. each element is the sum of the
previous two elements. This type of rule for a sequence, where each term is
defined using the values of some previous terms, is called a **recurrence relation**.

* The sequence of odd positive integers: $1, 3, 5, 7, ... $or $\left \{a_n\right \}$, where $$a_n = 2n-1.$$

* The sequence of prime numbers: $2, 3, 5, 7, 11, 13, ... $ or $\left \{ p_m \right \}$ , where $$p_m = ???.$$

## Sequences \\\\ Arithmetic and geometric sequences

**Definition** (1.2)
An *arithmetic sequence* has a common difference between successive elements and a *geometric sequence* has a common ratio of successive elements. So we can write an arithmetic
sequence as
$$a, a + d , a + 2d , a + 3d ,\dots $$
 or $\left \{ a_n\right \}$ , where $a_n = a + (n - 1)d$ .
Here $a$ is the initial element and $d$ is the common difference. A geometric sequence can
be written as
$$a, ar , ar^2 , ar^3 ,\dots $$
 or $\left \{ a_n \right \}$ , where $a_n = ar^{n-1}$.
Here $a$ is the initial element and $r$ is the common ratio.

**Examples** (1.2 through 1.5)

* The sequences of positive integers and odd positive integers above are actually arithmetic
sequences. The sequence of positive integers can be written as $\left \{ a_n \right \}$ , where
$$a_n = n = 1 + (n - 1),$$
so 1 is the initial element and 1 is the common difference. The
sequence of odd positive integers can be written as $\left \{ a_n \right \}$ , where 
$$a_n = 1 + (n - 1)2 ,$$ 
so 1 is the initial element and 2 is the common difference. 

* The sequence, 
$$ 1, \frac{1}{2}, \frac{1}{4} , \frac{1}{8}, \dots $$
of powers of $\frac{1}{2}$, is geometric as it has the form $\left \{a_n \right \}$ , where 
$$a_n = \left ( \frac{1}{2} \right )^{n-1},$$
so 1 is the initial element and 2 the common ratio. 

* Compound interest awarded on investments or charged on debts provide examples of geometric sequences. Suppose a bank offers an annual compound interest rate of $r \%$ on an initial deposit of $P$ units. Then the value of the deposit after $n$ years is given by 
$$v_n = P \left ( 1 + \frac{r}{100} \right )^n .$$

* The sequence $\left \{ x_n \right \}$, where 
$$x_n = \frac{1}{n^2} ,$$
is neither arithmetic nor geometric, as it is not possible to express it in the required form. 

## Sequences \\\\ Monotonic sequences: increasing or decreasing behaviour

**Definition** (1.3)
A sequence $\left \{ x_n \right \}$ is *increasing* if its elements satisfy 
$$ x_1 \leq x_2 \leq x_3 \leq \dots $$
and *decreasing* if they satisfy 
$$ x_1 \geq x_2 \geq x_3 \geq \dots  .$$
If the inequalities are all strict then the sequence can be called *strictly increasing* or *strictly decreasing* as appropriate.

### Proving monotonicity, i.e. increasing or decreasing behaviour

Two approaches ...

* Examine the difference between consecutive terms, i.e. $a_{n+1} - a_n$ and then try to establish one of the inequalities
$$ a_{n+1} - a_n \geq 0 \quad \text{ or } \quad a_{n+1} - a_n \leq 0 .$$

* Examine the quotient of consecutive terms, 
$$ \frac{a_{n+1}}{a_n} ,$$
and try to establish one of the inequalties 
$$ \frac{a_{n+1}}{a_n} \geq 1 \quad \text{ or } \quad \frac{a_{n+1}}{a_n} \leq 1 .$$

* Strict inequalities here will establish the strict version of increasing / decreasing as appropriate.

**Example** (1.6)
Investigate the sequence $\{ a_n \}$ defined by 
$$ a_n = \frac{5^n}{n!},$$
and describe its increasing / decreasing behaviour.

*NB: $n!$ is the factorial of $n$, defined by,* 
$$n! = n \times (n-1) \times (n-2) \times  \dots \times 3 \times 2 \times 1 .$$

Ivestigate by computing some values...

<div class="compute"><script type="text/x-sage">
list_plot([(5^n)/factorial(n) for n in range(5)])
</script></div>

and then **prove** it.

The above computation is performed by a [Sage](http://www.sagemath.org) cell. In Matlab, use the `plot` command.

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
