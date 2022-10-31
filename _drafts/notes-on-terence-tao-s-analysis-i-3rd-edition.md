---
layout: post
title: Notes on Terence Tao's Analysis I, 3rd Edition
category: Notes
tags: [mathematics, analysis]
math: true
---
[Terence Tao](https://terrytao.wordpress.com/)’s two-volume book *Analysis* is an expanded and cleaned-up version of his lecture notes for an [analysis course](https://www.math.ucla.edu/~tao/resource/general/131ah.1.03w/) at [UCLA](https://www.ucla.edu/). It was first published in 2006. Here are some notes I took from the [first volume](https://terrytao.wordpress.com/books/analysis-i/) of the [3rd edition](https://link.springer.com/book/10.1007/978-981-10-1789-6), which was published in 2016.

- toc
{: toc }

## Chapter 2. Starting at the beginning: the natural numbers

### 2.1 The Peano axioms

The Peano axioms use only two fundamental concepts to build the natural number system: 0 and incrementing.

> Axiom 2.1. 0 is a natural number.

> Axiom 2.2. If \\(n\\) is a natural number, then \\(n++\\) is also a natural number.

These two axioms can't prevent the "wrap-around-to-zero" issue, e.g., \\(3++ = 0\\). So we need to import the third axiom:

> Axiom 2.3. 0 is not the successor of any natural number; i.e., we have \\(n++ \neq 0\\) for every natural number \\(n\\).

But these three axioms still can't prevent the "wrap-around-to-non-zero" issue, e.g., \\(3++ = 1++\\). So we need to import the fourth axiom:

> Axiom 2.4. Different natural numbers must have different successors; i.e., if \\(n, m\\) are natural numbers and \\(n \neq m\\), then \\(n++ \neq m++\\). Equivalently, if \\(n++ = m++\\), then we must have \\(n = m\\).

There is still a case that can't be avoided by only these four axioms: there may be some "rogue" elements being included in the natural number system. An informal example:

$$
\mathbf{N} := \{0,0.5,1,1.5,2,2.5,3,3.5,\cdots\}
$$

It is informal because we haven't defined real numbers yet, but once we do it, we can make this example.

We can include the fifth axiom to resolve this problem:

> Axiom 2.5 (Principle of mathematical induction). Let \\(P(n)\\) be any property pertaining to a natural number \\(n\\). Suppose that \\(P(0)\\) is true, and suppose that whenever \\(P(n)\\) is true, \\(P(n++)\\) is also true. Then \\(P(n)\\) is true for every natural number \\(n\\).

Let \\(P(n)\\) be "\\(n\\) is not a half-integer." \\(P(0)\\) is true, and if \\(P(n)\\) is true, then \\(P(n++)\\) is also true. Thus, \\(P(n)\\) is true for every natural number \\(n\\), i.e., every natural number is not a half-integer. This result can cull "rogue" elements mentioned in the above example.

### 2.2 Addition
