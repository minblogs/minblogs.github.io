---
title: 'Mathematical Induction and Binomial Theorem'
date: 2023-08-15
draft: false
tags: ['Math', 'Number Theory']
---

# Well-Ordering Principle

If a subset $S$ of natural numbers is non-empty, then $S$ has a smallest element.

# Mathematical Induction

Assume that a subset $S$ of natural numbers satisfies the following conditions:

1. $1$ is an element of $S$.
2. For any natural number $k$, if $k \in S$, then $k+1 \in S$.

Then, $S = \mathbb{N}$.

## Proof

Let $T := \mathbb{N} \setminus S$ be defined, and assume that $T$ is non-empty.

Since $T \subset \mathbb{N}$, by the [well-ordering principle](#well-ordering-principle), $T$ has a smallest element. Let this element be $m$.

-   First, consider the case where $m = 1$. By the given conditions, $1 \in S$, so $1 \notin T$. This is a contradiction.
-   Next, consider the case where $m > 1$. In this case, $m-1$ is a natural number, so $m-1 \in \mathbb{N}$. Additionally, since $m$ is the smallest element of $T$, $m-1$ must be in $S$. However, by the condition, if $k \in S$, then $k+1 \in S$. Therefore, if $m-1 \in S$, then $m = (m-1)+1 \in S$, which contradicts the assumption that $m \in T$.

Thus, $T$ must be empty, and it follows that $S = \mathbb{N}$.

# Binomial Coefficient

For $n \in \mathbb{N}$ and $0 \leq k \leq n$, the binomial coefficient is defined as:

$$
\binom{n}{k} := \frac{n!}{k!(n-k)!}
$$

Here, $n!$ represents the factorial of the natural number $n$, which is calculated as follows:

$$
\begin{align*}
n! &= \prod_{k=1}^{n} k \\\\
   &= n \times (n-1) \times (n-2) \times \cdots \times 1
\end{align*}
$$

# Binomial Theorem

The binomial Theorem is a formula that expands a binomial expression raised to a power as a sum of terms involving binomial coefficients. It provides a convenient way to perform these calculations.

According to the binomial Theorem, the expansion of the binomial expression $(a+b)^n$ can be written as:

$$
\begin{align*}
(a+b)^n &= \sum_{k=0}^{n} \binom{n}{k} a^{n-k} b^k \\\\
&= a^n + n a^{n-1} b + \frac{n(n-1)}{2} a^{n-2} b^2 + \cdots + n b^{n-1} a + b^n
\end{align*}
$$
