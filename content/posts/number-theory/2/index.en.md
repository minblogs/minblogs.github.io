---
title: 'Division Algorithm'
date: 2023-08-19
draft: false
tags: ['Math', 'Number Theory', 'Algorithm']
---

# Theorem

Given $a, b \in \mathbb{Z}$ with $b > 0$, there exist unique $q, r \in \mathbb{Z}$ such that

$$
a = qb + r \quad (0 \leq r < b)
$$

In this case, $q$ is called a **quotient** and $r$ is called a **remainder.**

## Example

1. $a = 23, b = 5 \implies 23 = 4 \cdot 5 + 3 \implies q = 4, r = 3$
2. $a = -23, b = 5 \implies -23 = (-5) \cdot 5 + 2 \implies q = -5, r = 2$

## Proof

Define $S := \\{a - xb \geq 0 : x \in \mathbb{Z}\\} \subseteq \mathbb{N} \cup \\{0\\}$. $\implies$ $S$ is non-empty.

> $\because a - (-|a|)b = a + |a|b \geq a + |a| \geq 0 \implies a - (-|a|)b \in S \implies S \neq \varnothing$

By Well-ordering principle, $S$ has the smallest integer $r \in S$.

$$
r \in S \implies \exists q \in \mathbb{Z} \text{ s.t. } a = qb + r \quad (r \geq 0)
$$

**Claim 1:** $0 \leq r < b$. Suppose that $r \geq b \implies a - (q+1)b = r - b \geq 0$  
$\implies a - (q+1)b \in S$, but $a -(q + 1)b < a - qb = r$, which contradicts to fact that $r$ is the smallest in $S \implies r < b$.

**Claim 2:** $q$ and $r$ are unique. Assume that $a = qb + r = q^\prime b + r^\prime $ with $q, q^\prime \in \mathbb{Z}$  
and $0 \leq r, r^\prime < b \implies r^\prime - r = (q - q^\prime)b \implies |r^\prime - r| = |q - q^\prime |b$  
and $|r^\prime - r| < b$ $\implies |q - q^\prime| < 1 \implies q = q^\prime$ and $r = r^\prime$.

# Generalized Division Algorithm

Given $a, b \in \mathbb{Z}$ with $b \neq 0$, there exist unique $q, r \in \mathbb{Z}$ such that

$$
a = qb + r \quad (0 \leq r < |b|)
$$

## Proof

If $b < 0$, then $|b| > 0$.

By Division Algorithm, $\exists q^\prime, r \in \mathbb{Z}$ s.t. $a = q^\prime |b| + r$ with $0 \leq r < |b|$.

Since $|b| = -b$, we have $a = q^\prime (-b) + r = (-q^\prime) b + r$.

If we write $q = -q^\prime$, then $a = qb + r$ with $0 \leq r < |b|$.

## Example

Let $a = 61$ and $b = -7$. Then $61 = (-8)(-7) + 5$. Hence, $q = -8$ and $r = 5$.

# Application

Let $b \in \mathbb{N}$. Then each integer $a$ has the form of

$$
a = qb + r \quad (q \in \mathbb{Z}, 0 \leq r < b)
$$

## Definition

If $b = 2$, then $a = 2q + r$ with $q \in \mathbb{Z}$ and $0 \leq r < 2$.

- $a = 2q \implies a$ is called even.
- $a = 2q + 1 \implies a$ is called odd.

## Example

Show that $N = \frac{1}{3}a(a^2 + 2)$ is an integer. for all $a \in \mathbb{N}$.

{{< collapse summary="Solution" >}}

Note that $a = 3q + r$ with $q \in \mathbb{Z}$ and $0 \leq r < 3$   
$\implies a = 3q$ or $a = 3q + 1$ or $a = 3q + 2$

1. $a = 3q \implies N = \frac{1}{3}(3q)((3q)^2 + 2) = q(9q^2 + 2)$
2. $a = 3q + 1 \implies N = \frac{1}{3}(3q + 1)((3q + 1)^2 + 2) = (3q + 1)(3q^2 + 3q + 1)$
3. $a = 3q + 2 \implies N = \frac{1}{3}(3q + 2)((3q + 2)^2 + 2) = (3q + 2)(3q^2 + 4q + 1)$ 

{{< /collapse >}}