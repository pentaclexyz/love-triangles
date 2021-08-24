https://raoulm.home.xs4all.nl/fractals/Fractals/Fractals.html


### Fractals 

Python code to create a Julia and a Mandelbrot fractal.

Runs from the command line on Mac OSX.

I also tested it on Ubuntu: after installing python-tk through the Synaptic package manager, it runs.


### Set up

```$ git clone git@github.com:pentacledotai/fractals.git```


### Run

```
> python JuliaInPythonAndTk.py
```


Fractal functions

The colour of every pixel in the picture is a measure of the number of iterations that a recursive function was run for that coordinate, until it overshot a pre-set limit or reached a pre-set maximum number of iterations.


The function for the Julia set is f(n) = f(n)2 + c, with n and c as complex numbers. The number n is the current coordinate, the number c is a constant. Complex numbers are written like 3+2i, which is plotted on a graph as a coordinate (3,2). The ‘imaginary unit’ i has the property that i2 = -1, which makes it possible to do algebra with it.

For every pixel in the pic, its coordinate is used as n1 to start the iteration.


To find the number of iterations for coordinate (2,1) in the picture, take n=2+1i and c=1+1i:

f(n1) = (2+1i)x(2+1i)+(1+1i), which is 4 + 4i + 2i2 + 1 + 1i, which is 4 + 5i.

f(n2) = (4+5i)x(4+5i)+(1+1i), which is 16 + 40i + 25i2 + 1 + 1i, which is -8 + 41i.

Etcetera, until a limit is reached (see xl/xh/yl/yh and maxiter in the Julia code).


In the Julia code, the above is translated into this:

an = a*a + b*b*ii + e

bn = a*b + a*b + f

With an and bn being the new value for a and b in each iteration, and e and f for 1 and 1 in c=1+1i.


The rest of the code is mostly to project the cartesian coordinates on window coordinates, and to map iteration counts on colours.


For the Mandelbrot set, the function is f(n) = f(n)2 + z, with z being the current coordinate.

For Julia, c is the same for every pixel in the picture. For Mandelbrot z is the current coordinate, so z is different for every pixel in the picture.
