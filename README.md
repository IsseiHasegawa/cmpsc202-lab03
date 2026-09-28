# Lab 3: Asymptotic Analysis

This lab focuses on understanding and analyzing the asymptotic behavior of algorithms. We will explore concepts such as Big-O, Big-$\Theta$, and Big-$\Omega$ notations, and apply them to various algorithmic problems to determine their efficiency and scalability.

**Instructions:** To complete this lab, you may work in groups, but you must write your solutions yourself. Once you have completed the lab, push your changes to your forked repository.

## Problem 1

Suppose $T(n)$ is the worst case running time of an algorithm with input size $n$, and we know that $T(n)$ is $\mathcal{O}(n^3)$ and $\Omega(n^2)$. For each of the following statements, determine whether it must be true, must be false, or could be either true or false. Give a brief justification for each.

1. $T(n)$ is $\mathcal{O}(n^2)$.

Could be either true or false, because (T(n)) could be $n^2$, which is $\mathcal{O}(n^2)$, but it could also be $n^3$, which is not $\mathcal{O}(n^2)$.

2. $T(n)$ is $\Theta(n^3)$.

Could be either true or false, because $T(n)$ could be $n^3$, but it could also be $n^2$ or another function between $n^2$ and $n^3$.

3. $T(n)$ is $\Omega(n)$.

Must be true, because $T(n)$ is already known to be $\Omega(n^2)$. Since $n^2$ grows faster than $n$, $T(n)$ must also be $\Omega(n)$.

4. $T(n)$ is $\Theta(n^{1.5})$.

Must be false, because $n^{1.5}$ grows more slowly than $n^2$. This would contradict the fact that $T(n)$ is $\Omega(n^2)$.

5. $T(n)$ is $\mathcal{O}(n)$.

Must be false, because a function that is $\Omega(n^2)$ cannot also have an asymptotic upper bound of $\mathcal{O}(n)$.

6. $T(n)$ is $\Theta(n^2 \log n)$.

Could be either true or false, because $n^2 \log n$ grows faster than $n^2$ but slower than $n^3$. Therefore, it satisfies the given bounds, but $T(n)$ could also be another function such as $n^2$ or $n^3$.

## Problem 2

Consider the following algorithm where $f(A, i, j)$ is an unknown algorithm that takes as input an array $A$ and two indicies $i$ and $j$ and returns a number.

```
Mystery Algorithm
Input: An array of int $A$ of length $n$.
Output: int sum
    n = |A|
    sum = 0
    for i = 1 to n:
        for j = 1 to n:
            sum += f(A, i, j)
```

Without knowing anything about $f$, what can we say about the running time of the Mystery Algorithm in terms of $n$? Justify your answer.

The nested loops each run $n$ times, so the function $f(A,i,j)$ is called $n \times n = n^2$ times.

Without knowing the running time of $f$, we cannot give an exact upper bound for the entire Mystery Algorithm. However, the loops themselves require at least $\Omega(n^2)$ time because there are $n^2$ iterations.

If the running time of one call to $f$ is $F(n)$, then the total running time is $\Theta(n^2 F(n) + n^2)$.

If $f$ takes at least constant time, this can be written as $\Theta(n^2 F(n))$.

For example, if $f$ is $\Theta(1)$, the Mystery Algorithm is $\Theta(n^2)$. If $f$ is $\Theta(n)$, the Mystery Algorithm is $\Theta(n^3)$.

Therefore, without knowing anything about $f$, the strongest general statement is that the algorithm performs $n^2$ calls to $f$ and takes at least $\Omega(n^2)$ time, but we cannot determine a tighter upper bound.
