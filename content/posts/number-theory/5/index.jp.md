---
title: "互いに素"
date: 2023-08-24
draft: false
tags: ["Math", "Number Theory"]
---

# 定義

$a, b \in \mathbb{Z}$（ただし、少なくとも一方は 0 ではない）のとき、  
<div style="text-align: center;">
$a, b$ が<b>互いに素</b>であるとは $\overset{\text{def}}{\iff} \gcd(a, b) = 1$
</div>

## 例

$\gcd(2, 5) = 1 \implies 2$ と $5$ は互いに素である。

# 定理 2.4

$a, b \in \mathbb{Z}$（ただし、少なくとも一方は 0 ではない）のとき、  
$a, b$ が互いに素 $\iff \exists\ x, y \in \mathbb{Z}$ で $ax + by = 1$ を満たす。

> $a$ と $b$ が互いに素 $\overset{\text{def}}{\iff} \gcd(a, b) = 1$

## 証明

$(\implies)$ $d = \gcd(a, b) = 1$ のとき、[定理 2.3](/posts/number-theory/4/#theorem-23) を用いる。

$(\impliedby)$ ある $x, y \in \mathbb{Z}$ が存在して $ax + by = 1$ と仮定する。$d = \gcd(a, b)$ とすると、  
$d \mid (ax + by) \implies d \mid 1 \implies d = 1$

# 系 2.4.1

$\gcd(a, b) = d \implies \gcd\left(\frac{a}{d}, \frac{b}{d}\right) = 1$

> $\gcd(a, b) = d$ のとき、$a = dr$, $b = ds$ となる $r, s \in \mathbb{Z}$ が存在し、$\gcd(r, s) = 1$

## 証明

$\gcd(a, b) = d$ より、ある $x, y \in \mathbb{Z}$ に対して $d = ax + by$  
$\implies 1 = \frac{a}{d}x + \frac{b}{d}y$ となり、$\frac{a}{d}, \frac{b}{d} \in \mathbb{Z}$

[定理 2.4](/posts/number-theory/5/#theorem-24) により、$\gcd\left(\frac{a}{d}, \frac{b}{d}\right) = 1$

## 例

$\gcd(-12, 30) = 6$ かつ $\gcd\left(\frac{-12}{6}, \frac{30}{6}\right) = \gcd(-2, 5) = 1$

# 系 2.4.2

$a \mid c$ かつ $b \mid c$ で、$\gcd(a, b) = 1$ のとき、$ab \mid c$

## 証明

- $a \mid c$, $b \mid c$ より、ある $r, s \in \mathbb{Z}$ が存在して $c = ar = bs$
- $\gcd(a, b) = 1 \implies 1 = ax + by$ となる $x, y \in \mathbb{Z}$ が存在

$\implies c = c \cdot 1 = c(ax + by) = cax + cby = (bs)ax + (ar)by = ab(sx + ry)$  
$\implies ab \mid c$

## 補足

> 「$\gcd(a, b) = 1$」という条件は必要である。

例えば、$6 \mid 24$, $8 \mid 24$ だが、$(6 \cdot 8) \nmid 24$

# 定理 2.5（ユークリッドの補題）

$a \mid bc$ かつ $\gcd(a, b) = 1$ のとき、$a \mid c$

## 証明

[定理 2.4](/posts/number-theory/5/#theorem-24) により、ある $x, y \in \mathbb{Z}$ に対して $1 = ax + by$  
$\implies c = c(ax + by) = acx + bcy$

$a \mid acx$ かつ $a \mid bcy \implies a \mid c$

## 補足

> 「$\gcd(a, b) = 1$」という条件は必要である。

例えば、$12 \mid (9 \cdot 8)$ だが、$12 \nmid 9$, $12 \nmid 8$

# 定理 2.6

$a, b \in \mathbb{Z}$（ただし、少なくとも一方は 0 ではない）のとき、  
<div style="display: flex;">
  $d = \gcd(a, b)$ $\iff$
  <ol style="margin-top: 0">
    <li style="margin-top: 0"> $d \mid a$ および $d \mid b$</li>
    <li> 任意の $c$ に対して、$c \mid a$ および $c \mid b$ ならば $c \mid d$</li>
  </ol>
</div>

## 証明

$(\implies)$ $d = \gcd(a, b)$ のとき、(1) は明らか。  
また、ある $x, y \in \mathbb{Z}$ に対して $d = ax + by$ が成り立つ。  
$c \mid a$, $c \mid b$ のとき、$c \mid (ax + by)$ より $c \mid d$。したがって (2) も成り立つ。

$(\impliedby)$ (1), (2) が成り立つと仮定する。  
任意の $c \mid d$ に対して $c \leq d$ となるので、$d = \gcd(a, b)$
