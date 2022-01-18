---
layout: post
title: "Governing Equations Navier-Stokes"
subtitle: ""
# date: 2020-01-26 23:45:13 -0400
# The big banner behind the blog post title
background: '/img/posts/01.jpg'
---

Imagine a fluid flowing through space. This could be the air circulating in your room, water flowing through a pipe, oil spilling in the ocean, etc. We want to be able to model these types of fluid motion, but how? In contrast to solid bodies, fluids can change their shape and most likely have different physical properties throughout space *and* time (temperature, pressure, velocity, etc.). 

## Control Volume


Compared to solid bodies undergoing translational motion, At first this may be tricky to think of when comparing how we solve for properties of solid things; if you throw a rock (undergoing translational motion), it will stay the same size and shape, and the velocity at each point of that rock is the same. 

## Derivation of the Material Derivative 

Also known as the 'Substantial Derivative".

The fluid element is flowing through cartesian space where the unit vectors along the $$x$$, $$y$$, and $$z$$ axes are $$ \boldsymbol{i} $$, $$ \boldsymbol{j} $$, and $$ \boldsymbol{k} $$, respectfully.

![Fluid Element](/img/posts/cfd-equations/fluid-elem.png)
<img src="/img/posts/cfd-equations/fluid-elem.png" />

The vector field of a fluid flow is given by

$$
\boldsymbol{V} = u\boldsymbol{i} + v\boldsymbol{j} + w\boldsymbol{k}
$$

where $$ u(x, y, z, t) = \frac{dx}{dt} $$ is the velocity component in the $$x$$-direction and along the $$ \boldsymbol{i} $$ unit vector. $$ v(x,y,z,t) = \frac{dy}{dt} $$ is the velocity component in the $$y$$-direction and along the $$ \boldsymbol{j} $$ unit vector. Finally, $$ w(x,y,z,t) = \frac{dz}{dt} $$ is the velocity component in the $$z$$-direction and along the $$ \boldsymbol{k} $$ unit vector. 

Notice that all the components of the velocity are functions of space ($$x, y, z$$) and time $$t$$. This is true in a general *unsteady* flow, meaning the fluid properties don't only change as it moves along space but also change with time. For example, if we just look at only one point in space (not moving around) the conditions of the flow through that particular point will vary as time passes. This can be shown mathematically as 

$$ \frac{d(property)}{dt} \ne 0 $$

where $$property$$ is the fluid's property in question which can be velocity, temperature, density, etc. Obviously, if the flow is *steady* then the change of that property in respect to time (and still within the same location in space) will be $$0$$.

So, now that we have established that the fluid element's velocity changes with time and space let's look at another property that also will change through time and space, say density $$\rho(x, y, z, t)$$.

