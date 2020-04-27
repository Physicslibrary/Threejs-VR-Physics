# Threejs-VR-Physics (under construction)

Explore computational physics in Threejs VR

## System requirements

Oculus Quest recommended (6DoF headset/controllers).<br>

Oculus Browser (tested with Quest Update >16.0).<br>

## Mass on a spring.

Mass on a spring is solved using Euler method.<br>

<pre>

F = m * a             (Newton's second law of motion)

a = F/m               (1)

F(spring) = -k * x    (Hooke's law for spring) (2)

a = -k * x / m        (put 2 into 1)

dv/dt = -k * x / m    (aceleration = dv/dt, change in velocity with time) (3)

v = dx/dt             (velocity = dx/dt, change in distance with time) (4)

Equations 3 and 4 are usually solved using calculus. Since a web browser can multiply and add
floating points very fast, make 3 and 4 finite-difference equations:

(vnew - vold)/dt = -k * xold / m       (3)

vnew = vold + (-k * xold / m) * dt     (5)

vnew = (xnew - xold) / dt              (4)

xnew = xold + vnew * dt                (6)

Put 5 and 6 into javascript code with initial conditions:

var k = 0.2;    // spring constant
var mass = 2;

var xnew, xold, vnew, vold;
xold = 0.5;
vold = 0;
var dt = 0.05;  // time step

</pre>

In Oculus Quest, open Oculus Browser and go to link:<br>

## References

Pieter B. Visscher, Fields and Electrodynamics, John Wiley & Sons (1988).

Harvey Gould and Jan Tobochnik, An Introduction to Computer Simulation Methods, Addison-Wesley (1996).

[https://threejs.org/](https://threejs.org/)

<br>Copyright (c) 2020 Hartwell Fong
