---
layout: post
title:  "Power set and the set of indicator functions have the same cardinality"
date:   2019-04-16 11:00:00 +0900
use_math: false
categories: jekyll update
---
This post is the proof of the following statement.

Let $$P(S)$$ be the set of all subsets of $$S$$, and let $$T$$ be the
set of all functuins from $$S$$ to $$\{0,1\}$$. Show that $$P(S)$$ and
$$T$$ have the same cardinality.

To see that there exists a bijective function $$f$$ that maps $$T$$
to $$S$$, we have to define $$T$$ in much more set-theoriotic way. It
follows as;

$$T:=\{g|g:S\rightarrow\{0,1\}\}$$

In which case, by the definition of function, one has

$$g:S\rightarrow\{0,1\}:=\{(a_{i},g(a_{i}))|a_{i}\in S,g(a_{i})\in\{0,1\}\}$$

where $$i$$ is an index. This expression gives direct intuition on
the function $$f$$that we are planning to design. Let $$f(X)=Y$$ for $$X\in T$$ and $$Y\in P(S)$$ if $$X(a)=1$$ imply $$a\in Y$$
and $$X(a)=0$$ imply $$a\notin Y$$. We will prove that this function is bijective indeed.

First it is surjective hence one can directly get $$X$$ for every given
$$Y$$.

Now, assume that it is not injective. That is, $$f(X_{1})=f(X_{2})$$
for $$X_{1}\neq X_{2}$$. Because $$X_{1}\neq X_{2}$$, there must exist
some element $$\alpha\in S$$ that $$X_{1}(\alpha)\neq X_{2}(\alpha)$$.
But clearly this contradicts because $$\alpha$$ is either in the set
$$f(X_{1})$$ or not.

2019330001
