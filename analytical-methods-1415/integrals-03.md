% 6G5Z3001_1314 \\\\ Mathematical Methods
% Killian O'Brien
% Nov 2013
$\newcommand{\pderiv}[2]{\frac{\partial #1}{\partial #2}}
\newcommand{\ppderiv}[2]{\frac{\partial^2 #1}{\partial #2}}$

# Multi-variable calculus

## Multi-variable calculus \\\\ Multiple integration examples

1. Evaluate the integral 
$$\iint\limits_{R} y \, dA,$$
where the integral is taken over the region $R$ in the plane, bounded by the four curves 
$$y=(x+1)^2, \, \, x=y-y^3, \, \, x=-1, \,\, y=-1.$$
(See [this](http://tinyurl.com/otx39s7) Sage cell for a plot of these boundary curves)

1. Evaluate 
$$\iint\limits_{R} 3x \, dA ,$$
where the region of integration $R$ is the region in the upper half-plane bounded by the circles of radii 1 and 2, centred on the origin.


1. Evaluate the integral 
$$\iint\limits_{D} \sqrt{x^2 + y^2} \, dx \, dy ,$$
where the integral is taken over the disc $D$ in the $xy$-plane of radius 5. 

2. Evaluate the following triple integral
$$ \iiint\limits_{R} \, z \, dx \, dy \, dz ,$$
where the integral is taken over the region $R$ of $xyz$-space consisting of the upper-half ($z \geq 0$) of the ball of radius 1, centred on the origin.





 
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
