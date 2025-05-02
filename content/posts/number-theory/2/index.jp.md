---
title: "除法アルゴリズム"
date: 2023-08-19
draft: false
tags: ["Math", "Number Theory", "Algorithm"]
---

# 定理 2.1

$a, b \in \mathbb{Z}$ かつ $b > 0$ のとき、次を満たす一意な $q, r \in \mathbb{Z}$ が存在する。

$$
a = qb + r \quad (0 \leq r < b)
$$

このとき、$q$ は **商（quotient）**、$r$ は **剰余（remainder）** と呼ばれる。

## 例

1. $a = 23$, $b = 5$ $\implies 23 = 4 \cdot 5 + 3 \implies$ $q = 4$, $r = 3$
2. $a = -23$, $b = 5$ $\implies -23 = (-5) \cdot 5 + 2 \implies$ $q = -5$, $r = 2$

## 証明

次の集合を定義する：  
$S := \{a - xb \geq 0\ |\ x \in \mathbb{Z} \} \subseteq \mathbb{N} \cup \{0\}$  
$\implies S$ は空集合ではない。

> $\because\ a - (-|a|)b = a + |a|b \geq a + |a| \geq 0 \implies a - (-|a|)b \in S \implies S \neq \varnothing$

[整列原理](/posts/number-theory/1/#整列原理) より、$S$ には最小の元 $r \in S$ が存在する。

$$
r \in S \implies \exists\ q \in \mathbb{Z} \text{ に対して } a = qb + r \quad (r \geq 0)
$$

**主張 1：** $0 \leq r < b$  
$r \geq b$ と仮定すると、$a - (q+1)b = r - b \geq 0$  
$\implies a - (q+1)b \in S$ かつ $a - (q+1)b < r$ より、$r$ が最小という仮定に矛盾する。  
$\implies r < b$

**主張 2：** $q$ と $r$ は一意である。  
$a = qb + r = q^\prime b + r^\prime$ とする。ここで $q, q^\prime \in \mathbb{Z}$、$0 \leq r, r^\prime < b$  
$\implies r^\prime - r = (q - q^\prime)b \implies |r^\prime - r| = |q - q^\prime|b$  
また、$|r^\prime - r| < b$ より $|q - q^\prime| < 1 \implies q = q^\prime$、$r = r^\prime$ である。

# 系

$a, b \in \mathbb{Z}$ かつ $b \neq 0$ のとき、次を満たす一意な $q, r \in \mathbb{Z}$ が存在する。

$$
a = qb + r \quad (0 \leq r < |b|)
$$

## 証明

$b < 0$ の場合、$|b| > 0$。

除法アルゴリズムにより、$\exists\ q^\prime, r \in \mathbb{Z}$ に対して $a = q^\prime |b| + r$、$0 \leq r < |b|$。

$|b| = -b$ より、$a = q^\prime (-b) + r = (-q^\prime) b + r$

$q = -q^\prime$ とおくと、$a = qb + r$、$0 \leq r < |b|$ となる。

## 例

$a = 61$, $b = -7$ のとき、$61 = (-8)(-7) + 5$ である。したがって、$q = -8$, $r = 5$

# 応用

$b \in \mathbb{N}$ のとき、任意の整数 $a$ は次の形で表せる：

$$
a = qb + r \quad (q \in \mathbb{Z}, 0 \leq r < b)
$$

## 定義

$b = 2$ のとき、$a = 2q + r$ （$q \in \mathbb{Z}$, $0 \leq r < 2$）

- $a = 2q$ のとき、$a$ は **偶数（even）** と呼ばれる。
- $a = 2q + 1$ のとき、$a$ は **奇数（odd）** と呼ばれる。

## 例

任意の自然数 $a$ に対して $N = \frac{1}{3}a(a^2 + 2)$ が整数であることを示せ。

{{< collapse summary="解答を見る" >}}

$a = 3q + r$（$q \in \mathbb{Z}$、$0 \leq r < 3$）より  
$\implies a = 3q$ または $a = 3q + 1$ または $a = 3q + 2$

1. $a = 3q \implies N = \frac{1}{3}(3q)((3q)^2 + 2) = q(9q^2 + 2)$
2. $a = 3q + 1 \implies N = \frac{1}{3}(3q + 1)((3q + 1)^2 + 2) = (3q + 1)(3q^2 + 2q + 1)$
3. $a = 3q + 2 \implies N = \frac{1}{3}(3q + 2)((3q + 2)^2 + 2) = (3q + 2)(3q^2 + 4q + 2)$

すべてのケースにおいて $N$ は整数である。

{{< /collapse >}}
