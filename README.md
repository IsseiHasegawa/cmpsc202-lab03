# Lab 3: Asymptotic Analysis

This lab focuses on understanding and analyzing the asymptotic behavior of algorithms. We will explore concepts such as Big-O, Big-$\Theta$, and Big-$\Omega$ notations, and apply them to various algorithmic problems to determine their efficiency and scalability.

**Instructions:** To complete this lab, you may work in groups, but you must write your solutions yourself. Once you have completed the lab, push your changes to your forked repository.

## Problem 1

Suppose $T(n)$ is the worst case running time of an algorithm with input size $n$, and we know that $T(n)$ is $\mathcal{O}(n^3)$ and $\Omega(n^2)$. For each of the following statements, determine whether it must be true, must be false, or could be either true or false. Give a brief justification for each.

1. $T(n)$ is $\mathcal{O}(n^2)$.
   could be either true or false, because (T(n)) could be (n^2), which is (\mathcal{O}(n^2)), but it could also be (n^3), which is not (\mathcal{O}(n^2)).

2. $T(n)$ is $\Theta(n^3)$.
3. $T(n)$ is $\Omega(n)$.
4. $T(n)$ is $\Theta(n^{1.5})$.
5. $T(n)$ is $\mathcal{O}(n)$.
6. $T(n)$ is $\Theta(n^2 \log n)$.

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
