---
title: "수학적 귀납법과 이항 정리"
date: 2023-08-15
draft: false
tags: ["Mathematics", "Number Theory"]
---

# 정렬 원리

$S$ : $\mathbb{Z^+} = \\{0, 1, 2, \dots\\}$&nbsp;의 공집합이 아닌 부분집합이라 하자.  
$\implies$ 집합 $S$&nbsp;는 최소 원소를 가진다   
$\iff \exists\ a \in S$ s.t. $a \leq b$, $\forall\ b \in S$

# 정리 1.2

$S \subseteq \mathbb{N}$&nbsp;이 다음 조건을 만족한다고 하자.

1. $1 \in S$
2. 임의의 $k \in S$&nbsp;에 대해 $k + 1 \in S$

그렇다면 $S = \mathbb{N}$&nbsp;이다.

## 증명

$T := \mathbb{N} \setminus S$&nbsp;라고 하자. $T$&nbsp;가 공집합이 아니라고 가정하자.

$T \subset \mathbb{N}$&nbsp;이므로 [정렬 원리](#정렬-원리)에 따라 $T$&nbsp;는 최소 원소 $m \in T$&nbsp;를 가진다.

- $1 \notin T \implies m \geq 2 \implies m - 1 \in \mathbb{N}$
- $m \in T \implies m \notin S \implies m - 1 \notin S \implies m - 1 \in T$  
  이는 $m$&nbsp;이 $T$&nbsp;의 최소 원소라는 가정에 모순이다.

$\therefore$ $T$&nbsp;는 공집합이고 $\implies S = \mathbb{N}$&nbsp;이다.

## 예제

임의의 $n \in \mathbb{N}$&nbsp;에 대해 다음을 보여라.  
$1 + 2 + 3 + \cdots + n = \frac{n(n+1)}{2}$

{{<collapse summary="풀이 보기">}}

- $P(n) : 1 + 2 + 3 + \cdots + n = \frac{n(n+1)}{2}$
- $S := \\{n \in \mathbb{N}\ |\ P(n) \small\text{이 참인 경우}\\}$&nbsp;라고 정의하자.
   1. $1 \in S \iff P(1)$&nbsp;이 참이다. $\left(\because P(1) : 1 = \frac{1(1+1)}{2}\right)$
   2. $k \in S \implies k+1 \in S \iff P(k)$&nbsp;이 참이면 $P(k+1)$&nbsp;도 참이다.  
      $\because$ $1 + 2 + \cdots + k = \frac{k(k+1)}{2}$&nbsp;이라면,  
      $$
      \begin{align*}
      1 + 2 + \cdots + k + (k+1) &= \frac{k(k+1)}{2} + (k+1) \\\\
                                 &= \frac{k(k+1) + 2(k+1)}{2} \\\\
                                 &= \frac{(k+1)(k+2)}{2}
      \end{align*}
      $$

{{</collapse>}}

# 이항 계수

$n \in \mathbb{N}$&nbsp;이고 $0 \leq k \leq n$&nbsp;일 때, 다음과 같이 정의한다.

$$
\binom{n}{k} := \frac{n!}{k!(n-k)!}
$$

여기서 $n!$ (n의 팩토리얼)은 다음과 같이 정의된다:

$$
\begin{align*}
n! &= \prod_{k=1}^{n} k \\\\
   &= n \times (n-1) \times (n-2) \times \cdots \times 1
\end{align*}
$$

# 이항 정리

이항식 $(a + b)^n$&nbsp;의 전개는 다음과 같이 표현할 수 있다:

$$
\begin{align*}
(a+b)^n &= \sum_{k=0}^{n} \binom{n}{k} a^{n-k} b^k \\\\
&= a^n + n a^{n-1} b + \frac{n(n-1)}{2} a^{n-2} b^2 + \cdots + n b^{n-1} a + b^n
\end{align*}
$$
