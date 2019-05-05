---
layout: post
title:  "Trigonometric, Harmonic Series "
date:   2019-05-05 01:21:23 +0900
categories: math
---

Investigating and studying in MSE, people often come across various
problems related to trigonometric series. Some problems tend to be
wildly interesting, especially the question that asks rather the sum
converges or not. e.g.
$$
\sum_{n=1}^{\infty}\frac{\sin n}{n}<\infty?
$$

This is by far the simplest of it's kind. In fact, the above value
is so well known that in general,

$$
\sum_{n=1}^{\infty}\frac{\sin nx}{n}=\frac{\pi-x}{2}
$$

for $$x\in(0,2\pi)$$. This can be proven by simple Fourier transformation.
Alternatively (and probably the simplest way) one can prove the convergence
by Dirichlet's test.

Also, using the Dirichlet's test we can prove that

$$
\sum_{n=1}^{\infty}\frac{\sin n}{n^{\epsilon}}<\infty
$$

for all positive real $$\epsilon$$.

Next is the question of convergence of infinite sum

$$
\sum_{n=1}^{\infty}\frac{\sin n^{2}}{n}<\infty?
$$

In fact in this post we will investigate on much more general form.
However for the sake of motive, let's begin with above case.

Abel's Summation Formula

Suppose that we thoroughly know about the series $$a_{n}$$, so that the
partial sum $$\sum_{i=1}^{m}a_{i}$$ is well known. Now suppose that
we wish to investigate on the following form of sum:

$$
\sum_{n=1}^{m}a_{n}f(n)
$$

Indeed, there is a way to express the above sum in the sense of **integration
by parts**. Denote $$A(t)=\sum_{1\leq i\leq t}a_{t}$$. We have

### Abel's summation formula

$$
\sum_{n=1}^{m}a_{n}f(n)=A(m)f(m)-\int_{1}^{m}A(t)f'(t)dt
$$

The proof is actually extremely simple: one can simply notice that

$$
a_{m}f(m)+\int_{m-1}^{m}A(t)f'(t)dt=A(m)f(m)-A(m-1)f(m-1)
$$

Specifically, let $$f(n)=1/n$$ and $$a_{n}=\sin n^{2}$$,

$$
\sum_{n=1}^{\infty}\frac{\sin n^{2}}{n}=\lim_{m\rightarrow\infty}\sum_{n=1}^{m}\frac{\sin n^{2}}{n}=\lim_{m\rightarrow\infty}\frac{A(m)}{m}+\int_{1}^{m}\frac{A(t)}{t^{2}}dt
$$

So, the problem of rather the above sum is convergent or not is actually
equivalent to asking rather the following limit exists

$$
\frac{A(m)}{m},\int_{1}^{m}\frac{A(t)}{t^{2}}dt
$$

where $$A(t)=\sum_{1\leq i\leq t}a_{t}$$.

Intuitively above sum is bounded somewhere with $$O(\sqrt{t})$$, and
indeed, that is the case. By using the Weyl's bound,(which we will
prove later) the result is straightforward.

Now here is the cool part. After considering these series, it is natural
to think of the following series.

$$
\sum_{n=1}^{\infty}\frac{\sin n^{2}}{n^{\alpha}}
$$

However, this sum is not convergent for all $$\alpha<0.29...$$

Suppose that indeed above sum is convergent. This implies for every
$$m,H$$, one has

$$
\sum_{n=m+1}^{m+H}\frac{\sin n^{2}}{n^{\alpha}}
$$

is bounded. Moreover, for some positive $$\delta$$ if $$H=m^{1/(2-\alpha)-\delta}$$,

$$
\sum_{n=m+1}^{m+H}\frac{\sin n^{2}}{(m+1)^{\alpha}}
$$

is also bounded as $$o(1)$$, because *

$$
|\sum_{n=m+1}^{m+H}\frac{\sin n^{2}}{n^{\alpha}}-\sum_{n=m+1}^{m+H}\frac{\sin n^{2}}{(m+1)^{\alpha}}|=|\sum_{n=1}^{H}\frac{\sin(m+n)^{2}}{(m+1)^{\alpha}}((1+\frac{n-1}{m+1})^{-\alpha}-1)|\sim|\sum_{n=1}^{H}\frac{\sin(m+n)^{2}}{(m+n)^{\alpha}}(-\alpha\frac{n-1}{(m+1)})|
$$
$$
=O(H^{1-\alpha})O(H)/(m+1)=o(1)
$$

On the other hand,
$$
|\sum_{n=m+1}^{m+H}\sin n^{2}|>H^{1/2}
$$

holds infinitely often for all $$\epsilon>0$$. We will prove this later
on. Thus for large enough $$m$$,

$$
\frac{|\sum_{n=m+1}^{m+H}\sin n^{2}|}{(m+1)^{\alpha}}>\frac{H^{1/2-\epsilon}}{(m+1)^{\alpha}}=m^{1/(4-2\alpha)-\alpha-\epsilon_{2}}>1
$$

which is not $$o(1)$$. Thus we are done.

