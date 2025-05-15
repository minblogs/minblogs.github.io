---
title: "Least Common Multiple"
date: 2023-09-04
draft: false
tags: ["Mathematics", "Number Theory"]
---

# Definition 2.4

Given $a, b \in \mathbb{Z} (a \neq 0 \text{ or } b \neq 0)$, the **least common multiple** of $a$ and $b$ is the positive integer $m$ satisfying

1. $a \mid m$ and $b \mid m$
2. $a \mid c$ and $b \mid c \implies m \leq c$

In this case, we write $m = \mathrm{lcm}(a, b)$

# Theorem 2.8

$$
\gcd(a, b) \cdot \mathrm{lcm}(a, b) = |a| \cdot |b|
$$

# Corollary 2.8

For any $a, b \in \mathbb{N}$, $\mathrm{lcm}(a, b) = ab \iff \gcd(a, b) = 1$

## Proof

Let $d = \gcd(a, b)$. Then $a = dr$ and $b = ds$ for some $r, s \in \mathbb{Z}$.

Define $m := \frac{ab}{d}$. We will show that $m = \mathrm{lcm}(a, b)$

1. Note that $m = as$ and $m = br \implies a \mid m$ and $b \mid m$
2. Let $a \mid c$ and $b \mid c$. Then $c = au$ and $c = bv$ for some $u, v \in \mathbb{Z}$.   
   Since $d = \gcd(a, b)$, $d = ax + by$ for some $x, y \in \mathbb{Z}$. Then
   $$
   \frac{c}{m} = \frac{cd}{ab} = \frac{c(ax + by)}{ab} = \frac{(bv)(ax) + (au)(by)}{ab} = vx + uy
   $$
   $\implies m \mid c \implies m \leq c$

By (1) and (2), we have $m = \mathrm{lcm}(a, b)$. Then $ab = dm = \gcd(a, b) \cdot \mathrm{lcm}(a, b)$