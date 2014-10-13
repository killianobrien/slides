% 6G5Z3001_1415\\\\ Mathematical Methods
% Killian O'Brien
% Oct 2014
$\newcommand{\pderiv}[2]{\frac{\partial #1}{\partial #2}}
\newcommand{\ppderiv}[2]{\frac{\partial^2 #1}{\partial #2}}$

# Multi-variable calculus

## Multi-variable calculus \\\\ Total differentials & small increments formula (sec. 1.7)

Now we consider the effect on a function $f$ of changing all its arguments simultaneously. We consider the two-variable case which has a straightforward generalization to functions of more than two variables. 

### Definition 1.3 (Total differential)
Let $f$ be a function of the two independent variables $x$ and $y$. Let $\Delta f$ be the change in $f$ brought about by the changes, $\Delta x$ and $\Delta y$, in $x$ and $y$, i.e.
$$
\Delta f = f(x + \Delta x, y + \Delta y) - f(x,y) .
$$
Suppose that there exist functions $A$ and $B$ of $x$ and $y$ such that 
$$
\Delta f = A(x,y) \Delta x + B(x,y) \Delta y + \lambda \Delta x + \mu \Delta y,
$$
such that $\lambda, \mu \to 0$ as $\Delta x , \Delta y \to 0$. Then we say that $f$ has a *total differential* $df$ and we write 
$$
df = A(x,y)\, dx + B(x,y) \, dy. 
$$

### Example 1.6

Consider the function $f$ defined by 
$$
f(x,y) = x^2 + xy.
$$
Show that this has a total differential.

## Multi-variable calculus \\\\ Total differentials & small increments formula (sec. 1.7)

### Theorem 1.2 (Total differentials)

If the partial derivatives $\frac{\partial f}{\partial x}$ and $\frac{\partial f}{\partial y}$ exist and are continuous then 
$$
\Delta f = \frac{\partial f}{\partial x} \, \Delta x +\frac{\partial f}{\partial y} \, \Delta y + \lambda ( \Delta x + \Delta y ),
$$
where $\lambda \to 0$ as $\Delta x , \Delta y \to 0$, i.e. the function $f$ has a total differential and 
$$
d f = \frac{\partial f}{\partial x} \, d x +\frac{\partial f}{\partial y} \, dy.
$$

![Fig. Changes on the surface $z=f(x,y)$](tot-diff.png)

*Proof.* From the diagram we express $\Delta f$ as follows,
$$
\begin{align}
\Delta f 
&= f(x + \Delta x, y+ \Delta y) - f(x,y),\\
&= CF - AB,\\
&= DF, \\
&= GH + EF.
\end{align}
$$

Now as $\Delta x$ becomes small and approaches 0, the curve $BH$, which lies on the surface, is approximately a straight line. And so
$$
\begin{align}
GH &\approx BG \tan (\angle GBH ) ,\\
&= \Delta x \, \tan (\angle GBH ),\\
&\approx \Delta x \, \frac{\partial f}{\partial x}.
\end{align}
$$

In the same way, examining the 'triangle' $EHF$ shows that 
$$
EF \approx \Delta y \, \frac{\partial f}{\partial y}.
$$
And so
$$
\Delta f \approx \Delta x \, \frac{\partial f}{\partial x} + \Delta y \, \frac{\partial f}{\partial y},
\label{E:smallincs}
$$
and as $\Delta x, \Delta y \to 0$ the error in this approximation tends to 0, therefore
$$
d f = \frac{\partial f}{\partial x} \, d x +\frac{\partial f}{\partial y} \, dy,
$$
as required.

## Multi-variable calculus \\\\ Total differentials & small increments formula (sec. 1.7)

### Definition 1.4 (Small increments formula)

The equation is called the *small increments formula* and it shows how the partial derivatives of a function can be used to approximate the change in value of the function brought about by changes in the value of the arguments of the function. In general, for a function $f$ of $n$ variables $x_1, \dots , x_n$ the small increments formula is 
$$
\Delta f \approx \sum_{i=1}^n \Delta x_i \, \frac{\partial f}{\partial x_i}.
$$

### Examples 1.7 & 1.8 

Discuss on visualizer.

## Multi-variable calculus \\\\ Chain Rule & Jacobians (sec. 1.8)

### Recall chain rule for functions of a single variable

Suppose that $y=f(x)$ and $x = g(t)$. Then
$$
\frac{dy}{dt} = \frac{df}{dx} \, \frac{dg}{dt},
$$
or in alternative notation 
$$
y'(t) = f'(x(t)) \, g'(t) .
$$
What we seek now is a chain rule functions of more than one variable. 

## Multi-variable calculus \\\\ Chain Rule & Jacobians (sec. 1.8)

Again we shall consider the general two-variable situation and then describe the extension to any number of variables. So suppose we have two coordinate systems for $\mathbb{R}^2$, $(x,y)$ and $(s,t)$ say, and that these are related by functions 
$$x = u(s,t) , \quad y=v(s,t).$$
Then if we have a function 
$$ z = f(x,y),$$
that defines $z$ as a function of $x$ and $y$, we can also consider $z$ as a function of $s$ and $t$, i.e.
$$ z = f \big ( u(s,t), v(s,t) \big ). $$
The small increments formula applied to $z=f(x,y)$ gives us 
$$ 
\Delta z \approx  \frac{\partial f}{\partial x} \, \Delta x + \frac{\partial f}{\partial y} \, \Delta y ,
$$
and dividing across by $\Delta s$ gives 
$$ 
\frac{\Delta z}{\Delta s} \approx  \frac{\partial f}{\partial x} \, \frac{\Delta x}{\Delta s} + \frac{\partial f}{\partial y} \, \frac{\Delta y}{\Delta s} .
$$
When the limit of this approximation is taken as $\Delta s \to 0$ it becomes exact and we get 
$$ 
\frac{\partial z}{\partial s} =  \frac{\partial f}{\partial x} \, \frac{\partial x}{\partial s} + \frac{\partial f}{\partial y} \, \frac{\partial y}{\partial s} \label{E:chainrule1}. 
$$
A similar treatment of the small increments formula using the change $\Delta t$ produces 
$$ 
\frac{\partial z}{\partial t} =  \frac{\partial f}{\partial x} \, \frac{\partial x}{\partial t} + \frac{\partial f}{\partial y} \, \frac{\partial y}{\partial t} . \label{E:chainrule2} 
$$
These last two equations are together referred to as the *chain rule* equations. They describe the relationship between the derivatives, $\frac{\partial z}{\partial s}$, and $\frac{\partial z}{\partial t}$, of $z$ with respect to the new variables $s,t,$ with the derivatives with respect to the old variables $x,y$.

### Definition 1.5 (Chain rule for two-variable functions)
If 
$$ 
z = f(x,y) = f \big ( u(s,t),v(s,t) \big ),
$$
then 
$$
\begin{align}
\frac{\partial z}{\partial s} &=  \frac{\partial f}{\partial x} \, \frac{\partial x}{\partial s} + \frac{\partial f}{\partial y} \, \frac{\partial y}{\partial s}, \\
\frac{\partial z}{\partial t} &=  \frac{\partial f}{\partial x} \, \frac{\partial x}{\partial t} + \frac{\partial f}{\partial y} \, \frac{\partial y}{\partial t} . 
\end{align}
$$

This has the obvious generalization to the case of $n$-variable functions, for any $n \geq 1$.

### Definition 1.6 (Chain rule for $n$-variable functions)
If 
$$ 
z = f(x_1,x_2, \dots ,x_n), 
$$
and the variables $x_i$ are in turn related to the new coordinates $s_1, s_2, \dots ,s_n$ by the functions 
$$ 
x_i = u_i(s_1, \dots ,s_n),
$$
then 
$$
\begin{align}
\frac{\partial z}{\partial s_i} = \sum_{j=1}^n \frac{\partial f}{\partial x_j} \, \frac{\partial x_j}{\partial s_i}.
\end{align}
$$

### Example 1.10 
Translate the expression
$$\mathcal{F} = x \, \pderiv{f}{x} + y \, \pderiv{f}{y} , 
$$
into polar coordinates.

## Multi-variable calculus \\\\ Chain Rule & Jacobians (sec. 1.8)

### The Jacobian

The chain rule equations can be expressed very neatly in matrix form, for instance in the two-variable case they become the single matrix equation
$$
\left (
\begin{array}{cc}
\pderiv{f}{s} & \pderiv{f}{t}
\end{array} \right ) 
= \left (
\begin{array}{cc}
\pderiv{f}{x} & \pderiv{f}{y}
\end{array} \right ) 
\, \left (
\begin{array}{cc}
\pderiv{x}{s} & \pderiv{x}{t} \\
\pderiv{y}{s} & \pderiv{y}{t}
\end{array} \right ) ,$$
or expressed the other way round as
$$
\left (
\begin{array}{cc}
\pderiv{f}{x} & \pderiv{f}{y}
\end{array} \right ) 
= \left (\begin{array}{cc}
\pderiv{f}{s} & \pderiv{f}{t}
\end{array} \right ) 
\, \left (
\begin{array}{cc}
\pderiv{x}{s} & \pderiv{x}{t} \\
\pderiv{y}{s} & \pderiv{y}{t}
\end{array} \right )^{-1}, $$
(assuming of course that this inverse matrix exists).

The $2 \times 2$ matrix of partial derivatives of the transformation between the coordinate systems $(x,y)$ and $(s,t)$ here is called a Jacobian matrix. Also important is the determinant of this matrix which is called the Jacobian determinant and denoted as 
$$ 
\frac{\partial (x,y)}{\partial (s,t)} = \left | \mathcal{J} \right | = \left |
\begin{array}{cc}
\pderiv{x}{s} & \pderiv{x}{t} \\
\pderiv{y}{s} & \pderiv{y}{t}
\end{array} \right | .
$$
We will make use of the Jacobian determinant later in section \ref{S:coordchange} when changing coordinate systems in various integrals. The Jacobian has the natural generalisation to any number of variables, as in the following definition.

### Definition 1.7 (Jacobian matrix / determinant)
Let $n \in \mathbb{Z}$, $n \geq 1$. The Jacobian matrix of the transformation from the (old) coordinates $(x_1, \dots x_n)$ for $\mathbb{R}^n$ to the (new) coordinate system $(u_1 , \dots u_n)$ is the matrix 
$$ 
\mathcal{J} = \left ( \pderiv{x_i}{u_j} \right ),
$$
i.e. the entry in the $i^{th}$ row and $j^{th}$ column is $\pderiv{x_i}{u_j}$.

The Jacobian determinant refers to the determinant of this matrix. Note that some authors will use the term *Jacobian* to refer to the determinant while others may use it to refer to the matrix. Care should be taken to take the correct meaning from the context.

## Suggested activities

* Read the rest of section 1.8 in notes and work on Exercises 1.2 & 1.3 
* Finish exercises 1.1 if you have not already done so!

* *Schaum's Outlines of Calculus* by Ayres & Mendelson: Chapter 49 Total Differential, differentiability, chain rules.
	* includes lots of extra practice problems - some with solutions. 
 

 
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
