---
title: "최대공약수"
date: 2023-08-23
draft: false
tags: ["Mathematics", "Number Theory"]
---

# 정의

$a, b \in \mathbb{Z}$&nbsp;일 때, **최대공약수** $d$&nbsp;는 다음 조건을 만족하는 양의 정수입니다:

1. $d \mid a$ 그리고 $d \mid b$
2. 만약 어떤 정수 $c$&nbsp;가 $a$&nbsp;와 $b$&nbsp;를 모두 나눈다면, $c \leq d$

이 경우 $a, b$&nbsp;의 최대공약수 $d$&nbsp;를 $\gcd(a, b)$&nbsp;라고 표기한다.


## 요약

1. $a$&nbsp;와 $b$&nbsp;의 모든 양의 약수를 구합니다.
2. 공통 약수를 찾습니다.
3. 그중 가장 큰 것을 선택합니다.

## 예시

$\gcd(-12, 30)$을 구해 봅시다.

1. 양의 약수들:
   - $-12$: $1, 2, 3, 4, 6, 12$
   - $30$: $1, 2, 3, 5, 6, 10, 15, 30$
2. 공통된 양의 약수들: $1, 2, 3, 6$
3. $\max\\{1, 2, 3, 6\\} = 6$

$\therefore \gcd(-12, 30) = 6$

일부 정수 $x, y$&nbsp;에 대해 $-12x + 30y$&nbsp;의 값을 계산해보면:

|  $x$ \\ $y$ |     -2   |     -1   |      0   |      1   |      2   | $\cdots$ |
|:-----------:|:--------:|:--------:|:--------:|:--------:|:--------:|:--------:|
|      -2     |    -36   |     -6   |     24   |     54   |     84   | $\cdots$ |
|      -1     |    -48   |    -18   |     12   |     42   |     72   | $\cdots$ |
|       0     |    -60   |    -30   |      0   |     30   |     60   | $\cdots$ |
|       1     |    -72   |    -42   |    -12   |     18   |     48   | $\cdots$ |
|       2     |    -84   |    -54   |    -24   |      6   |     36   | $\cdots$ |
|   $\vdots$  | $\vdots$ | $\vdots$ | $\vdots$ | $\vdots$ | $\vdots$ | $\ddots$ |

## 관찰

- 어떤 정수 $x, y$&nbsp;가 존재하여 $-12x + 30y = 6$을 만족합니다.
- 모든 값이 $6$&nbsp;의 배수입니다.  
  $\because -12x + 30y = 6(-2x + 5y)$

> 정리: $\boxed{\gcd(-12, 30) = 6}$

# 정리

$a, b \in \mathbb{Z}$&nbsp;이고 $(a \neq 0 \text{ 또는 } b \neq 0)$&nbsp;일 때, $d = \gcd(a, b)$&nbsp;라고 하자.  
그러면 $\exists x, y \in \mathbb{Z}$ s.t. $ax + by = d$

## 증명

$S := \\{au + bv > 0\ |\ u, v \in \mathbb{Z}\\}$&nbsp;라고 하자.

$a \neq 0$&nbsp;이라고 가정하자. ($b \neq 0$&nbsp;인 경우는 유사하게 증명됨)

**주장**: $S$&nbsp;는 공집합이 아니다.

- 만약 $a > 0$&nbsp;이면, $a = a \cdot 1 + b \cdot 0 > 0 \implies a \in S$
- 만약 $a < 0$&nbsp;이면, $-a = a \cdot (-1) + b \cdot 0 > 0 \implies -a \in S$

$\implies$ [정렬의 원리 (well-ordering principle)](/posts/number-theory/1/#정렬-원리)에 의해 $S$&nbsp;는 최소 원소 $d$&nbsp;를 갖는다. $\quad \cdots (\ast)$

$d = ax + by$&nbsp;인 어떤 정수 $x, y$&nbsp;가 존재함.

이제 우리가 증명할 것은 $d = \gcd(a, b)$&nbsp;라는 것이다.

1. $d \mid a$ 그리고 $d \mid b$
   - 나눗셈 알고리즘에 따라, $a = qd + r$&nbsp;인 $q, r \in \mathbb{Z}$&nbsp;가 존재하고 $0 \le r < d$
   - 만약 $r > 0$&nbsp;이면, 
   $$
   r = a - qd = a - q(ax + by) = a(1 - qx) + b(-qy)
   $$
   이므로 $r > 0 \implies r \in S$
   - 하지만 $r < d$&nbsp;이므로 $(\ast)$&nbsp;에 모순됨  
     $\implies r = 0 \implies a = qd \implies d \mid a$ (유사하게 $d \mid b$&nbsp;도 증명됨)

2. 만약 $c \mid a$&nbsp;이고 $c \mid b$&nbsp;라면 $c \le d$
   - 이때 $c \mid (ax + by)$&nbsp;이므로 $c \mid d \implies c \le d$

$\therefore d = \gcd(a, b)$

# 따름정리

$a, b \in \mathbb{Z}$&nbsp;이고 $(a \neq 0 \text{ 또는 } b \neq 0)$&nbsp;일 때, $d = \gcd(a, b)$&nbsp;라고 하자. 그러면

$$
\\{ax + by \mid x, y \in \mathbb{Z}\\} = \\{kd \mid k \in \mathbb{Z}\\}
$$

## 증명

위 정리에 따라 어떤 정수 $x_0, y_0$&nbsp;가 존재하여 $d = ax_0 + by_0$&nbsp;라고 하자.

1. $(B \subseteq A)$ $kd \in B$&nbsp;일 때, $kd = k(ax_0 + by_0) = a(kx_0) + b(ky_0) \in A$
2. $(A \subseteq B)$ $ax + by \in A$&nbsp;일 때,  
   $d = \gcd(a, b)$&nbsp;이므로 $a = dr$, $b = ds$&nbsp;인 정수 $r, s$&nbsp;가 존재함  
   따라서 $ax + by = drx + dsy = d(rx + sy) \in B$
