# Threejs-VR-Physics (under construction)

Explore computational physics in Threejs VR

## Threejs-VR-Physics Pages

[https://physicslibrary.github.io/Threejs-VR-Physics/](https://physicslibrary.github.io/Threejs-VR-Physics/)

## System requirements

Oculus Quest recommended (6DoF headset/controllers).<br>

Oculus Browser (tested Quest Update >16.0).<br>

## Mass on a spring.

<img src="images/1.png" width="480">

The two green wireframe boxes on the lower right are Touch controllers. For "Mass on a spring",
they do not do anything except to help see hands in VR. The green box on the left is the mass
at x = -0.5m with an arrow showing the force of the spring on the mass as a function of position.

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

With an Oculus Quest, open Oculus Browser and go to link (and "Enter VR"):<br>

[https://physicslibrary.github.io/Threejs-VR-Physics/examples/webxr_vr_mass_on_a_spring.html](https://physicslibrary.github.io/Threejs-VR-Physics/examples/webxr_vr_mass_on_a_spring.html)

Webxr_vr_mass_on_a_spring.html uses a subset of three.js r115 (three.module.js, VRButton.js, and BoxLineGeometry.js). Complete three.js can be downloaded from threejs website.

Tutorial on how to make Threejs-VR-Physics on a Raspberry Pi is the same as "Making Threejs-WebXR-67P (experimental Feb 10, 2020)":

[https://github.com/Physicslibrary/Threejs-WebXR-67P](https://github.com/Physicslibrary/Threejs-WebXR-67P)

## References

Pieter B. Visscher, Fields and Electrodynamics, John Wiley & Sons (1988).

Harvey Gould and Jan Tobochnik, An Introduction to Computer Simulation Methods, Addison-Wesley (1996).

[https://threejs.org/](https://threejs.org/)

<br>Copyright (c) 2020 Hartwell Fong
