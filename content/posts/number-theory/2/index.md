---
title: "나눗셈 알고리즘"
date: 2023-08-19
draft: false
tags: ["Mathematics", "Number Theory", "Algorithm"]
---

# 정리 2.1

$a, b \in \mathbb{Z}$&nbsp;이고 $b > 0$&nbsp;일 때, 다음을 만족하는 유일한 $q, r \in \mathbb{Z}$&nbsp;가 존재한다.

$$
a = qb + r \quad (0 \leq r < b)
$$

이때, $q$&nbsp;를 **몫(quotient)**, $r$&nbsp;을 <b>나머지(remainder)</b>라고 한다.

## 예시

1. $a = 23$, $b = 5$ $\implies 23 = 4 \cdot 5 + 3 \implies$ $q = 4$, $r = 3$
2. $a = -23$, $b = 5$ $\implies -23 = (-5) \cdot 5 + 2 \implies$ $q = -5$, $r = 2$

## 증명

다음 집합을 정의하자.  
$S := \\{a - xb \geq 0\ |\ x \in \mathbb{Z} \\} \subseteq \mathbb{N} \cup \\{0\\}$  
$\implies S$&nbsp;는 공집합이 아니다.

> $\because\ a - (-|a|)b = a + |a|b \geq a + |a| \geq 0 \implies a - (-|a|)b \in S \implies S \neq \varnothing$

[정렬 원리](/posts/number-theory/1/#정렬-원리)에 따라 $S$&nbsp;에는 최소 원소 $r \in S$&nbsp;가 존재한다.

$$
r \in S \implies \exists\ q \in \mathbb{Z} \text{ s.t. } a = qb + r \quad (r \geq 0)
$$

**주장 1:** $0 \leq r < b$  
$r \geq b$&nbsp;라고 가정하자. 그러면 $a - (q+1)b = r - b \geq 0$  
$\implies a - (q+1)b \in S$&nbsp;이고, $a - (q+1)b < r$&nbsp;이므로 $r$&nbsp;이 최소라는 가정에 모순이다.  
$\implies r < b$

**주장 2:** $q$&nbsp;와 $r$은 유일하다.  
$a = qb + r = q^\prime b + r^\prime$&nbsp;이라고 하자. 여기서 $q, q^\prime \in \mathbb{Z}$, $0 \leq r, r^\prime < b$  
$\implies r^\prime - r = (q - q^\prime)b \implies |r^\prime - r| = |q - q^\prime|b$  
또한 $|r^\prime - r| < b$&nbsp;이므로 $|q - q^\prime| < 1 \implies q = q^\prime$&nbsp;이고 $r = r^\prime$&nbsp;이다.

# 따름정리 (일반화된 나눗셈 알고리즘)

$a, b \in \mathbb{Z}$&nbsp;이고 $b \neq 0$&nbsp;일 때, 다음을 만족하는 유일한 $q, r \in \mathbb{Z}$&nbsp;가 존재한다.

$$
a = qb + r \quad (0 \leq r < |b|)
$$

## 증명

$b < 0$&nbsp;인 경우 $|b| > 0$&nbsp;이다.

나눗셈 알고리즘에 따라, $\exists\ q^\prime, r \in \mathbb{Z}$ s.t. $a = q^\prime|b| + r$&nbsp;이고 $0 \leq r < |b|$

$|b| = -b$&nbsp;이므로, $a = q^\prime(-b) + r = (-q^\prime)b + r$

$q = -q^\prime$&nbsp;라고 두면 $a = qb + r$&nbsp;이고 $0 \leq r < |b|$&nbsp;가 된다.

## 예시

$a = 61$, $b = -7$&nbsp;일 때, $61 = (-8)(-7) + 5$&nbsp;이므로 $q = -8$, $r = 5$&nbsp;이다.

# 응용

$b \in \mathbb{N}$&nbsp;일 때, 모든 정수 $a$&nbsp;는 다음 꼴로 쓸 수 있다.

$$
a = qb + r \quad (q \in \mathbb{Z}, 0 \leq r < b)
$$

## 정의

$b = 2$&nbsp;일 때, $a = 2q + r$ (단, $q \in \mathbb{Z}, 0 \leq r < 2$)

- $a = 2q$&nbsp;이면 $a$&nbsp;는 **짝수**라고 한다.
- $a = 2q + 1$&nbsp;이면 $a$&nbsp;는 **홀수**라고 한다.

## 예시

모든 자연수 $a$&nbsp;에 대해 $N = \frac{1}{3}a(a^2 + 2)$&nbsp;가 정수임을 보여라.

{{< collapse summary="풀이 보기" >}}

$a = 3q + r$ ($q \in \mathbb{Z}, 0 \leq r < 3$) 이므로  
$\implies a = 3q$ 또는 $a = 3q + 1$ 또는 $a = 3q + 2$

1. $a = 3q \implies N = \frac{1}{3}(3q)((3q)^2 + 2) = q(9q^2 + 2)$
2. $a = 3q + 1 \implies N = \frac{1}{3}(3q + 1)((3q + 1)^2 + 2) = (3q + 1)(3q^2 + 2q + 1)$
3. $a = 3q + 2 \implies N = \frac{1}{3}(3q + 2)((3q + 2)^2 + 2) = (3q + 2)(3q^2 + 4q + 2)$

모든 경우에서 $N$은 정수이다.

{{< /collapse >}}
