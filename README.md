# Spherical-Pendulum-Simulation
In this project I solve for the trajectory of a Spherical Pendulum using the RKF45 method.

The Spherical Pendulum is the 3D analogue of the commonly seen pendulum. That is to say, the pendulum bob is allowed to move on the 3d surface of a sphere while still being subjected to the force of gravity. Spherical coordinates (r, theta, phi) are maybe the easiest way to interpret the motion. r defines the length of the pendulum rod and is fixed constant ( which is why the pendulum bob always lies exactly on a sphere of radius r). Theta is the angle the rod makes with the vertical z axis, and phi is the angle made with the projection of the rod into the x-y plane.

RKF45 is the Runge-Kutta-Fehlberg adaptive method of solving a system of 1d differential equations. Being adaptive means that the step size used to update the position of the bob changes (gets larger or smaller) such that the error in the numerical solution is always within some bound. This is the advantage of using this method over Runge-Kutta 4 (RK4). In RK4 the step size is kept fixed, so the errors can grow to be larger under certain circumstances. 

Because of the nature of the adaptive method used in this code, the animation does not move in constant time steps (t) but in time steps dt that continuasly adapt to keep the error fixed below 1E-6. So, while the actually trajectory of the spherical pendulum is reproduced, the animation looks to slow down at parts where many very small time steps were taken, only to speed up again when the time steps grow larger.

The actual differential equation which describes the motion was derived from the euler-lagrangian equation and detailed somewhat below:

The Lagrangian is defined as: 

<a href="https://www.codecogs.com/eqnedit.php?latex=L&space;=&space;T&space;-&space;U" target="_blank"><img src="https://latex.codecogs.com/gif.latex?L&space;=&space;T&space;-&space;U" title="L = T - U" /></a>
