---
title: "나눗셈 알고리즘"
date: 2023-08-19
draft: false
tags: ["Math", "Number Theory", "Algorithm"]
---

# 정리

$a, b \in \mathbb{Z}$이고 $b > 0$일 때, 유일한 $q, r \in \mathbb{Z}$가 존재하여

$$
a = qb + r \quad (0 \leq r < b)
$$

를 만족한다. 이때, $q$를 **몫(quotient)**, $r$을 **나머지(remainder)** 라고 한다.

## 예시

1. $a = 23, b = 5 \implies 23 = 4 \cdot 5 + 3 \implies q = 4, r = 3$
2. $a = -23, b = 5 \implies -23 = (-5) \cdot 5 + 2 \implies q = -5, r = 2$

## 증명

$S := \\{a - xb \geq 0\ |\ x \in \mathbb{Z}\\} \subseteq \mathbb{N} \cup \\{0\\}$로 정의하자. 그러면 $S$는 공집합이 아니다.

> $\because a - (-|a|)b = a + |a|b \geq a + |a| \geq 0 \implies a - (-|a|)b \in S \implies S \neq \varnothing$

정렬 원리(Well-ordering Principle)에 의해, $S$는 최소 원소 $r \in S$를 가진다.

$$
r \in S \implies \exists\ q \in \mathbb{Z} \text{ s.t. } a = qb + r \quad (r \geq 0)
$$

**주장 1:** $0 \leq r < b$  
$r \geq b$라고 가정하자. 그러면 $a - (q+1)b = r - b \geq 0$이 되어  
$a - (q+1)b \in S$이다. 그런데 $a - (q+1)b < a - qb = r$이므로, 이는 $r$이 $S$의 최소 원소라는 사실에 모순된다.  
따라서 $r < b$이다.

**주장 2:** $q$와 $r$은 유일하다.  

$a = qb + r = q^\prime b + r^\prime$이라고 가정하자. 단, $q, q^\prime \in \mathbb{Z}$, $0 \leq r, r^\prime < b$

그러면  
$$
r^\prime - r = (q - q^\prime)b
$$
가 되어 양변에 절댓값을 취하면  
$$
|r^\prime - r| = |q - q^\prime||b|
$$
이다. 그런데 $|r^\prime - r| < b$이므로, $|q - q^\prime| < 1$이다.   
$q, q^\prime$는 모두 정수이므로, $q = q^\prime$이고 따라서 $r = r^\prime$이다.

# 일반화된 나눗셈 알고리즘

$a, b \in \mathbb{Z}$이고 $b \neq 0$일 때, 유일한 $q, r \in \mathbb{Z}$가 존재하여

$$
a = qb + r \quad (0 \leq r < |b|)
$$

를 만족한다.

## 증명

$b < 0$인 경우, $|b| > 0$이다.

나눗셈 알고리즘에 의해, $q^\prime, r \in \mathbb{Z}$가 존재하여 $a = q^\prime |b| + r$이고 $0 \leq r < |b|$이다.

$|b| = -b$이므로,

$$
a = q^\prime (-b) + r = (-q^\prime)b + r
$$

로 쓸 수 있다. 여기서 $q = -q^\prime$로 정의하면, $a = qb + r$이고 $0 \leq r < |b|$을 만족한다.

## 예시

$a = 61$, $b = -7$이라 하자. 그러면

$$
61 = (-8)(-7) + 5
$$

이므로, $q = -8$, $r = 5$이다.

# 응용

$b \in \mathbb{N}$일 때, 모든 정수 $a$는 다음과 같은 형태로 쓸 수 있다.

$$
a = qb + r \quad (q \in \mathbb{Z}, 0 \leq r < b)
$$

## 정의

특히, $b = 2$일 때 $a = 2q + r$ ($q \in \mathbb{Z}$, $0 \leq r < 2$)로 표현할 수 있다.

- $a = 2q$이면, $a$를 **짝수(even)** 라 한다.
- $a = 2q + 1$이면, $a$를 **홀수(odd)** 라 한다.

## 예시

모든 자연수 $a \in \mathbb{N}$에 대해

$$
N = \frac{1}{3}a(a^2 + 2)
$$

가 정수임을 보여라.

{{< collapse summary="풀이 보기" >}}

$a = 3q + r$ ($q \in \mathbb{Z}$, $0 \leq r < 3$)라 하자.  
즉, $a$는 $3q$, $3q+1$, $3q+2$ 중 하나이다.

1. $a = 3q$인 경우
$$
N = \frac{1}{3}(3q)((3q)^2 + 2) = q(9q^2 + 2)
$$

2. $a = 3q + 1$인 경우
$$
N = \frac{1}{3}(3q + 1)((3q + 1)^2 + 2) = (3q + 1)(3q^2 + 2q + 1)
$$

3. $a = 3q + 2$인 경우
$$
N = \frac{1}{3}(3q + 2)((3q + 2)^2 + 2) = (3q + 2)(3q^2 + 4q + 2)
$$

{{< /collapse >}}
