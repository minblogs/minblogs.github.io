---
title: '割り算アルゴリズム'
date: 2023-08-19
draft: false
tags: ['数学', '数論', 'アルゴリズム']
---

# 定理

$a, b \in \mathbb{Z}$ かつ $b > 0$ のとき、次のような一意な $q, r \in \mathbb{Z}$ が存在する：

$$
a = qb + r \quad (0 \leq r < b)
$$

このとき、$q$ を **商**、$r$ を **余り** と呼ぶ。

## 例

1. $a = 23, b = 5 \implies 23 = 4 \cdot 5 + 3 \implies q = 4, r = 3$
2. $a = -23, b = 5 \implies -23 = (-5) \cdot 5 + 2 \implies q = -5, r = 2$

## 証明

$S := \\{a - xb \geq 0\ |\ x \in \mathbb{Z}\\} \subseteq \mathbb{N} \cup \{0\}$ と定義する。よって、$S$ は空でない。

> $\because a - (-|a|)b = a + |a|b \geq a + |a| \geq 0 \implies a - (-|a|)b \in S \implies S \neq \varnothing$

整列原理により、$S$ は最小の整数 $r \in S$ を持つ。

$$
r \in S \implies \exists\ q \in \mathbb{Z} \text{ s.t. } a = qb + r \quad (r \geq 0)
$$

**主張 1:** $0 \leq r < b$  
$r \geq b$ と仮定すると、$a - (q+1)b = r - b \geq 0$  
よって、$a - (q+1)b \in S$ だが、$a -(q + 1)b < a - qb = r$ であり、$r$ が $S$ の最小要素であるという事実に矛盾する。  
したがって、$r < b$ となる。

**主張 2:** $q$ と $r$ は一意である。  
$a = qb + r = q^\prime b + r^\prime$ と仮定する。ここで、$q, q^\prime \in \mathbb{Z}$ かつ $0 \leq r, r^\prime < b$ である。  
よって、$r^\prime - r = (q - q^\prime)b$ となり、  
$|r^\prime - r| = |q - q^\prime|b$  
また、$|r^\prime - r| < b$ よって、$|q - q^\prime| < 1$ となり、  
したがって $q = q^\prime$ であり、$r = r^\prime$ となる。

# 一般化された割り算アルゴリズム

$a, b \in \mathbb{Z}$ かつ $b \neq 0$ のとき、次のような一意な $q, r \in \mathbb{Z}$ が存在する：

$$
a = qb + r \quad (0 \leq r < |b|)
$$

## 証明

もし $b < 0$ の場合、$|b| > 0$ である。

割り算アルゴリズムにより、$\exists\ q^\prime, r \in \mathbb{Z}$ で、$a = q^\prime |b| + r$ かつ $0 \leq r < |b|$ が成り立つ。

$|b| = -b$ なので、$a = q^\prime (-b) + r = (-q^\prime) b + r$ と書ける。

もし $q = -q^\prime$ と定義すれば、$a = qb + r$ となり、$0 \leq r < |b|$ が成り立つ。

## 例

$a = 61$, $b = -7$ とする。すると、

$$
61 = (-8)(-7) + 5
$$

となり、$q = -8$, $r = 5$ である。

# 応用

$b \in \mathbb{N}$ のとき、任意の整数 $a$ は次の形を持つ：

$$
a = qb + r \quad (q \in \mathbb{Z}, 0 \leq r < b)
$$

## 定義

$b = 2$ のとき、$a = 2q + r$ ($q \in \mathbb{Z}$, $0 \leq r < 2$)。

- $a = 2q$ のとき、$a$ は **偶数** と呼ばれる。
- $a = 2q + 1$ のとき、$a$ は **奇数** と呼ばれる。

## 例

任意の自然数 $a \in \mathbb{N}$ に対して、$N = \frac{1}{3}a(a^2 + 2)$ が整数であることを示せ。

{{< collapse summary="解法" >}}

$a = 3q + r$ ($q \in \mathbb{Z}$, $0 \leq r < 3$) とする。  
すなわち、$a = 3q$ または $a = 3q + 1$ または $a = 3q + 2$ のいずれかである。

1. $a = 3q$ の場合  
$$
N = \frac{1}{3}(3q)((3q)^2 + 2) = q(9q^2 + 2)
$$
2. $a = 3q + 1$ の場合  
$$
N = \frac{1}{3}(3q + 1)((3q + 1)^2 + 2) = (3q + 1)(3q^2 + 2q + 1)
$$
3. $a = 3q + 2$ の場合  
$$
N = \frac{1}{3}(3q + 2)((3q + 2)^2 + 2) = (3q + 2)(3q^2 + 4q + 2)
$$

{{< /collapse >}}
