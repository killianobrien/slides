% 6G5Z3001_1314 \\\\ Mathematical Methods
% Killian O'Brien
% Oct 2013
$\newcommand{\pderiv}[2]{\frac{\partial #1}{\partial #2}}
\newcommand{\ppderiv}[2]{\frac{\partial^2 #1}{\partial #2}}$

# Multi-variable calculus

## Multi-variable calculus \\\\ Chain Rule examples

Use the chain rule to solve the following problems (taken from Schaum's Calculus Chapt. 49)

1. Consider a function $f$ defined on points in the plane. Translate the expression 
$$ \left ( \frac{\partial f}{\partial x} \right )^2 + \left ( \frac{\partial f}{\partial y} \right )^2$$
into polar coordinates.

2. Consider a right-circular cone of height 15cm and radius 10cm. Suppose that the height is increasing at a rate of 0.2cm/min and the radius is decreasing at a rate of 0.3cm/min. How fast is the volume of the cone changing at this moment?

3. Consider a cylinder of height 8cm and radius 6cm. Suppose that the height is decreasing at a rate of 0.4cm/min and the radius is increasing at a rate of 0.4cm/min. How fast is the volume of the cone changing at this moment? How about the surface area? 

4. Consider a particle moving in the plane whose $x$ and $y$ coordinates are given by 
$$x(t) = 2+3t, \quad y(t)=t^2 + 4 ,$$
where $x$ and $y$ are measure in centimetres and $t$ is measured in seconds. At what rate is the distance of the particle from the origin changing at time $t=1$. 

<div class="compute"><script type="text/x-sage">

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


[`cloud.sagemath.com`](https://cloud.sagemath.com).
 --->
