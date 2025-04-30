---
title: '約数と倍数'
date: 2023-08-22
draft: false
tags: ['数学', '数論']
---

<style>
  mark {
    background-color:rgba(255, 243, 176, 0.4);
    color: rgb(31, 31, 31);
  }

  body.dark mark {
    background-color:rgba(102, 92, 0, 0.4);
    color:rgb(196, 196, 197);
  }
</style>

# 定義

$a, b \in \mathbb{Z}$ かつ $a \neq 0$ のとき、

1. $a \mid b \overset{\text{def}}{\iff}$ $b = ac$ を満たす $c \in \mathbb{Z}$ が存在する（$b$ は $a$ で割り切れる）
2. $a \nmid b \overset{\text{def}}{\iff}$ $b$ は $a$ で割り切れない

このとき、$a$ は $b$ の **約数**（または **因数**）、$b$ は $a$ の **倍数** と呼ばれる。

## 例

$4 \mid 12,\ 4 \mid (-12),\ 3 \nmid 10$

# 定理（整除性の性質）

$a,\ b,\ c \in \mathbb{Z}$ のとき、以下が成り立つ：

1. $a \mid 0,\ 1 \mid a,\ a \mid a$
2. $a \mid 1 \iff a = \pm 1$
3. $a \mid b$ および $c \mid d \implies ac \mid bd$
4. $a \mid b$ および $b \mid c \implies a \mid c$
5. $a \mid b$ および $b \mid a \implies a = \pm b$
6. $a \mid b$ かつ $b \neq 0 \implies |a| \leq |b|$
7. <mark>$a \mid b,\ a \mid c$ のとき、任意の $x, y \in \mathbb{Z}$ に対して $a \mid (bx + cy)$</mark>

## 証明

### (3) $a \mid b$ および $c \mid d \implies ac \mid bd$

- $a \mid b \implies b = ar$ （ただし $r \in \mathbb{Z}$）
- $c \mid d \implies d = cs$ （ただし $s \in \mathbb{Z}$）

$\implies bd = (ar)(cs) = (ac)(rs) \implies ac \mid bd$

### (4) $a \mid b$ および $b \mid c \implies a \mid c$

- $a \mid b \implies b = ar$ （ただし $r \in \mathbb{Z}$）
- $b \mid c \implies c = bs$ （ただし $s \in \mathbb{Z}$）

$\implies c = bs = (ar)s = a(rs) \implies a \mid c$

### (7) $a \mid b,\ a \mid c$ のとき、任意の $x, y \in \mathbb{Z}$ に対して $a \mid (bx + cy)$

- $a \mid b \implies b = ar$ （ただし $r \in \mathbb{Z}$）
- $a \mid c \implies c = as$ （ただし $s \in \mathbb{Z}$）

$\implies bx + cy = (ar)x + (as)y = a(rx + sy) \implies a \mid (bx + cy)$