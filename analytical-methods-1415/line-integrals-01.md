% 6G5Z3001_1415 \\\\ Mathematical Methods
% Killian O'Brien
% Nov 2014
$\newcommand{\pderiv}[2]{\frac{\partial #1}{\partial #2}}
\newcommand{\ppderiv}[2]{\frac{\partial^2 #1}{\partial #2}}$

# Multi-variable calculus

## Multi-variable calculus \\\\ Line integrals (sec. 1.11)

An expression of the form, 
$$
L = P(x,y) \, dx + Q(x,y) \, dy ,
$$
is called a *linear differential form*  in the variables $x$ and $y$. Recall that for functions of a single variable we met integrals of the form
$$
I = \int_a^b \, f(x) \, dx ,
$$
which involved integrating the function $f$ over the interval from $x=a$ to $x=b$. 

Similar integrals occur in the calculus of two-variable functions. These integrals take place over a line, or curve, $C$ in the $xy$-plane. Their integrands are linear differential forms and they take the form
$$
I = \int\limits_C \, P(x,y) \, dx + Q(x,y) \, dy .
$$
One way of evaluating such integrals is to use a specification of the curve $C$ to reduce $I$ to an integral of a one-variable function, as the following example illustrates. 

### Example 1.14

We will integrate the form 
$$
L = 10 x^2 y \, dx + (3x+2y)\, dy ,
$$
along the curve 
$$
C: \quad y=x^2 ,
$$
from the point $(0,0)$ to the point $(1,1)$. 

## Multi-variable calculus \\\\ Line integrals (sec. 1.11)

### Theorem 1.4 (Properties of line integrals)

These properties are all generalizations of equivalent properties that hold for definite integrals of functions of a single variable. 

* Line integrals are linear, and in particular 
$$
\int\limits_{C} \, P(x,y) \, dx + Q(x,y) \, dy = \int\limits_{C} \, P(x,y) \, dx + \int\limits_{C} Q(x,y) \, dy .
$$

* If $C$ is a curve and $C'$ is the same curve, but running in the \emph{opposite} direction, then for any linear differential form $L$,
$$
\int\limits_{C} \, L = - \int\limits_{C'} \, L .
$$

* If a path is split into components then the integral over the path is the sum of the integrals over the components. For example if $AB$ denotes a curve from a point $A$ to a point $B$, $BC$ denotes a curve from $B$ to $C$ and $AC$ denotes the union of the two curves, then for any linear differential form $L$ 
$$
\int\limits_{AC} \, L = \int\limits_{AB} \, L + \int\limits_{BC} \, L .
$$

### Example 1.15

Integrate the linear differential form 
$$
L = 10 x^2 y \, dx + (3x + 2y) \, dy
$$
from the point $A=(0,0)$ to the point $B=(1,1)$ along the path made up of the two straight line segments $AD$ and $DB$, where $D$ is the intermediate point $D=(1,0)$.

## Multi-variable calculus \\\\ Line integrals along parametrised paths (sec. 1.12)

When the path of integration is *parametrised*, i.e. the $x$ and $y$ coordinates are given as functions of an independent variable $t$, then a line integral over such a path can often be evaluated by converting everything to the independent variable $t$ to obtain a standard single-variable integral. 

### Example 1.16

Evaluate the line integral
$$
I= \int\limits_{C} \, x^2 \, dy - yx \, dx,
$$
where $C$ is the semi-circular path, of radius $1$ and  traversed clockwise, from the point $(-1,0)$ to $(1,0)$.

 
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
