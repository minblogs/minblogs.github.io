---
title: '최대공약수'
date: 2023-08-23
draft: false
tags: ['Math', 'Number Theory']
---

# 정의

$a, b \in \mathbb{Z}$일 때, **최대공약수** $d$는 다음 조건을 만족하는 양의 정수입니다:

1. $d \mid a$ 그리고 $d \mid b$
2. 만약 어떤 정수 $c$가 $a$와 $b$를 모두 나눈다면, $c \leq d$

이 경우 우리는 $d = \gcd(a, b)$라고 씁니다.

## 요약

- $a$와 $b$의 모든 양의 약수를 구합니다.
- 공통 약수를 찾습니다.
- 그중 가장 큰 것을 선택합니다.

## 예시

$\gcd(-12, 30)$을 구해 봅시다.

1. 양의 약수들:
   - $-12$: $1, 2, 3, 4, 6, 12$
   - $30$: $1, 2, 3, 5, 6, 10, 15, 30$
2. 공통된 양의 약수들: $1, 2, 3, 6$
3. $\therefore \gcd(-12, 30) = 6$

일부 정수 $x, y$에 대해 $-12x + 30y$의 값을 계산해보면:

|  $x$ \\ $y$ |     -2   |     -1   |      0   |      1   |      2   | $\cdots$ |
|:-----------:|:--------:|:--------:|:--------:|:--------:|:--------:|:--------:|
|      -2     |    -36   |     -6   |     24   |     54   |     84   | $\cdots$ |
|      -1     |    -48   |    -18   |     12   |     42   |     72   | $\cdots$ |
|       0     |    -60   |    -30   |      0   |     30   |     60   | $\cdots$ |
|       1     |    -72   |    -42   |    -12   |     18   |     48   | $\cdots$ |
|       2     |    -84   |    -54   |    -24   |      6   |     36   | $\cdots$ |
|   $\vdots$  | $\vdots$ | $\vdots$ | $\vdots$ | $\vdots$ | $\vdots$ | $\ddots$ |

## 관찰

- 어떤 정수 $x, y$가 존재하여 $-12x + 30y = 6$을 만족합니다.
- 모든 값이 $6$의 배수입니다.  
  $\because -12x + 30y = 6(-2x + 5y)$

> 정리: $\boxed{\gcd(-12, 30) = 6}$

# 정리

$a, b \in \mathbb{Z}$이고 $(a \neq 0 \text{ 또는 } b \neq 0)$일 때, $d = \gcd(a, b)$라고 하자.  
그러면 $\exists x, y \in \mathbb{Z}$ s.t. $ax + by = d$

## 증명

$S := \\{au + bv > 0\ |\ u, v \in \mathbb{Z}\\}$라고 하자.

$a \neq 0$이라고 가정하자. ($b \neq 0$인 경우는 유사하게 증명됨)

**주장**: $S$는 공집합이 아니다.

- 만약 $a > 0$이면, $a = a \cdot 1 + b \cdot 0 > 0 \implies a \in S$
- 만약 $a < 0$이면, $-a = a \cdot (-1) + b \cdot 0 > 0 \implies -a \in S$

$\implies$ [정렬의 원리 (well-ordering principle)](/posts/number-theory/1/#정렬-원리)에 의해 $S$는 최소 원소 $d$를 갖는다. $\quad \cdots (\ast)$

$d = ax + by$인 어떤 정수 $x, y$가 존재함.

이제 우리가 증명할 것은 $d = \gcd(a, b)$라는 것이다.

1. $d \mid a$ 그리고 $d \mid b$
   - 나눗셈 알고리즘에 따라, $a = qd + r$인 $q, r \in \mathbb{Z}$가 존재하고 $0 \le r < d$
   - 만약 $r > 0$이면, 
   $$
   r = a - qd = a - q(ax + by) = a(1 - qx) + b(-qy)
   $$
   이므로 $r > 0 \implies r \in S$
   - 하지만 $r < d$이므로 $(\ast)$에 모순됨  
     $\implies r = 0 \implies a = qd \implies d \mid a$ (유사하게 $d \mid b$도 증명됨)

2. 만약 $c \mid a$이고 $c \mid b$라면 $c \le d$
   - 이때 $c \mid (ax + by)$이므로 $c \mid d \implies c \le d$

$\therefore d = \gcd(a, b)$

# 따름정리

$a, b \in \mathbb{Z}$이고 $(a \neq 0 \text{ 또는 } b \neq 0)$일 때, $d = \gcd(a, b)$라고 하자. 그러면

$$
\{ax + by \mid x, y \in \mathbb{Z}\} = \{kd \mid k \in \mathbb{Z}\}
$$

## 증명

위 정리에 따라 어떤 정수 $x_0, y_0$가 존재하여 $d = ax_0 + by_0$라고 하자.

1. $(B \subseteq A)$: $kd \in B$일 때, $kd = k(ax_0 + by_0) = a(kx_0) + b(ky_0) \in A$
2. $(A \subseteq B)$: $ax + by \in A$일 때,  
   $d = \gcd(a, b)$이므로 $a = dr$, $b = ds$인 정수 $r, s$가 존재함  
   따라서 $ax + by = drx + dsy = d(rx + sy) \in B$
