---
title: "유클리드 호제법"
date: 2023-09-02
draft: false
tags: ["Mathematics", "Number Theory", "Algorithm", "Euclidean Algorithm"]
---

<style>
  span.katex-display {
    width: fit-content;
    height: fit-content;
  }
</style>

# 정의

1. $a = q_1 b + r_1$ (단, $0 \leq r_1 < b$)   
$r_1 = 0$이면 $a = q_1 b$이고 $\gcd(a, b) = b$이다.  
$r_1 > 0$이면 다음 단계로 진행한다.
2. $b = q_2 r_1 + r_2$ (단, $0 \leq r_2 < r_1$)  
$r_2 = 0$이면 여기서 중단한다.  
$r_2 > 0$이면 다음 단계로 진행한다.
3. $r_1 = q_3 r_2 + r_3$ (단, $0 \leq r_3 < r_2$)  
$r_3 = 0$이면 여기서 중단한다.  
$r_3 > 0$이면 다음 단계로 진행한다.

이 과정을 반복하면 다음과 같은 감소 수열을 얻게 된다:

<div style="text-align: center;">
$b > r_1 > r_2 > r_3 > \cdots > r_n \geq 0$ (이 과정은 유한한 단계 내에 반드시 종료된다.)
</div>

## 보조정리 (Lemma)

$a = qb + r \implies \gcd(a, b) = \gcd(b, r)$

## 증명

$d = \gcd(a, b)$라고 하자.

1. $d \mid a$ 그리고 $d \mid b$ 이므로, $d \mid (a - qb) \implies d \mid r \implies d \mid b$, $d \mid r$.
2. 어떤 수 $c$가 $b \mid c$ 이고 $r \mid c$ 이면, $c \mid (qb + r) \implies c \mid a \implies c \mid a$, $c \mid b$.

$d = \gcd(a, b)$이므로 $c \leq d$임.

(1)과 (2)에 의해 $d = \gcd(b, r)$이 성립함.

$\therefore \gcd(a, b) = \gcd(b, r)$

## 예제

1. $\gcd(48, 18)$을 구하라.

{{<collapse summary="풀이 보기">}}
$48$의 양의 약수: 1, 2, 3, 4, 6, 8, 12, 16, 24, 48  
$18$의 양의 약수: 1, 2, 3, 6, 9, 18  
$\implies$ 공통된 양의 약수: 1, 2, 3, 6

$\therefore \gcd(48, 18) = 6$
{{</collapse>}}

2. $\gcd(12378, 3054)$를 구하라.

{{<collapse summary="풀이 보기">}}
$$
\begin{align*}
12378 &= 4 \cdot 3054 + 162 \\\\
3054 &= 18 \cdot 162 + 138 \\\\
162 &= 1 \cdot 138 + 24 \\\\
138 &= 5 \cdot 24 + 18 \\\\
24 &= 1 \cdot 18 + 6 \\\\
18 &= 3 \cdot 6
\end{align*}
$$

$\therefore \gcd(12378, 3054) = 6$
{{</collapse>}}

# 활용

$x, y \in \mathbb{Z}$ 중 $ax + by = \gcd(a, b)$를 만족하는 정수를 구하라.

[정리 2.3](/posts/number-theory/4/#theorem-23)에 의해 $\exists\ x, y \in \mathbb{Z}$ s.t. $ax + by = \gcd(a, b)$

## 질문

$48x + 18y = 6$을 만족하는 $x, y \in \mathbb{Z}$를 구하라.

{{<collapse summary="풀이 보기">}}
<div style="display: flex; justify-content: space-around">

$$
\begin{align*}
48 &= 2 \cdot 18 + 12 \\\\
18 &= 1 \cdot 12 + 6 \\\\
12 &= 2 \cdot 6
\end{align*}
$$

$$
\begin{align*}
6 &= 18 - 1 \cdot 12 \\\\
&= 18 - 1 \cdot (48 - 2 \cdot 18) \\\\
&= 48 \cdot (-1) + 18 \cdot 3
\end{align*}
$$
</div>
$\implies 48 \cdot (-1) + 18 \cdot 3 = 6$

$\therefore x = -1,\ y = 3$
{{</collapse>}}

※ 주의: 이 해는 유일하지 않음. 정리 2.9 참고.

## 예제

$12378x + 3054y = 6$을 만족하는 정수 $x, y$를 구하라.

{{<collapse summary="풀이 보기">}}
$$
\begin{align*}
12378 &= 4 \cdot 3054 + 162 \\\\
3054 &= 18 \cdot 162 + 138 \\\\
162 &= 1 \cdot 138 + 24 \\\\
138 &= 5 \cdot 24 + 18 \\\\
24 &= 1 \cdot 18 + 6 \\\\
18 &= 3 \cdot 6 \\\\
\ \\\\
\implies &\gcd(12378, 3054) = 6 \\\\
\ \\\\ 
6 &= 24 - 18 \\\\
&= 24 - (138 - 5 \cdot 24) \\\\
&= -138 + 6 \cdot 24 = -138 + 6 \cdot (162 - 138) \\\\
&= 6 \cdot 162 -7 \cdot 138 \\\\
&= 6 \cdot 162 -7 \cdot (3054 - 18 \cdot 162) \\\\
&= 132 \cdot 162 + 3054 \cdot (-7) \\\\
&= 132 \cdot (12378 - 4 \cdot 3054) + 3054 \cdot (-7) \\\\
&= 12378 \cdot 132 + 3054 \cdot (-535)
\end{align*}
$$
$\therefore x = 132,\ y = -535$는 $12378x + 3054y = 6$의 해 중 하나이다.
{{</collapse>}}

# 정리 2.7

$k > 0$일 때, $\gcd(ka, kb) = k \cdot \gcd(a, b)$

## 증명

$$
\begin{align*}
a &= q_1 b + r_1, & 0 &< r_1 < b \\\\
b &= q_2 r_1 + r_2, & 0 &< r_2 < r_1 \\\\
r_1 &= q_3 r_2 + r_3, & 0 &< r_3 < r_2 \\\\
& \qquad \qquad \vdots \\\\
r_{n-2} &= q_{n} r_{n-1} + r_n, & 0 &< r_n < r_{n-1} \\\\
r_{n-1} &= q_{n+1} r_n \\\\
\ \\\\ 
\implies &\gcd(a, b) = r_n \\\\
\ \\\\ 
ka &= q_1 (kb) + kr_1, & 0 &< kr_1 < kb \\\\
kb &= q_2 (kr_1) + kr_2, & 0 &< kr_2 < kr_1 \\\\
kr_1 &= q_3 (kr_2) + kr_3, & 0 &< kr_3 < kr_2 \\\\
& \qquad \qquad \vdots \\\\
kr_{n-2} &= q_{n} (kr_{n-1}) + kr_n, & 0 &< kr_n < kr_{n-1} \\\\
kr_{n-1} &= q_{n+1} (kr_n)
\end{align*}
$$
$\therefore \gcd(ka, kb) = \gcd(kb, kr_1) = \cdots = \\\\ \gcd(kr_{n-1}, kr_n) = kr_n = k \cdot \gcd(a, b)$
