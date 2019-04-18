---
layout: post
title:  "Vibration of a Circular Membrane Part 2: Solving the Wave Equation"
date:   2019-04-18 01:21:23 +0900
categories: math
---

Last time we ended with the Laplacian of polar coordinates, namely

$$
\Delta u(x,y)=\nabla^{2}u=\frac{\partial^{2}u}{\partial x^{2}}+\frac{\partial^{2}u}{\partial y^{2}}=\frac{\partial^{2}u}{\partial r^{2}}+\frac{1}{r}\frac{\partial u}{\partial r}+\frac{1}{r^{2}}\frac{\partial^{2}u}{\partial\theta^{2}}
$$

In this post, I will introduce you Wave equation, 2-dim wave equation
and the solution for the case where $$u(x,y,t)=u(r,t)$$. i.e., $$u$$
is circularly symmetric (radially symmetric).

## 1.Two Dimensional Wave Equation

How would one describe the movement of a wave? More explicitly, suppose
that you have an infinitely thin rubber cloak. This piece of rubber
is extremely

precise and tensionly even, so that every molecule(or, infinitesimal
amount of local part of the cloak) of the rubber is being pulled by
the same force, every time, evenly.

Notice that if the rubber cloak changes its form with ''meaningfully
big amount'', the tension would not be even, thus we need the assumption
that total changes of the wave as time passes is not large.

For every point of the cloak, it moves only if there are some curvature
at that point. We can think of this as some kind of a trampoline,
since trampoline only pushes things up when it has a positive
second derivative(i.e., positive curvature). Also, one can educatedly guess
that the second derivative of the trampoline is proportional to the
amount of force it will provide

upward. (You can get this result much more rigorously, but that's
rather simple and you probably already know why it works.) Therefore,
one has

$$
F_{z}=C(\frac{\partial^{2}u}{\partial x^{2}}+\frac{\partial^{2}u}{\partial y^{2}})
$$

where $$F_{z}$$is force (more precisely, force per area) caused by
the rubber cloak in upward direction. We will use the famous **Newton's
law** to get

$$
\frac{\partial^{2}u}{\partial t^{2}}=c^{2}(\frac{\partial^{2}u}{\partial x^{2}}+\frac{\partial^{2}u}{\partial y^{2}})
$$

This is the **Two Dimensional Wave equation**.

## 2. Radially Symmetric, Finite Wave Equation
Taking the Laplacian for polar coordinate, we have

$$
\frac{\partial^{2}u}{\partial t^{2}}=c^{2}(\frac{\partial^{2}u}{\partial r^{2}}+\frac{1}{r}\frac{\partial u}{\partial r}+\frac{1}{r^{2}}\frac{\partial^{2}u}{\partial\theta^{2}})
$$

Since we are considering radially symmetric case, we have

$$
\frac{\partial^{2}u}{\partial t^{2}}=c^{2}(\frac{\partial^{2}u}{\partial r^{2}}+\frac{1}{r}\frac{\partial u}{\partial r})
$$

We will now consider $$u$$ as a function with two variables, $$r$$ and
$$t$$.

But this is not enough to fully solve the wave equation. As all differential
equations, one needs initial conditions and boundary conditions. In this
case, we will have a condition that describe

a finite wave. That is;

$$
u(a,t)=0\text{ for some }a>0
$$

Also, the starting state of the wave is also known, because we need
at least somewhere to start with.
$$
u(r,0)=f(r),\frac{\partial u}{\partial t}(r,0)=g(r)
$$

So we know the position and velocity of the overall cloak at time
$$t=0$$.

Now to solve the equation, we will use separation of variables $$u(r,t)=R(r)T(t)$$.

