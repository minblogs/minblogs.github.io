---
title: 'Divisor and Multiple'
date: 2023-08-22
draft: false
tags: ['Math', 'Number Theory']
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

# Definition

Given $a, b \in \mathbb{Z}$ with $a \neq 0$,

1. $a \mid b \overset{\text{def}}{\iff}$ there exists $c \in \mathbb{Z}$ such that $b = ac$ ($b$ is divisible by $a$)
2. $a \nmid b \overset{\text{def}}{\iff}$ $b$ is not divisible by $a$

If $a$ is called a **divisor** (or **factor**) of $b$ and $b$ is called a **multiple** of $a$.

## Examples

$4 \mid 12$, $4 \mid (-12)$, $3 \nmid 10$

# Theorem (properties of divisibility)

Let $a, b, c \in \mathbb{Z}$. Then

1. $a \mid 0$, $1 \mid a$, $a \mid a$
2. $a \mid 1 \iff a = \pm 1$
3. $a \mid b$ and $c \mid d \implies ac \mid bd$
4. $a \mid b$ and $b \mid c \implies a \mid c$
5. $a \mid b$ and $b \mid a \implies a = \pm b$
6. $a \mid b$ and $b \neq 0 \implies |a| \leq |b|$
7. <mark> $a \mid b$ and $a \mid c \implies a \mid (bx + cy)$ for any $x, y \in \mathbb{Z}$ </mark>

## Proof

### (3) $a \mid b$ and $c \mid d$ $\implies$ $ac \mid bd$

- $a \mid b \implies b = ar$ for some $r \in \mathbb{Z}$
- $c \mid d \implies d = cs$ for some $s \in \mathbb{Z}$

$\implies bd = (ar)(cs) = (ac)(rs) \implies ac \mid bd$

### (4) $a \mid b$ and $b \mid c$ $\implies$ $a \mid c$

- $a \mid b \implies b = ar$ for some $r \in \mathbb{Z}$
- $b \mid c \implies c = bs$ for some $s \in \mathbb{Z}$

$\implies c = bs = (ar)s = a(rs) \implies a \mid c$

### (7) $a \mid b$ and $a \mid c \implies a \mid (bx + cy)$ for any $x, y \in \mathbb{Z}$

- $a \mid b \implies b = ar$ for some $r \in \mathbb{Z}$
- $a \mid c \implies c = as$ for some $s \in \mathbb{Z}$

$\implies bx + cy = (ar)x + (as)y = a(rx + sy) \implies a \mid (bx + cy)$