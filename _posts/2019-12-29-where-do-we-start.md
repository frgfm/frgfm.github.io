---
layout: post
date: 2019-09-16
title: A good start eases the journey
urlimg: https://i.imgflip.com/1bc3wo.jpg
summary: Initialization for efficient training
permalink: /:title/
mathjax: true
update_date: 2019-12-29
---



For every layer,

Input : $x \sim \mathcal{N}(0, 1)$

Output: $y \sim \mathcal{N}(0, V)$



As numbers are encoded for computation, our layer outputs need to be bound to a finite value
$$
\forall x \sim \mathcal{N}(0, 1), \forall n \in \mathbb{N}, f_1 \circ ... \circ f_n(x) = f^{(n)}(x) \\
where\ f_i(x) = w_i \cdot x + b_i \\
$$
Xavier init
$$
\forall x \sim \mathcal{N}(0, 1), \forall n \in \mathbb{N}, \\
E[f^{(n)}(x)] = 0 \iff  \forall i \in [\![1, n]\!], E[f_i(x)] = 0 \\
\iff \forall i \in [\![1, n]\!], E[w_i \cdot x + b_i] = 0 \\
\iff \forall i \in [\![1, n]\!], b_i = 0
$$

$$
\forall X \sim \mathcal{N}(0, 1), \forall n \in \mathbb{N}, 
var(f^{(n)}(X)) = var(f^{(n+1)}(X)) \\
\iff \forall X \sim \mathcal{N}(0, V), \forall n \in \mathbb{N}, var(W_n \cdot X) = var(X) \\
\iff E[X]^2 \cdot var(W_n) + E[W_n]^2 \cdot var(X) + var(X) var(W_n) = var(X) \\
\iff var(W_ n)= n \cdot var(w_n^{(i)}) = 1 \\
\iff var(w) = \frac{1}{n}
$$





LSUV

MSRA

OrthoNorm