$$
\frac{T''}{c^{2}T}=\frac{1}{R}(R''+\frac{1}{r}R')
$$

The left hand side and the right hand side has the equality, but with
different variables. This must mean that they equal to some constant
$$-\lambda^{2}$$. The reason why it is negative is because we expect

non-trivial solutions, and that if it is positive, for fixed $$r$$
we have exponential solution. This is contradictory because physically
we expect finite solution for arbitrary given time(of course,

more rigorous argument can be made. We will not mention it now.Perhaps
later? lol). We now have full description of equations we need to
solve.

$$
rR''+R'+\lambda^{2}rR=0,R(a)=0
$$

$$
T''+c^{2}\lambda^{2}T=0
$$
## 3. Bessel Functions
The first equation is strange. Specifically, the differential equation
$$
xy''+y'+xy=0
$$

is not the kind that we know of. We can assume it's existence and
use Taylor expansion

$$
y=\sum_{k=0}^{\infty}a_{k}\frac{x^{k}}{k!},(k+1)a_{k+1}=-a_{k-1}
$$

Indeed, such function exists and are called ''Bessel Functions''.
There are two solution to above differential equation, and one can
easily see that by the Taylor expansion,

since the parity of the coefficients' index doesn't change. There are
actually a lot of different kinds of Bessel function and we will talk
about it in different post.

$$
J_{0}(x)=\sum_{k=0}^{\infty}\frac{(-1)^{k}}{k!^{2}}(\frac{x}{2})^{2k}
$$

$$
Y_{0}(x)=\frac{2}{\pi}J_{0}(x)\log(\frac{x}{2})-\frac{2}{\pi}\sum_{k=0}^{\infty}\frac{(-1)^{k}}{k!^{2}}(\frac{x}{2})^{2k}\psi(k+1)
$$

Let's just realize that these are called ''Bessel functions of order
0 of the first and second kind''. Just in case you are unfamiliar
with function $$\psi(k)$$, they satisfy

$$
\psi(n+1)=-\gamma+\sum_{m=1}^{n}\frac{1}{n}
$$

where $$\gamma$$ is Eular- Mascheroni constant.

We now have the solution for $$R$$ part. Namely that

$$R(r)=c_{1}J_{0}(\lambda r)+c_{2}Y_{0}(\lambda r)$$

But unfortunately, function $$Y_{0}$$is unbounded near 0. You can see
this by the $$\log(x/2)$$ part in the formula above. Thus, we are left
with the first kind.

Now using boundary condition $$R(a)=0$$, it must imply that $$J_{0}(\lambda a)=0$$.
Now the set of possible $$\lambda$$ one can take is now only countably
many,because there are countably many

solutions to the equation $$J_{0}(x)=0$$ and one can arrange them in
order

$$
\alpha_{1}<\alpha_{2}<\alpha_{3}\cdots
$$

Immediately $$\lambda$$'s are now arrangeable in order

$$
\lambda_{n}=\frac{\alpha_{n}}{a}
$$

These solutions now uniquely determines $$T,R$$, and therefore one
can write the full solution in the form of the following.

$$
u(r,t)=\sum_{n=1}^{\infty}(A_{n}\cos(c\lambda_{n}t)+B_{n}\sin(c\lambda_{n}t))J_{0}(\lambda_{n}r)
$$

Now we use initial conditions to determine $$A_{n}$$and $$B_{n}$$. taking
$$t=0$$ gives

$$
u(r,0)=f(r)=\sum_{n=1}^{\infty}A_{n}J_{0}(\lambda_{n}r)
$$

This looks familiar. We already know that, if it was the case for
$$\sin(nr)$$ instead of $$J_{0}(\lambda_{n}r)$$, way to determine $$A_{n}$$.
That was done by using fourier transformation! Using similar method
as in

fourier series, coefficients are actually determined as

$$
A_{n}=\frac{2}{a^{2}J_{1}(\alpha_{n})}\int_{0}^{a}f(r)J_{0}(\lambda_{n}r)rdr
$$

Where $$J_{1}(x)=\sum_{k=0}^{\infty}(-1)^{k}(x/2)^{2k+1}/k!(k+1)!$$.

Done with $$A_{n},$$as for $$B_{n},$$

$$
\frac{\partial}{\partial t}u(r,0)=g(r)=\sum_{n=1}^{\infty}c\lambda_{n}B_{n}J_{0}(\lambda_{n}r)
$$

Which looks similar to the first case and indeed,

$$
c\lambda_{n}B_{n}=\frac{2}{a^{2}J_{1}(\alpha_{n})}\int_{0}^{a}g(r)J_{0}(\lambda_{n}r)rdr
$$

Therefore we have the wanted solution for two-dimensional, finite,
radially symmetric wave equation.
