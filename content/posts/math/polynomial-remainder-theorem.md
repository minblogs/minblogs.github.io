---
title: "다항식의 나머지 정리"
date: 2020-06-04
draft: false
tags: ["Mathematics", "Algebra", "Polynomials"]
---

다항식의 나머지 정리(Polynomial Remainder Theorem)는 다항식의 나눗셈과 관련된 중요한 정리로, 다항식을 특정 값으로 나누었을 때의 나머지를 구하는 방법을 제공한다. 이 정리는 다음과 같이 요약할 수 있다:
> 다항식 $f(x)$가 주어졌을 때, $f(x)$를 $x - a$로 나누었을 때의 나머지는 $f(a)$이다.
이 정리는 다항식의 나눗셈을 단순화하고, 특정 값에서의 다항식의 값을 쉽게 계산할 수 있게 해준다.

다항식 $f(x)$&nbsp;를 $x^2-x+1$&nbsp;로 나누었을 때의 나머지는 $(k+1)x-k+1$&nbsp;이고, 
$x^2+x+1$&nbsp;로 나누었을 때의 나머지는 $(-k+1)x-k+1$&nbsp;일 때, 다음 물음에 답하시오.   
(단, $k$는 $0$이 아닌 실수)

1. 다항식 $f(x)$&nbsp;를 $x^3+1$&nbsp;로 나누었을 때의 나머지를 $x^2+ax-1$&nbsp;이라 할 때, 실수 $a, k$&nbsp;의 값을 각각 구하시오.

2. 다항식 $f(x)$&nbsp;를 $x^4+x^2+1$&nbsp;로 나누었을 때의 나머지를 $g(x)$&nbsp;라 할 때, $k$&nbsp;의 값에 관계 없이 함수 $y=g(x)$&nbsp;의 그래프와 항상 접하는 직선의 방정식을 구하시오.

## 풀이

### 1번

다항식 $f(x)$&nbsp;를 $x^2-x+1$&nbsp;로 나누었을 때의 나머지가 $(k+1)x-k+1$&nbsp;이므로,
$$
f(x) = (x^2 - x + 1)q(x) + (k+1)x - k + 1
$$
여기서 $q(x)$는 어떤 다항식이다.

다항식 $f(x)$&nbsp;를 $x^2+x+1$&nbsp;로 나누었을 때의 나머지가 $(-k+1)x-k+1$&nbsp;이므로,
$$
f(x) = (x^2 + x + 1)p(x) + (-k+1)x - k + 1
$$
여기서 $p(x)$는 또 다른 다항식이다.
이 두 식을 비교하면, 다음과 같은 관계를 얻을 수 있다:
$$
(x^2 - x + 1)q(x) - (x^2 + x + 1)p(x) + 2kx = 0
$$
이 식을 정리하면,
$$
(q(x) - p(x))x^2 - (q(x) + p(x) - 2k)x + (q(x) - p(x)) = 0
$$
$x$&nbsp;에 관계 없이 항등식 이므로, 각 항의 계수가 모두 0이어야 한다.
따라서 다음과 같은 연립 방정식을 얻는다:
$$
\begin{cases}
\begin{align*}
q(x) - p(x) &= 0 \\\\
q(x) + p(x) &= 2k
\end{align*}
\end{cases}
$$
이 연립 방정식에서 $q(x) = p(x)$&nbsp;이므로, $q(x) + p(x) = 2q(x) = 2k$&nbsp;가 된다.
따라서 $q(x) = k$&nbsp;가 되고, $p(x) = k$&nbsp;가 된다.

이제 $f(x)$&nbsp;를 구하기 위해, $q(x)$&nbsp;와 $p(x)$&nbsp;를 대입한다:
$$
f(x) = (x^2 - x + 1)k + (k+1)x - k + 1
$$
이 식을 정리하면,
$$
f(x) = kx^2 + x + 1
$$

이제 $f(x)$&nbsp;를 $x^3 + 1$&nbsp;로 나누었을 때의 나머지는 다음과 같다:
$$
f(x) = (x^3 + 1)h(x) + x^2 + ax - 1
$$

여기서 $h(x)$는 어떤 다항식이다. $x^3 + 1 = (x + 1)(x^2 - x + 1)$&nbsp;이므로,
$$
f(x) = (x + 1)(x^2 - x + 1)h(x) + x^2 + ax - 1
$$
이때, $f(x)$&nbsp;를 $x^2 - x + 1$&nbsp;로 나누었을 때의 나머지가 $(k+1)x - k + 1$&nbsp;이므로,
$$
x^2 + ax - 1 = x^2 - x + 1 + (a + 1)x - 2
$$
$(a + 1)x - 2 = (k + 1)x - k + 1$&nbsp;이고 $a = k, k = 3$&nbsp;이므로,

$\therefore \boxed{a = 3, k = 3}$

### 2번

다항식 $f(x)$&nbsp;를 $x^4 + x^2 + 1$&nbsp;로 나누었을 때의 나머지를 $g(x)$&nbsp;라고 할 때, $f(x)$&nbsp;는 다음과 같이 표현할 수 있다:
$$
f(x) = (x^4 + x^2 + 1)h(x) + g(x)
$$
여기서 $h(x)$는 어떤 다항식이다. $f(x)$&nbsp;는 이차식이므로, $g(x) = f(x)$&nbsp;가 된다.
따라서 $g(x) = kx^2 + x + 1$&nbsp;이다.

$y = g(x)$&nbsp;위의 점 $(t, g(t))$&nbsp;에서의 접선의 방정식은 다음과 같다:
$$
y = g'(t)(x - t) + g(t)
$$
여기서 $g'(x)$는 $g(x)$의 도함수이다. $g(x) = kx^2 + x + 1$&nbsp;이므로, $g'(x) = 2kx + 1$&nbsp;가 된다.
따라서 접선의 방정식은 다음과 같다:
$$
y = (2kt + 1)(x - t) + kt^2 + t + 1
$$
임의의 실수 $t$&nbsp;에 대해 접선 $y = (2kt + 1)(x - t) + kt^2 + t + 1$&nbsp;이 존재한다면 $t$&nbsp;에 대한 판별식 $D_t$&nbsp;는 0이어야 한다.
따라서 방정식 $-kt^2 + 2kxt + x - y + 1 = 0$ 의 판별식 $D_t$&nbsp;는 다음과 같다:
$$
D_t = (2kx)^2 - 4(-k)(x - y + 1) = 4k^2x^2 + 4k(x - y + 1)
$$
이 판별식이 항상 0이 되려면, $4x^2k^2 + 4(x - y + 1)k = 0$&nbsp;이어야 한다.
k가 0이 아닌 실수이므로, $k$에 대한 판별식 $D_k$&nbsp;는 다음과 같다:
$$
D_k = 16(x - y + 1)^2 = 0
$$
따라서 $x - y + 1 = 0$&nbsp;이므로, $\boxed{y = x + 1}$&nbsp;가 된다.