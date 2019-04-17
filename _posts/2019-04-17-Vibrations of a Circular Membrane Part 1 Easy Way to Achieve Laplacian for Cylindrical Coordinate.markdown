---
layout: post
title:  "Vibrations of a Circular Membrane Part 1: Easy Way to Achieve Laplacian for Cylindrical Coordinate"
date:   2019-04-17 11:21:23 +0900
categories: math
---
As a freshman, one is indirectly forced to take a lot of introductory
courses before taking PDE course. However, it isn't always mandatory,
so I took the class anyway.

Most of the topics, theorems, and problems are straightforward and
intuitive. This turned out to be rather biased, because the only reason
it felt that way was because that

I already had some background study(mainly by quantum mechanics and
analytical number theory). This post was made because I was ''organizing''
my study on this specific topic, on Polar PDE.

One of the thing that is rather tiresome is getting the Laplacian
of cylindrical coordinate. Beforehand, let's quickly brief about the Laplacian
in polar coordinates.

We wish to express $$\Delta u(x,y)$$ with derivatives by $$r$$ and $$\theta$$.
In other words, suppose that
$$
\Delta u=\frac{\partial^{2}u}{\partial x^{2}}+\frac{\partial^{2}u}{\partial y^{2}}=A\frac{\partial^{2}u}{\partial r^{2}}+B\frac{\partial u}{\partial r}+C\frac{\partial^{2}u}{\partial\theta^{2}}+D\frac{\partial u}{\partial\theta}+E\frac{\partial^{2}u}{\partial r\partial\theta}
$$

, how would one determine $$A,B,C,D,E\in \mathbb{R}$$?

Is it even clear that the above statement is true? Is the above variable
$$A,B,C,D,E$$ is constant, or function of $$r,\theta$$ in general? If
one takes the chain rule, it is clear that it is not the case, yet

the above equation holds true for some $$A,B,C,D,E$$ that is function
of $$r$$ and $$\theta$$. One is tempted to use brute force and check
the coefficients, but I came up with non rigorous, but much more fast
and intuitive way.

First, let's only consider the case $$u(x,y)=f(r)g(\theta)$$ . From
now we will abuse notation so that$$f'=\frac{\partial}{\partial r}f(r)$$
, $$g'=\frac{_{\partial}}{\partial\theta}g(\theta)$$ , $$s=\sin(\theta),c=\cos(\theta)$$.
We will use chain rule,

$$
\frac{\partial u}{\partial x}=\frac{\partial u}{\partial r}\frac{\partial r}{\partial x}+\frac{\partial u}{\partial\theta}\frac{\partial\theta}{\partial x}
$$

so that

$$
\frac{\partial u}{\partial x}=fg'(-\frac{y}{r^{2}})+f'g\frac{x}{r}=(\frac{f}{r})(g's)+f'(gc)
$$

Notice that using the equation to itself,

$$
\frac{\partial^{2}u}{\partial x^{2}}=\frac{\partial}{\partial x}(\frac{f}{r})(g's)+\frac{\partial}{\partial x}f'(gc)=(\frac{f}{r^{2}})s(sg')'+(-\frac{f}{r})'sg'c+(-\frac{f'}{r})s(gc)'+f''gc^{2}
$$

$$
=\frac{f}{r^{2}}scg'+\frac{f}{r^{2}}s^{2}g''-(\frac{f'r-f}{r^{2}})scg'-\frac{f'}{r}s(-sg+g'c)+f''gc^{2}
$$

Now here is where beautiful part takes place. When we get $$\frac{\partial^{2}u}{\partial y^{2}}$$,
It is same as substituting $$\cos(\theta)$$ as $$\sin(\theta)$$. But
wait, the derivative part needs to correlate too! Thus we instead
think of taking $$\theta$$ to $$\theta-\pi/2$$. This is consistent.
Also, this means all the ''sc'' above changes it's sign, because
$$\cos(\theta-\pi/2)\sin(\theta-\pi/2)=-\sin(\theta)\cos(\theta)$$.

Thus, one can easily get
$$
\Delta u=\frac{f}{r^{2}}g''+\frac{f'}{r}g+f''g
$$

Since $$\frac{\partial^{2}u}{\partial\theta^{2}}=fg''$$, $$\frac{\partial u}{\partial r}=f'g$$
and $$\frac{\partial^{2}u}{\partial r^{2}}=f''g$$, this simply implies
that $$A=1,$$$$B=1/r$$, $$C=1/r^{2},D=E=0$$.

Because of additivity of derivatives, if one can every ''smooth''
function (in this case, into sum of function in form of $$f(r)g(\theta)$$,
one can gurantee that indeed above equation holds in general. When
we use Seperation of variables to solve PDE problems, this is already
under the assumption, so it is rather safe assumption to make. Also,
most function that we care about has a closed form expression, rather
that is in form of taylor series or fourier series. Either case it
is under the realm of ''Seperation of variables''. However, do notice
that this is not rigirous, and would need much more proof and work
to make it viable for general $$C^{2}$$ functions.

Finally, let's get into the cylindrical coordinates. The relationship
between $$(x,y,z)$$ and $$(r,\theta,z)$$ is

$$
x=r\cos(\theta),y=r\sin(\theta),z=z
$$

we wish to find

$$
\Delta u=\frac{\partial^{2}u}{\partial x^{2}}+\frac{\partial^{2}u}{\partial y^{2}}+\frac{\partial^{2}u}{\partial z^{2}}=A\frac{\partial^{2}u}{\partial r^{2}}+B\frac{\partial u}{\partial r}+C\frac{\partial^{2}u}{\partial\theta^{2}}+D\frac{\partial u}{\partial\theta}+E\frac{\partial^{2}u}{\partial z^{2}}+F\frac{\partial u}{\partial z}+G\frac{\partial^{2}u}{\partial r\partial\theta}+H\frac{\partial^{2}u}{\partial r\partial z}+I\frac{\partial^{2}u}{\partial\theta\partial z}
$$

functions $$A,B,C,D,E,F,G,H,I$$. again, we assume that $$u$$ is ``nice''
in the sense that $$u(r,\theta,z)=\sum f(r)g(\theta)h(z)$$. Using the
same idea, we have

$$
\frac{\partial u}{\partial x}=\frac{\partial u}{\partial r}\frac{\partial r}{\partial x}+\frac{\partial u}{\partial\theta}\frac{\partial\theta}{\partial x}+\frac{\partial u}{\partial z}\frac{\partial z}{\partial x}=(\frac{f}{r})(g's)+f'(gc)
$$

because $$\frac{\partial z}{\partial x}$$=0.

This is same as our previous polar coordinate case, thus immediately
we get

$$
\frac{\partial^{2}u}{\partial x^{2}}+\frac{\partial^{2}u}{\partial y^{2}}=\frac{\partial^{2}u}{\partial r^{2}}+\frac{1}{r}\frac{\partial u}{\partial r}+\frac{1}{r^{2}}\frac{\partial^{2}u}{\partial\theta^{2}}
$$

Therefore we have

$$
\Delta u=\frac{\partial^{2}u}{\partial x^{2}}+\frac{\partial^{2}u}{\partial y^{2}}+\frac{\partial^{2}u}{\partial z^{2}}=\frac{\partial^{2}u}{\partial r^{2}}+\frac{1}{r}\frac{\partial u}{\partial r}+\frac{1}{r^{2}}\frac{\partial^{2}u}{\partial\theta^{2}}+\frac{\partial^{2}u}{\partial z^{2}}
$$

.

Now that we have covered (what is basically undergraduate calculus
level) mathematics for two-dimensional radially symmetric wave PDE, we will continue on next post.
