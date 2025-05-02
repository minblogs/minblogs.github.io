---
title: "약수와 배수"
date: 2023-08-22
draft: false
tags: ["Math", "Number Theory"]
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

# 정의

$a, b \in \mathbb{Z}$이고 $a \neq 0$일 때,

1. $a \mid b \overset{\text{def}}{\iff}$ 어떤 정수 $c$가 존재하여 $b = ac$인 경우, $b$는 $a$로 나누어떨어진다
2. $a \nmid b \overset{\text{def}}{\iff}$ $b$는 $a$로 나누어떨어지지 않는다

이때 $a$를 $b$의 **약수**(divisor 또는 factor), $b$를 $a$의 **배수**(multiple)라고 한다.

## 예시

$4 \mid 12$, $4 \mid (-12)$, $3 \nmid 10$

# 정리 (나눗셈의 성질)

$a, b, c \in \mathbb{Z}$일 때 다음이 성립한다:

1. $a \mid 0$, $1 \mid a$, $a \mid a$
2. $a \mid 1 \iff a = \pm 1$
3. $a \mid b$, $c \mid d \implies ac \mid bd$
4. $a \mid b$, $b \mid c \implies a \mid c$
5. $a \mid b$, $b \mid a \implies a = \pm b$
6. $a \mid b$, $b \neq 0 \implies |a| \leq |b|$
7. <mark>$a \mid b$, $a \mid c \implies$ 임의의 정수 $x, y$에 대해 $a \mid (bx + cy)$</mark>

## 증명

### (3) $a \mid b$, $c \mid d \implies ac \mid bd$

- $a \mid b \implies b = ar$ ($r \in \mathbb{Z}$)
- $c \mid d \implies d = cs$ ($s \in \mathbb{Z}$)

$\implies bd = (ar)(cs) = (ac)(rs) \implies ac \mid bd$

### (4) $a \mid b$, $b \mid c \implies a \mid c$

- $a \mid b \implies b = ar$ ($r \in \mathbb{Z}$)
- $b \mid c \implies c = bs$ ($s \in \mathbb{Z}$)

$\implies c = bs = (ar)s = a(rs) \implies a \mid c$

### (7) $a \mid b$, $a \mid c \implies$ 임의의 정수 $x, y$에 대해 $a \mid (bx + cy)$

- $a \mid b \implies b = ar$ ($r \in \mathbb{Z}$)
- $a \mid c \implies c = as$ ($s \in \mathbb{Z}$)

$\implies bx + cy = (ar)x + (as)y = a(rx + sy) \implies a \mid (bx + cy)$
