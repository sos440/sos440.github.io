---
layout: post
title: Elementary proof of the partial fraction decomposition of $\csc^2 z$
date:   2024-11-15 00:14:00 +0900
categories: math
---

In this posting, we provide an elementary proof of:

> **Theorem.** For any complex $z$ with $z \notin \pi \mathbb{Z}$, we have
> 
> $$ \cot z = \lim_{N\to\infty} \sum_{k=-N}^{N} \frac{1}{z - k\pi} $$
>
> and
> 
> $$ \csc^2 z = \sum_{k=-\infty}^{\infty} \frac{1}{(z - k\pi)^2}. $$

*Proof.* Since both $\cot z$ and $\csc^2 z$ are $\pi$-periodic, we may assume $\lvert \operatorname{Re}(z) \rvert \leq \frac{\pi}{2}$.
Then by using the identity $a^n - b^n = \prod_{k=0}^{n-1} (a - e^{\frac{2\pi i k}{n}} b)$, we get

$$
\begin{align*}
\sin z
&= \frac{1}{2i} \left( e^{iz} - e^{-iz} \right) \\
&= \frac{1}{2i} \prod_{k=0}^{n-1} \left( e^{\frac{iz}{n}} - e^{\frac{2\pi i k}{n}} e^{-\frac{iz}{n}} \right) \\
&= \frac{1}{2i} \prod_{k=0}^{n-1} 2i e^{\frac{\pi i k}{n}} \sin\left( \frac{z - \pi k}{n} \right) \\
&= (-2)^{n-1} \prod_{k=0}^{n-1} \sin\left( \frac{z - \pi k}{n} \right).
\end{align*}
$$

Now let $N_0 = \lfloor \frac{n-1}{2} \rfloor$ and $N_1 = n - 1 - N_0 = \lceil \frac{n-1}{2} \rceil$. Then by log-differentiating both sides,

$$
\begin{align*}
\cot z
&= \sum_{k=0}^{n-1} \frac{1}{n} \cot\left( \frac{z - \pi k}{n} \right) \\
&= \sum_{k=-N_0}^{N_1} \frac{1}{n} \cot\left( \frac{z - \pi k}{n} \right) \\
&= \sum_{k=-N_0}^{N_1} \frac{\cos \left( \frac{z - \pi k}{n} \right)}{\operatorname{sinc}\left( \frac{z - \pi k}{n} \right)} \frac{1}{z - \pi k}.
\end{align*}
$$