### Discrete Gauss summations

Now we are left to prove that discrete gauss sums, have fluctuation
of about $$\sqrt{N}$$ infinitely often. This is intuitively true, because
sum of $$N$$ random variables tends to have positive probability to
be

greater than $$O(\sqrt{N})$$, even sometimes greater than$$O(\sqrt{N\log\log N})$$.
Sketch of the proof goes something like this, we first prove that
for irrational $$\beta$$,

$$
|\sum_{n=m+1}^{m+H}e^{2\pi i\beta n^{2}}|>\sqrt{H}
$$

infinitely often, for fixed $$N$$ and variable $$m,$$ ranging with constraint
that $$H=m^{1/(2-\alpha)-\delta}.$$ Let's just assume that $$H^{\frac{1}{1/(2-\alpha)-\delta}}=D,D<m<2D+1$$
. Define $$X_{1},X_{2},\cdots,X_{H}$$ as $$X_{n}(m):=e^{2\pi i\beta(n+m)^{2}}$$.

One can see that

$$
\mathbb{E}(e^{2\pi i\beta n})=\frac{\sum_{m=D+1}^{2D}e^{2\pi i\beta n}}{D}=O(1/D)\text{ (Dirichlet kernel)}
$$

Now we wish to calculate the variance of the sum $$|X_{1}+X_{2}+\cdots+X_{H}|.$$
For a moment let's suppose that two variable $$X_{i}$$ and $$X_{j}$$
is independent (or nearly independent). This gives

$$
V(|\sum_{n=1}^{H}X_{n}|^{2})=\sum_{n=1}^{H}V(|X_{n}|^{2})+\sum_{1\leq u<v\leq H}V(X_{u}\overline{X_{v}}+\overline{X_{u}}X_{v})=\sum_{1\leq u<v\leq H}\mathbb{E}(X_{u}^{2}\overline{X_{v}^{2}}+\overline{X_{u}^{2}}X_{v}^{2}+2)-\mathbb{E}(X_{u}\overline{X_{v}}+\overline{X_{u}}X_{v})^{2}
$$

Indeed, given that $$\mathbb{E}(X_{a}\overline{X_{b}})=O(1/D),$$we
have

$$
V(|\sum_{n=1}^{H}X_{n}|^{2})=H(H-1)(1+O(1/D))\sim H^{2}
$$

Therefore we are left to prove that $$X_{a}$$ and $$X_{b}$$ has small
covariance. More precisely,

$$
\text{cov}(X_{u}\overline{X_{v}}+\overline{X_{u}}X_{v},X_{w}\overline{X_{r}}+\overline{X_{w}}X_{r})=\mathbb{E}((X_{u}\overline{X_{v}}+\overline{X_{u}}X_{v})(X_{w}\overline{X_{r}}+\overline{X_{w}}X_{r}))-\mathbb{E}(X_{w}\overline{X_{r}}+\overline{X_{w}}X_{r})\mathbb{E}(X_{u}\overline{X_{v}}+\overline{X_{u}}X_{v})=O(1/D)
$$

for arbitrary (not necessarily distinct) $$u,v,w,r$$.

This is almost trivial from the fact that again, $$\mathbb{E}(X_{a}\overline{X_{b}})=O(1/D)$$
and linearity of expectation. Therefore we have

$$
V(|\sum_{n=1}^{H}X_{n}|^{2})=\sum_{n=1}^{H}V(|X_{n}|^{2})+\sum_{1\leq u<v\leq H}V(X_{u}\overline{X_{v}}+\overline{X_{u}}X_{v})+\sum_{r,u\neq v}\text{cov}(X_{r}\overline{X_{r}},X_{u}\overline{X_{v}}+\overline{X_{u}}X_{v})
$$

$$
+\sum_{u\neq v,w\neq r}\text{cov}(X_{u}\overline{X_{v}}+\overline{X_{u}}X_{v},X_{w}\overline{X_{r}}+\overline{X_{w}}X_{r})+\sum_{u\neq v}\text{cov}(X_{u}\overline{X_{u}},X_{v}\overline{X_{v}})
$$

From the above argument, all the covariance part is really just of
$$O(1/D)$$, and the number of summations is of function $$H$$, therefore
is ignorable.

(The last summation count is $$O(H^{4}).$$This implies that the total
value is $$V(|\sum X_{n}|)=H^{2}+O(H^{4}/D)=H^{2}(1+o(1)))$$

Finally, we have that

$$
\mathbb{E}(|\sum_{n=1}^{H}X_{n}|^{4})>V(|\sum_{n=1}^{H}X_{n}|^{2})=H^{2}(1+o(1))
$$

Meaning that

$$
|\sum_{n=m+1}^{m+H}e^{2\pi i\beta n^{2}}|>\sqrt{H}
$$

infinitely often, thus we have the final result.

As I finish off, notice that at * one can expect cancellation to
happen with $$O(H^{1/2})$$ leftovers. If that is the case, one can reduce
$$\alpha$$ to $$0.5-\epsilon$$. I think I'll leave this as a conjecture.
