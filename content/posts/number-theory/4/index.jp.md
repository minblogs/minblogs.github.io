---
title: '最大公約数'
date: 2023-08-23
draft: false
tags: ['数学', '数論']
---

# 定義

$a, b \in \mathbb{Z}$ とする。**最大公約数** (greatest common divisor) とは、以下を満たす正の整数 $d$ のことをいう：

1. $d \mid a$ および $d \mid b$
2. 任意の $c$ に対して $c \mid a$ かつ $c \mid b$ ならば、$c \leq d$

このとき、$d = \gcd(a, b)$ と書く。

## 要約

- $a$ と $b$ の正の約数をすべて求める
- 共通の約数を見つける
- 最大のものを選ぶ

## 例題

$\gcd(-12, 30)$ を求めよ。

1. 正の約数の列挙
   - $-12$: $1, 2, 3, 4, 6, 12$
   - $30$: $1, 2, 3, 5, 6, 10, 15, 30$

2. 共通の正の約数: $1, 2, 3, 6$
3. よって $\therefore \gcd(-12, 30) = 6$

$x, y \in \mathbb{Z}$ に対する $-12x + 30y$ のいくつかの値：

|  $x$ \\ $y$ |     -2   |     -1   |      0   |      1   |      2   | $\cdots$ |
|:-----------:|:--------:|:--------:|:--------:|:--------:|:--------:|:--------:|
|      -2     |    -36   |     -6   |     24   |     54   |     84   | $\cdots$ |
|      -1     |    -48   |    -18   |     12   |     42   |     72   | $\cdots$ |
|       0     |    -60   |    -30   |      0   |     30   |     60   | $\cdots$ |
|       1     |    -72   |    -42   |    -12   |     18   |     48   | $\cdots$ |
|       2     |    -84   |    -54   |    -24   |      6   |     36   | $\cdots$ |
|   $\vdots$  | $\vdots$ | $\vdots$ | $\vdots$ | $\vdots$ | $\vdots$ | $\ddots$ |

## 観察

- ある $x, y \in \mathbb{Z}$ が存在して $-12x + 30y = 6$ を満たす
- 各値は $6$ の倍数である。  
  なぜなら、$-12x + 30y = 6(-2x + 5y)$ だから。

> 再確認：$\boxed{\gcd(-12, 30) = 6}$

# 定理

$a, b \in \mathbb{Z}\ (a \neq 0 \text{ または } b \neq 0)$ に対し、$d = \gcd(a, b)$ とすると、  
$\implies$ ある $x, y \in \mathbb{Z}$ が存在して $ax + by = d$ を満たす。

## 証明

$S := \\{au + bv > 0\ |\ u, v \in \mathbb{Z}\\}$ と定める。

$a \neq 0$ と仮定する（$b \neq 0$ の場合も同様に証明できる）。

**主張**：$S$ は空でない。

- $a > 0$ のとき、$a = a \cdot 1 + b \cdot 0 > 0 \implies a \in S$
- $a < 0$ のとき、$-a = a \cdot (-1) + b \cdot 0 > 0 \implies -a \in S$

よって、[整列定理 (well-ordering axiom)](/posts/number-theory/1/#well-ordering-principle) により、$S$ は最小の要素 $d$ をもつ：$d \in S \quad \cdots (\ast)$  

$d = ax + by$ となる $x, y \in \mathbb{Z}$ が存在するとする。

このとき、$d = \gcd(a, b)$ を示す（すなわち、$d = ax + by$）。

1. $d \mid a$ および $d \mid b$
   - 除算法により、$a = qd + r$ ($q, r \in \mathbb{Z}$、$0 \leq r < d$) が成り立つ
   - $r > 0$ と仮定すると、  
    $r = a - qd = a - q(ax + by) = a(1 - qx) + b(-qy) > 0 \implies r \in S$
   - しかし、$r < d$ は $(\ast)$ に矛盾する  
    よって $r = 0 \implies a = qd \implies d \mid a$（$b$ に関しても同様）
2. $c \mid a$ かつ $c \mid b$ ならば $c \leq d$  
  このとき、$c \mid (ax + by) \implies c \mid d \implies c \leq d$

したがって $\therefore d = \gcd(a, b)$

# 系（Corollary）

$a, b \in \mathbb{Z} (a \neq 0 \text{ または } b \neq 0)$ に対して $d = \gcd(a, b)$ とすると、

$$
\\{ax + by\ |\ x, y \in \mathbb{Z}\\} = \\{kd\ |\ k \in \mathbb{Z}\\}
$$

## 証明

定理より、ある $x_0, y_0 \in \mathbb{Z}$ が存在して $d = ax_0 + by_0$。

1. $(B \subseteq A)$：$kd \in B$ とする。すると  
   $kd = k(ax_0 + by_0) = a(kx_0) + b(ky_0) \in A$
2. $(A \subseteq B)$：$ax + by \in A$ とする。  
   $d = \gcd(a, b)$ なので、$a = dr,\ b = ds$ ($r, s \in \mathbb{Z}$) が存在する。  
   よって $ax + by = drx + dsy = d(rx + sy) \in B$
