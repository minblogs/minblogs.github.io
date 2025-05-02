---
title: "数学的帰納法と二項定理"
date: 2023-08-15
draft: false
tags: ["Math", "Number Theory"]
---

# 整列原理

自然数全体の集合 $\mathbb{N}$ の空でない部分集合 $S$ は、最小の要素を持つ。  
すなわち、$\exists\ a \in S$ かつ $\forall\ b \in S,\ a \leq b$ となる。

# 数学的帰納法

自然数の部分集合 $S$ が次の条件を満たすと仮定する。

1. $1$ は $S$ に属する。
2. 任意の自然数 $k$ に対して、もし $k \in S$ ならば $k+1 \in S$ である。

このとき、$S = \mathbb{N}$ が成り立つ。

## 証明

集合 $T := \mathbb{N} \setminus S$ を定義し、$T$ が空集合でないと仮定する。

$T \subset \mathbb{N}$ なので、[整列原理](#整列原理)により $T$ は最小元素を有する。この最小元を $m$ とする。

- まず、$m = 1$ の場合を考える。仮定より $1 \in S$ なので、$1 \notin T$ でなければならない。これは矛盾する。
- 次に、$m > 1$ の場合を考える。このとき $m-1$ は自然数であり、$m-1 \in \mathbb{N}$ である。また、$m$ は $T$ の最小元なので、$m-1 \in S$ でなければならない。さらに、仮定より $k \in S$ ならば $k+1 \in S$ なので、$m-1 \in S$ ならば $m = (m-1)+1 \in S$ となる。これは $m \in T$ という仮定と矛盾する。

よって、$T$ は空集合であり、$S = \mathbb{N}$ が成り立つ。

## 例題

任意の自然数 $n \in \mathbb{N}$ に対して、次の等式を示せ：

$$
1 + 2 + 3 + \cdots + n = \frac{n(n+1)}{2}
$$

{{<collapse summary="解答">}}

- 命題 $P(n)$：$1 + 2 + 3 + \cdots + n = \frac{n(n+1)}{2}$
- 集合 $S := \\{n \in \mathbb{N}\ |\ P(n) \text{ が成り立つ}\\}$ を定義する。
   1. $1 \in S \iff P(1)$ が真（$\because\ P(1) : 1 = \frac{1(1+1)}{2}$）
   2. $k \in S$ のとき、$k+1 \in S$ であることを示す：  
      すなわち $P(k)$ が真ならば $P(k+1)$ も真である。  
      $\because$ 仮定より $1 + 2 + \cdots + k = \frac{k(k+1)}{2}$ のとき、
      $$
      \begin{align*}
      1 + 2 + \cdots + k + (k+1) &= \frac{k(k+1)}{2} + (k+1) \\\\
                                 &= \frac{k(k+1) + 2(k+1)}{2} \\\\
                                 &= \frac{(k+1)(k+2)}{2}
      \end{align*}
      $$
      よって $P(k+1)$ も成り立つ。

{{</collapse>}}

# 二項係数

$n \in \mathbb{N}$、$0 \leq k \leq n$ のとき、二項係数は次のように定義される。
$$
\binom{n}{k} := \frac{n!}{k!(n-k)!}
$$

ここで、$n!$ は自然数 $n$ の階乗を意味し、$n$-ファクトリアル(factorial)は次のように計算される。

$$
\begin{align*}
n! &= \prod_{k=1}^{n} k \\\\
   &= n \times (n-1) \times (n-2) \times \cdots \times 1
\end{align*}
$$

# 二項定理

二項定理とは、$(a + b)^n$ を二項係数を用いた項の和として展開する公式である。

$$
\begin{align*}
(a+b)^n &= \sum_{k=0}^{n} \binom{n}{k} a^{n-k} b^k \\\\
&= a^n + n a^{n-1} b + \frac{n(n-1)}{2} a^{n-2} b^2 + \cdots + n b^{n-1} a + b^n
\end{align*}
$$
