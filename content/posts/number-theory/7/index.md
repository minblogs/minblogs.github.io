---
title: "최소공배수"
date: 2023-09-04
draft: false
tags: ["Mathematics", "Number Theory"]
---

# 정의 2.4

$a, b \in \mathbb{Z} \ (a \neq 0 \text{ 또는 } b \neq 0)$일 때, **최소공배수**(least common multiple) $m$은 다음 조건을   
만족하는 양의 정수이다.

1. $a \mid m$ 그리고 $b \mid m$
2. $a \mid c$ 이고 $b \mid c$&nbsp;이면, $m \leq c$

이 경우, $a, b$&nbsp;의 최소공배수 $m$을 $\mathrm{lcm}(a, b)$&nbsp;라고 표기한다.

# 정리 2.8

$$
\gcd(a, b) \cdot \mathrm{lcm}(a, b) = |a \cdot b|
$$

# 따름정리 2.8

모든 $a, b \in \mathbb{N}$&nbsp;에 대해, $\mathrm{lcm}(a, b) = ab \iff \gcd(a, b) = 1$

## 증명

$d = \gcd(a, b)$&nbsp;라고 하자. 그러면 어떤 $r, s \in \mathbb{Z}$가 존재하여 $a = dr$, $b = ds$로 쓸 수 있다.

$m := \frac{ab}{d}$&nbsp;라고 정의하자. 우리는 $m = \mathrm{lcm}(a, b)$임을 보일 것이다.

1. $m = as$&nbsp;이고 $m = br$&nbsp;이므로, $a \mid m$&nbsp;이고 $b \mid m$
2. 만약 어떤 정수 $c$&nbsp;에 대해 $a \mid c$&nbsp;이고 $b \mid c$&nbsp;라면, $c = au$ 그리고 $c = bv$&nbsp;인 $u, v \in \mathbb{Z}$가 존재한다.   
   또한 $d = \gcd(a, b)$&nbsp;이므로 정수 $x, y$가 존재하여 $d = ax + by$&nbsp;이다. 이때
   $$
   \frac{c}{m} = \frac{cd}{ab} = \frac{c(ax + by)}{ab} = \frac{(bv)(ax) + (au)(by)}{ab} = vx + uy
   $$
   즉, $m \mid c \implies m \leq c$

(1)과 (2)에 의해 $m = \mathrm{lcm}(a, b)$임을 알 수 있다.

따라서 $ab = dm = \gcd(a, b) \cdot \mathrm{lcm}(a, b)$가 된다.
