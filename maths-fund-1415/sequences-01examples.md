% 6G4Z3001_1314 \\\\ Mathematics Fundamentals
% Killian O'Brien
% Oct 2013
# Sequences \\\\ Examples

## Sequences \\\\ Examples \\\\ Increasing / decreasing

Try the difference or ratio method (or both) on the following sequences to determine their increasing/decreasing nature

* $\left \{ y_n \right \}$ where $y_n = \frac{1}{\sqrt{n^2+1} - n}$
* $\left \{ s_n \right \}$ where $s_n = \frac{3n}{4n+1}$.
* $\left \{ x_n \right \}$ where $x_n = \frac{2^n}{3^n - 4}$.
* $\left \{ f_n \right \}$ where $f_n = \frac{n^2}{2^n}$

Confirm this behaviour and investigate their convergence using the Sage cell ...

<div class="compute"><script type="text/x-sage">
list_plot([(5^n)/factorial(n) for n in range(5)])
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



 --->
