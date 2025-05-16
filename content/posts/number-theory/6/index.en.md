---
title: "Euclidean Algorithm"
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

# Definition

1. $a = q_1 b + r_1$ with $0 \leq r_1 < b$   
If $r_1 = 0$, then $a = q_1 b$ and $\gcd(a, b) = b$.   
If $r_1 > 0$, then we go to the next step.
2. $b = q_2 r_1 + r_2$ with $0 \leq r_2 < r_1$   
If $r_2 = 0$, then we stop in this step.   
If $r_2 > 0$, then we go to the next step.
3. $r_1 = q_3 r_2 + r_3$ with $0 \leq r_3 < r_2$   
If $r_3 = 0$, then we stop in this step.   
If $r_3 > 0$, then we go to the next step.

Continuing this process repeatedly, we obtain the decreasing sequence

<div style="text-align: center;">
$b > r_1 > r_2 > r_3 > \cdots > r_n \geq 0$. (It must stop in finitely many steps.)
</div>

## Lemma

$a = qb + r \implies \gcd(a, b) = \gcd(b, r)$

## Proof

Let $d = \gcd(a, b)$.   

1. $d \mid a$ and $d \mid b \implies d \mid (a - qb) \implies d \mid r \implies d \mid b$ and $d \mid r$.
2. Let $c \mid b$ and $c \mid r \implies c \mid (qb + r) \implies c \mid a \implies c \mid a$ and $c \mid b$.  

Since $d = \gcd(a, b)$, we have $c \leq d$.

By (1) and (2), we have $d = \gcd(b, r)$.

$\therefore \gcd(a, b) = \gcd(b, r)$.

## Example

1. Find $\gcd(48, 18)$

{{<collapse summary="Solution">}}
The positive divisor of $48$: 1, 2, 3, 4, 6, 8, 12, 16, 24, 48.   
The positive divisor of $18$: 1, 2, 3, 6, 9, 18.   
$\implies$ The common positive divisor of $48$ and $18$: 1, 2, 3, 6

$\therefore \gcd(48, 18) = 6$
{{</collapse>}}

2. Find $\gcd(12378, 3054)$

{{<collapse summary="Solution">}}
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

# Application

Find $x, y \in \mathbb{Z}$ with $ax + by = \gcd(a, b)$

By [Theorem 2.3](/posts/number-theory/4/#theorem-23), $\exists\ x, y \in \mathbb{Z}$ s.t. $ax + by = \gcd(a, b)$

## Question

How can we find $x, y \in \mathbb{Z}$ s.t. $48x + 18y = 6$?

{{<collapse summary="Solution">}}
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

$\therefore x = -1, y = 3$
{{</collapse>}}

Remark: This solution is not unique. See Theorem 2.9.

## Example

How can we find $x, y \in \mathbb{Z}$ s.t. $12378x + 3054y = 6$?

{{<collapse summary="Solution">}}
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
$\therefore x = 132, y = -535$ are one of solutions of $12378x + 3054y = 6$
{{</collapse>}}

# Theorem 2.7

$k > 0$, $\gcd(ka, kb) = k \cdot \gcd(a, b)$

## Proof

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
