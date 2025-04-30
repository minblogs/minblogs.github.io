---
title: 'Greatest Common Divisor'
date: 2023-08-23
draft: false
tags: ['Math', 'Number Theory']
---

# Definition

Let $a, b \in \mathbb{Z}$. The **greatest common divisor** of $a$ and $b$ is the positive integer $d$ satisfying

1. $d \mid a$ and $d \mid b$
2. if $c \mid a$ and $c \mid b$, then $c \leq d$

In this case we write $d = \gcd(a, b)$

## Summary

- Find all positive divisors of $a$ and $b$.
- Find all common divisors.
- Choose the greatest one.

## Example

Find $\gcd(-12, 30)$.

1. All positive divisors
   - $-12$: $1, 2, 3, 4, 6, 12$
   - $30$: $1, 2, 3, 5, 6, 10, 15, 30$
2. All common positive divisors of $12$ and $30$: $1, 2, 3, 6$
3. $\therefore \gcd(-12, 30) = 6$

Some values of $-12x + 30y$ for $x, y \in \mathbb{Z}$

|  $x$ \\ $y$ |     -2   |     -1   |      0   |      1   |      2   | $\cdots$ |
|:-----------:|:--------:|:--------:|:--------:|:--------:|:--------:|:--------:|
|      -2     |    -36   |     -6   |     24   |     54   |     84   | $\cdots$ |
|      -1     |    -48   |    -18   |     12   |     42   |     72   | $\cdots$ |
|       0     |    -60   |    -30   |      0   |     30   |     60   | $\cdots$ |
|       1     |    -72   |    -42   |    -12   |     18   |     48   | $\cdots$ |
|       2     |    -84   |    -54   |    -24   |      6   |     36   | $\cdots$ |
|   $\vdots$  | $\vdots$ | $\vdots$ | $\vdots$ | $\vdots$ | $\vdots$ | $\ddots$ |

## Observation

- $\exists\ x, y \in \mathbb{Z}$ s.t. $-12x + 30y = 6$
- Each number is multiple of $6$.   
  $\because -12x + 30y = 6(-2x + 5y)$

> Recall: $\boxed{\gcd(-12, 30) = 6}$

# Theorem

Given $a, b \in \mathbb{Z} (a \neq 0 \text{ or } b \neq 0)$, let $d = \gcd(a, b)$.   
$\implies \exists\ x, y \in \mathbb{Z}$ s.t. $ax + by = d$.

## Proof

Let $S := \\{au + bv > 0\ |\ u, v \in \mathbb{Z} \\}$.

Assume that $a \neq 0$. (If $b \neq 0$, then it is similar.)

Claim: $S$ is non-empty.

- If $a > 0$, then $a = a \cdot 1 + b \cdot 0 > 0 \implies a \in S$.
- If $a < 0$, then $-a = a \cdot (-1) + b \cdot 0 > 0 \implies -a \in S$.

$\implies$ By [well-ordering principle](/posts/number-theory/1/#well-ordering-principle), $S$ has the smallest element $d \in S \quad \cdots (\ast)$   

Write $d = ax + by$ for some $x, y \in \mathbb{Z}$

Now we show that Claim: $d = \gcd(a, b)$ (Recall: $d = ax + by$ for $x, y \in \mathbb{Z}$)

1. $d \mid a$ and $d \mid b$
   - By the [division algorithm](/posts/number-theory/2/), $\exists$ $q, r \in \mathbb{Z}$ s.t. $a = qd + r$ and $0 \leq r < d$.
   - Suppose that $r > 0$. Then   
    $r = a - qd  = a - q(ax + by) = a(1 - qx) + b(-qy) > 0 \implies r \in S$
   - But, $r < d$ , which contradicts to $(\ast)$.   
    $\implies r = 0 \implies a = qd \implies d \mid a$ (Similarly we can show $d \mid b$)
2. If $c \mid a$ and $c \mid b$, then $c \leq d$   
  If $c \mid a$ and $c \mid b$, then $c \mid (ax + by) \implies c \mid d \implies c \leq d$

$\therefore d = \gcd(a, b)$

# Corollary

Given $a, b \in \mathbb{Z} (a \neq 0 \text{ or } b \neq 0)$, let $d = \gcd(a, b)$. Then

$$
\\{ax + by\ |\ x, y \in \mathbb{Z}\\} = \\{kd\ |\ k \in \mathbb{Z}\\}
$$

## Proof

By Theorem, $d = ax_0 + by_0$ for some $x_0, y_0 \in \mathbb{Z}$.

1. $(B \subseteq A)$ Let $kd \in B$. Then $kd = k(ax_0 + by_0) = a(kx_0) + b(ky_0) \in A$
2. $(A \subseteq B)$ Let $ax + by \in A$.   
  Since $d = \gcd(a, b)$, $a = dr$ and $b = ds$ for some $r, s \in \mathbb{Z}$.   
  Then $ax + by = drx + dsy = d(rx + sy) \in B$