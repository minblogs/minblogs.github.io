---
title: "Diophantine Equation"
date: 2023-09-05
draft: false
tags: ["Mathematics", "Number Theory"]
---

# Theorem 2.9

1. $ax + by = c$ has a solution $\iff$ $d \mid c$, where $d = \gcd(a, b)$.
2. If $x_0$ and $y_0$ is any particular solution of $ax + by = c$, then all other solutions are given by
   $$
   x = x_0 + \frac{b}{d}t, \quad y = y_0 - \frac{a}{d}t
   $$
   where $t$ is any integer.

## Example

1. $3x + 6y = 18$ has solutions $\iff$ $\gcd(3, 6) = 3$ and $3 \mid 18$
2. $2x + 10y = 17$ has NO solutions $\iff$ $\gcd(2, 10) = 2$ and $2 \nmid 17$

## Proof (1)

$(\implies)$ Assume that $ax + by = c$ has a solution.   
Let $d = \gcd(a, b)$. Then $a = dr$ and $b = ds$ for some integers $r, s \in \mathbb{Z}$.   
$\implies c = ax + by = drx + dsy = d(rx + sy) \implies d \mid c$

$(\impliedby)$ By [Theorem 2.3](/posts/number-theory/4/#theorem-23), $\exists$ $x_0, y_0 \in \mathbb{Z}$ s.t. $d = ax_0 + by_0$,    
If $d \mid c$, then $c = dt$ for some $t \in \mathbb{Z}$.   
$\implies c = dt = a(tx_0) + b(ty_0) \implies ax + by = c$ has a solution.

## Proof (2)

Let $x', y'$ be any general solution of $ax + by = c$.   
Then $c = ax' + by' = a(x' - x_0) = b(y_0 - y')$

Note that $\exists$ relatively prime $r, s$ s.t. $a = dr$ and $b = ds$   
$\implies r(x' - x_0) = s(y_0 - y')$

Note that $r \mid s(y_0 - y')$ and $\gcd(r, s) = 1$   
$\implies$ By [Euclid's lemma](/posts/number-theory/5/#theorem-25-euclids-lemma), $r \mid (y_0 - y')$   
$\implies$ $y_0 - y' = rt$ for some $t \in \mathbb{Z}$   
$\implies$ $y' = y_0 - rt = y_0 - \frac{a}{d}t$ and $x' = x_0 + \frac{b}{d}t$

## Example

Consider the linear Diophantine equation $172x + 20y = 1000$

{{<collapse summary="Solution">}}
1. By [Euclidean algorithm](/posts/number-theory/6), we have
    $$
    \begin{align*}
    172 &= 8 \cdot 20 + 12 \\\\
    20 &= 1 \cdot 12 + 8 \\\\
    12 &= 1 \cdot 8 + 4 \\\\
    8 &= 2 \cdot 4 + 0
    \end{align*}
    $$
   $\implies \gcd(172, 20) = 4$. Since $4 \mid 1000$, the above equation has a solution.

   Then we have
    $$
    \begin{align*}
    4 &= 12 - 8 \\\\
      &= 12 - (20 - 12) \\\\
      &= 2 \cdot 12 - 20 \\\\
      &= 2 \cdot (172 - 8 \cdot 20) - 20 \\\\
      &= 2 \cdot 172 - 17 \cdot 20
    \end{align*}
    $$
    $\implies 1000 = 4 \cdot 250 = 172 \cdot (500) + 20 \cdot (-4250)$   
    $\implies x_0 = 500$ and $y_0 = -4250$ is a particular solution.
2. $x = 500 + \frac{20}{4}t = 500 + 5t$ and $y = -4250 - \frac{172}{4}t = -4250 - 43t$
3. If we want to find positive integer solutions, then $x > 0$ and $y > 0$
    
    <div style="text-align: center; margin: 1rem 0;">
      $500 + 5t > 0$ and $-4250 - 43t > 0$
    </div>
  $\iff -100 < t < -98.\text{xx} \iff t = -99 \implies x = 5$ and $y = 7$
{{</collapse>}}

# Corollary

If $\gcd(a, b) = 1$ and if $x_0, y_0$ is a particular solution of $ax + by = c$, then all solutions are given by $\forall t \in \mathbb{Z}$
$$
x = x_0 + bt, \quad y = y_0 - at
$$
