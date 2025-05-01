---
title: 'Mathematical Induction and Binomial Theorem'
date: 2023-08-15
draft: false
tags: ['Math', 'Number Theory']
---

# Well-Ordering Principle

$S$ : non-empty subset of $\mathbb{Z^+} = \\{0, 1, 2, ..., \\}$   
$\implies$ $S$ has the smallest element in $S$   
$\iff \exists\ a \in S$ s.t. $a \leq b$, $\forall\ b \in S$

# Theorem 1.2

Assume that a $S \subseteq \mathbb{N}$ satisfies

1. $1 \in S$
2. If $k \in S$, then $k+1 \in S$.

Then $S = \mathbb{N}$.

## Proof

Let $T := \mathbb{N} \setminus S$. Suppose that $T$ is non-empty.

Since $T \subset \mathbb{N}$, by the [well-ordering principle](#well-ordering-principle), $T$ must have the smallest element $m \in T$.

- $1 \notin T \implies m \geq 2 \implies m-1 \in \mathbb{N}$
- Since $m \in T$, $m \notin S \implies m-1 \notin S \implies m-1 \in T$, which is a   
  contradiction to the assumption : $m \in T$ is the smallest element in $T$

$\therefore$ $T$ is empty $\implies S = \mathbb{N}$

## Example

Show that $1 + 2 + 3 + \cdots + n = \frac{n(n+1)}{2}$, $\forall\ n \in \mathbb{N}$

{{<collapse summary="Solution">}}

- $P(n) : 1 + 2 + 3 + \cdots + n = \frac{n(n+1)}{2}$
- Define $S := \\{n \in \mathbb{N}\ |\ P(n) \text{ is true}\\}$
   1. $1 \in S \iff P(1)$ is true ($\because P(1) : 1 = \frac{1(1+1)}{2}$)
   2. if $k \in S$, then $k+1 \in S \iff P(k)$ is true, then $P(k+1)$ is true   
      $\because$ if $1 + 2 + \cdots + k = \frac{k(k+1)}{2}$, then   
      $$
      \begin{align*}
      1 + 2 + \cdots + k + (k+1) &= \frac{k(k+1)}{2} + (k+1) \\\\
                                 &= \frac{k(k+1) + 2(k+1)}{2} \\\\
                                 &= \frac{(k+1)(k+2)}{2}
      \end{align*}
      $$

{{</collapse>}}

# Binomial Coefficient

Let $n \in \mathbb{N}$ and $0 \leq k \leq n$. Then we define

$$
\binom{n}{k} := \frac{n!}{k!(n-k)!}
$$

where $n!$ is the factorial of $n$ defined as

$$
\begin{align*}
n! &= \prod_{k=1}^{n} k \\\\
   &= n \times (n-1) \times (n-2) \times \cdots \times 1
\end{align*}
$$

# Binomial Theorem

The expansion of the binomial expression $(a+b)^n$ can be written as:

$$
\begin{align*}
(a+b)^n &= \sum_{k=0}^{n} \binom{n}{k} a^{n-k} b^k \\\\
&= a^n + n a^{n-1} b + \frac{n(n-1)}{2} a^{n-2} b^2 + \cdots + n b^{n-1} a + b^n
\end{align*}
$$
