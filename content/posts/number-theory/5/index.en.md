---
title: "Relatively Prime"
date: 2023-08-24
draft: false
tags: ["Mathematics", "Number Theory"]
---

# Definition 2.3

Given $a, b \in \mathbb{Z}$ (at least one of them is not zero),
<div style="text-align: center; margin: 1rem 0;">
$a, b$ are called <b>relatively prime</b> $\overset{\text{def}}{\iff} \gcd(a, b) = 1$.
</div>

## Example

$\gcd(2, 5) = 1 \implies 2$ and $5$ are relatively prime

# Theorem 2.4

Given $a, b \in \mathbb{Z}$ (at least one of them is not zero),   
$a, b$ are relatively prime $\iff \exists\ x, y \in \mathbb{Z}$ s.t. $ax + by = 1$.

> $a$ and $b$ are relatively prime $\overset{\text{def}}{\iff} \gcd(a, b) = 1$

## Proof

$(\implies)$ $d = \gcd(a, b) = 1$. Use [Theorem 2.3.](/posts/number-theory/4/#theorem-23)

$(\impliedby)$ Assume that $ax + by = 1$ for some $x, y \in \mathbb{Z}$. Let $d = \gcd(a, b)$.   
Then $d \mid (ax + by) \implies d \mid 1 \implies d = 1$

# Corollary 2.4.1

$\gcd(a, b) = d \implies \gcd(\frac{a}{d}, \frac{b}{d}) = 1$

> If $\gcd(a, b) = d$, then $a = dr$ and $b = ds$ with $\gcd(r, s) = 1$.

## Proof

Since $\gcd(a, b) = d$, $d = ax + by$ for some $x, y \in \mathbb{Z}$.   
$\implies 1 = \frac{a}{d}x + \frac{b}{d}y$ with $\frac{a}{d}, \frac{b}{d} \in \mathbb{Z}$

By [Theorem 2.4](/posts/number-theory/5/#theorem-24), $\gcd(\frac{a}{d}, \frac{b}{d}) = 1$.

## Example

Note that $\gcd(-12, 30) = 6$ and $\gcd(\frac{-12}{6}, \frac{30}{6}) = \gcd(-2, 5) = 1$.

# Corollary 2.4.2

$a \mid c$ and $b \mid c$ with $\gcd(a, b) = 1 \implies ab \mid c$

## Proof

- $a \mid c$ and $b \mid c$ $\implies c = ar = bs$ for some $r, s \in \mathbb{Z}$
- $\gcd(a, b) = 1 \implies 1 = ax + by$ for some $x, y \in \mathbb{Z}$

$\implies c = c \cdot 1 = c(ax + by) = cax + cby = (bs)ax + (ar)by = (ab)(sx + ry)$   
$\implies ab \mid c$

## Remark

> The condition "$\gcd(a, b) = 1$" is necessary.

Note that $6 \mid 24$ and $8 \mid 24$. BUT, $(6 \cdot 8) \nmid 24$.

# Theorem 2.5 [Euclid's Lemma]

$a \mid bc$ with $\gcd(a, b) = 1 \implies a \mid c$

## Proof

By [Theorem 2.4](/posts/number-theory/5/#theorem-24), we write $1 = ax + by$ for some $x, y \in \mathbb{Z}$.   
$\implies c = c(ax + by) = acx + bcy$

$a \mid acx$ and $a \mid bcy$ $\implies a \mid c$

## Remark

> The condition "$\gcd(a, b) = 1$" is necessary.

Note that $12 \mid (9 \cdot 8)$. BUT, $12 \nmid 9$ and $12 \nmid 8$

# Theorem 2.6

Given $a, b \in \mathbb{Z}$ (at least one of them is not zero),
<div style="display: flex;">
  $d = \gcd(a, b)$ $\iff$ 
  <ol style="margin-top: 0">
    <li style="margin-top: 0"> $d \mid a$ and $d \mid b$ </li>
    <li> if $c \mid a$ and $c \mid b$, then $c \mid d$ </li>
  </ol>
</div>

## Proof

$(\implies)$ Let $d = \gcd(a, b)$. Then (1) is clear.   
Since $d = \gcd(a, b)$, $\exists\ x, y \in \mathbb{Z}$ s.t. $d = ax + by$.   
If $c \mid a$ and $c \mid b$, then $c \mid (ax + by)$, so that $c \mid d$. Thus (2) is true.

$(\impliedby)$ Assume that (1) and (2) are true. If $c \mid d$, then $c \leq d$.   
Thus $d = \gcd(a, b)$.
