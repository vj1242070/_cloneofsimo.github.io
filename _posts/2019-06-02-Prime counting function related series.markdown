---
layout: post
title:  "Prime counting function related series"
date:   2019-06-02 01:21:23 +0900
categories: math
---
This post we will study around the integral expression of some series.
Using prime number theorem and ratio test, one can see that

$$
\sum_{n=1}^{\infty}\frac{\pi(n)}{n^{3}}
$$

is convergent.

Finding it's value, is a difficult problem. In this post we prove
the following identity.

$$
\sum_{n=1}^{\infty}\frac{\pi(n)}{n^{3}}=\frac{1}{2}\int_{0}^{1}\log^{2}(x)\frac{P(x)}{x(1-x)}dx
$$

Where $$P(x)$$ is Z-transform of prime indicator function (well, not
really, we are only summing the positive part. i.e, $$P(x)=\sum_{n=1}^{\infty}\chi(n)x^{n},$$where
$$\chi(n)$$ is prime indicator function)

Notice that this is really not special because it is prime. Rather,
any arithematic function would satisfy. Indeed we have

$$
\zeta(3)=\int_{0}^{1}\frac{\log^{2}(x)}{1-x}dx
$$

One way would be just substituting with $$x=e^{-t}$$ and using geometric
sum. In general, the following equation holds. Let $$F(z)=\sum_{n\geq1}a_{n}z^{n}$$,
$$A(n)=\sum_{m\leq n}a_{m}$$

$$
\sum_{n=1}^{\infty}\frac{A(n)}{n^{s}}=\frac{(-1)^{s-1}}{(s-1)!}\int_{0}^{1}\log^{s-1}(x)\frac{F(x)}{x(1-x)}dx
$$

The above equation is equivalent to the following:

$$
\sum_{n=1}^{\infty}a_{n}(\zeta(s)-\sum_{m=1}^{n-1}\frac{1}{m^{s}})=\frac{(-1)^{s-1}}{(s-1)!}\int_{0}^{1}\sum_{n=1}^{\infty}a_{n}\frac{\log^{s-1}(x)x^{n-1}}{1-x}dx
$$

Now thinking about independence of $$a_{i}$$s, one can guess that proving
the following is enough.

$$
\zeta(s)-\sum_{m=1}^{n-1}\frac{1}{m^{s}}=\frac{(-1)^{s-1}}{(s-1)!}\int_{0}^{1}\frac{\log^{s-1}(x)}{1-x}x^{n-1}dx
$$

On the right hand side, substitute $$x=e^{-t}.$$

$$
\int_{\infty}^{0}(-t)^{s-1}e^{-nt}(1+e^{-t}+e^{-2t}+\cdots)dt
$$

Let's have a look at the integral

$$
\int_{0}^{\infty}t^{s-1}e^{-mt}dt
$$

This is just gamma function, up to constant multiplication. Take $$mt=r$$

$$
\int_{0}^{\infty}r^{s-1}e^{-r}dr=m^{s}\int_{0}^{\infty}t^{s-1}e^{-mt}dt
$$

We then have by definition of gamma function $$\Gamma(s)=m^{s}\int_{0}^{\infty}t^{s-1}e^{-mt}dt$$.
Therefore overall we have
$$
\frac{(-1)^{s-1}}{(s-1)!}\int_{0}^{1}\frac{\log^{s-1}(x)}{1-x}x^{n-1}dx=\frac{(-1)^{s-1}}{(s-1)!}\sum_{m=n}^{\infty}\int_{0}^{\infty}(-t)^{s-1}e^{-mt}dt=\frac{\Gamma(s)}{(s-1)!}\sum_{m=n}^{\infty}\frac{1}{m^{s}}
$$

It is well known property that $$\Gamma(s)=(s-1)!$$ for integer $$s$$.
Therefore we have what we wanted.

Fun problem as an exercise

$$
\int_{0}^{\infty}\frac{\log^{n}x}{(1-x)^{m}}dx
$$
