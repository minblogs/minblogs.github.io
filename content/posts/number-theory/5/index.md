---
title: "서로소"
date: 2023-08-24
draft: false
tags: ["Math", "Number Theory"]
---

# 정의

$a, b \in \mathbb{Z}$ (단, 둘 중 적어도 하나는 0이 아님)에 대해,  
<div style="text-align: center;">
$a, b$가 <b>서로소</b>라고 함 $\overset{\text{def}}{\iff} \gcd(a, b) = 1$
</div>

## 예시

$\gcd(2, 5) = 1 \implies 2$와 $5$는 서로소이다.

# 정리 2.4

$a, b \in \mathbb{Z}$ (단, 둘 중 적어도 하나는 0이 아님)에 대해,  
$a, b$가 서로소 $\iff \exists\ x, y \in \mathbb{Z}$ such that $ax + by = 1$

> $a$와 $b$가 서로소 $\overset{\text{def}}{\iff} \gcd(a, b) = 1$

## 증명

$(\implies)$ $d = \gcd(a, b) = 1$일 때, [정리 2.3](/posts/number-theory/4/#theorem-23)을 사용한다.

$(\impliedby)$ 어떤 $x, y \in \mathbb{Z}$에 대해 $ax + by = 1$이라 가정하자. $d = \gcd(a, b)$라 하면  
$d \mid (ax + by) \implies d \mid 1 \implies d = 1$

# 따름정리 2.4.1

$\gcd(a, b) = d \implies \gcd\left(\frac{a}{d}, \frac{b}{d}\right) = 1$

> $\gcd(a, b) = d$이면, $a = dr$, $b = ds$인 $r, s \in \mathbb{Z}$가 존재하고, $\gcd(r, s) = 1$

## 증명

$\gcd(a, b) = d$이므로, 어떤 $x, y \in \mathbb{Z}$에 대해 $d = ax + by$이다.  
$\implies 1 = \frac{a}{d}x + \frac{b}{d}y$ 이고, $\frac{a}{d}, \frac{b}{d} \in \mathbb{Z}$

[정리 2.4](/posts/number-theory/5/#theorem-24)에 의해 $\gcd\left(\frac{a}{d}, \frac{b}{d}\right) = 1$

## 예시

$\gcd(-12, 30) = 6$, $\gcd\left(\frac{-12}{6}, \frac{30}{6}\right) = \gcd(-2, 5) = 1$

# 따름정리 2.4.2

$a \mid c$이고 $b \mid c$, 또한 $\gcd(a, b) = 1$이면 $ab \mid c$

## 증명

- $a \mid c$, $b \mid c$이면 $c = ar = bs$인 $r, s \in \mathbb{Z}$가 존재
- $\gcd(a, b) = 1 \implies 1 = ax + by$인 $x, y \in \mathbb{Z}$가 존재

$\implies c = c \cdot 1 = c(ax + by) = cax + cby = (bs)ax + (ar)by = ab(sx + ry)$  
$\implies ab \mid c$

## 비고

> 조건 "$\gcd(a, b) = 1$"은 반드시 필요함.

예: $6 \mid 24$, $8 \mid 24$이지만, $6 \cdot 8 = 48 \nmid 24$

# 정리 2.5 (유클리드의 보조정리)

$a \mid bc$이고 $\gcd(a, b) = 1$이면 $a \mid c$

## 증명

[정리 2.4](/posts/number-theory/5/#theorem-24)에 의해 $1 = ax + by$인 $x, y \in \mathbb{Z}$가 존재  
$\implies c = c(ax + by) = acx + bcy$

$a \mid acx$이고 $a \mid bcy$이므로 $a \mid c$

## 비고

> 조건 "$\gcd(a, b) = 1$"은 반드시 필요함.

예: $12 \mid (9 \cdot 8)$이지만, $12 \nmid 9$, $12 \nmid 8$

# 정리 2.6

$a, b \in \mathbb{Z}$ (단, 둘 중 적어도 하나는 0이 아님)에 대해,  
<div style="display: flex;">
  $d = \gcd(a, b)$ $\iff$
  <ol style="margin-top: 0">
    <li style="margin-top: 0"> $d \mid a$이고 $d \mid b$</li>
    <li> $c \mid a$ 및 $c \mid b$이면 $c \mid d$</li>
  </ol>
</div>

## 증명

$(\implies)$ $d = \gcd(a, b)$라고 하면, (1)은 자명하다.  
또한 어떤 $x, y \in \mathbb{Z}$에 대해 $d = ax + by$가 성립한다.  
$c \mid a$, $c \mid b$이면 $c \mid (ax + by)$이므로 $c \mid d$. 즉, (2)도 성립.

$(\impliedby)$ (1), (2)가 참이라 가정하자. 만약 어떤 $c \mid d$이면 $c \leq d$가 된다.  
따라서 $d = \gcd(a, b)$이다.
