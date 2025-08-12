---
id: Intro
aliases:
  - dp
tags:
  - dp
---

# Dynamic Programming

DP is Recursion + Storage at its roots.
Make a choice diagram to solve DP problems.

## How to Identify Dynamic Programming

1. Choice, Inclusion Exclusion
2. Optimality, Min, Max, etc nikaalo

Write recursive function first -> memoize -> top down

## Solving a DP Problem

Base Condition: Think of the smallest valid input.

Always call a smaller recursion: eg `return func(n-1)`

### Memoization

Create a matrix t of size n*m(also called matrix dp in some solutions)

A recursive call will be of the form f(constant inputs, changing inputs).

We have to create a matrix of the changing inputs.

One drawback could be that stack overflows due to function calls.

### Top Down Approach

Used to mitigate the stack overflow error.
You usually won't need to use this, stack overflow errors are pretty rare. One example is the Scrambled String problem on Leetcode.

In this approach, we omit the recursive call and only use tables. It works on the principle of breaking into subproblems.

We use the first row of the table for initialization. They are used for the base conditions.
