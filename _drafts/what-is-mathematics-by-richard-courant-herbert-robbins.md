---
layout: post
title: What Is Mathematics? by Richard Courant & Herbert Robbins
category: Notes
tags: [mathematics]
math: true
---
[*What Is Mathematics?: An Elementary Approach to Ideas and Methods*](https://en.wikipedia.org/wiki/What_Is_Mathematics%3F) by [Richard Courant](https://en.wikipedia.org/wiki/Richard_Courant) & [Herbert Robbins](https://en.wikipedia.org/wiki/Herbert_Robbins) was first published in 1941. A [second edition](https://www.amazon.com/dp/0195105192) was published in 1996 with an additional chapter on recent progress in mathematics, written by [Ian Stewart](https://ianstewartjoat.weebly.com/).

This book is an introduction to mathematics, intended both for the mathematics student and for the general public.

- toc
{: toc }

## Notes on Each Chapter

### Chapter I. The Natural Numbers

**The principle of mathematical induciton**: Suppose \\(A(n)\\) is a proposition involving a natural number \\(n\\). If \\(A(s)\\) is true for a natural number \\(s\\), and if \\(A(r)\\) implies \\(A(r+1)\\) for every natural number \\(r \geq s\\), then \\(A(n)\\) is true for every natural number \\(n \geq s\\).

We can use mathematical induction to prove some formulas.

**The arithmetical progression**:

$$
A_n = 1 + 2 + \cdots + n = \frac{n(n+1)}{2}
$$

Proof: \\(A_1 = 1(1+1)/2 = 1\\), so \\(A_1\\) is true. Suppose \\(A_n = n(n+1)/2\\), then

$$
A_{n+1} = A_n + (n+1) = \frac{(n+1)(n+2)}{2} = \frac{(n+1)((n+1)+1)}{2}
$$

This closes the induction. \\(\blacksquare\\)

**The geometrical progression**:

$$
G_n = 1 + q + q^2 + \cdots + q^n = \frac{1-q^{n+1}}{1-q}
$$

where \\(q \neq 1\\).

Proof: \\(G_0 = (1-q)/(1-q) = 1\\), so \\(G_0\\) is true. Suppose \\(G_n = (1-q^{n+1})/(1-q)\\), then

$$
G_{n+1} = G_n + q^{n+1} = \frac{1-q^{(n+1)+1}}{1-q}
$$

This closes the induction. \\(\blacksquare\\)

**The sum of squares**:

$$
S_n = 1^2 + 2^2 + \cdots + n^2 = \frac{n(n+1)(2n+1)}{6}
$$

Proof: \\(S_1 = 1(1+1)(2+1)/6 = 1\\), so \\(S_1\\) is true. Suppose \\(S_n = n(n+1)(2n+1)/6\\), then

$$
\begin{align}
S_{n+1} = S_n + (n+1)^2 & = \frac{n(n+1)(2n+1) + 6(n+1)^2}{6} \\
    & = \frac{(n+1)(n(2n+1)+6(n+1))}{6} \\
    & = \frac{(n+1)(2n^2 + 7n + 6)}{6} \\
    & = \frac{(n+1)(n+2)(2n+3)}{6} \\
    & = \frac{(n+1)((n+1)+1)(2(n+1)+1)}{6}
\end{align}
$$

This closes the induction. \\(\blacksquare\\)

**The sum of cubes**:

$$
C_n = 1^3 + 2^3 + \cdots + n^3 = [\frac{n(n+1)}{2}]^2
$$

Proof: \\(C_1 = [1(1+1)/2]^2 = 1\\), so \\(C_1\\) is true. Suppose \\(C_n = [n(n+1)/2]^2\\), then

$$
\begin{align}
C_{n+1} = C_n + (n+1)^3 & = [\frac{n(n+1)}{2}]^2 + (n+1)^3 \\
    & = \frac{(n(n+1))^2 + 4(n+1)^3}{4} \\
    & = \frac{(n+1)^2(n^2 + 4(n+1))}{4} \\
    & = \frac{(n+1)^2(n+2)^2}{4} \\
    & = [\frac{(n+1)((n+1)+1)}{2}]^2
\end{align}
$$

This closes the induction. \\(\blacksquare\\)

**An important inequality**:

$$
(1+p)^n \geq 1+np
$$

where \\(p \geq -1\\) and \\(n\\) is a natural number.

Proof: We use the induction on \\(n\\). When \\(n=0\\), \\((1+p)^0 = 1 = 1+0 \cdot p\\), so the base case is proved. Suppose the inequality holds for \\(n\\), then for \\(n+1\\), we have

$$
(1+p)^{n+1} = (1+p)^n (1+p)
$$

\\(1+p \geq 0\\) since \\(p \geq -1\\), so

$$
(1+p)^n (1+p) \geq (1+np)(1+p) = 1+(n+1)p+np^2 \geq 1+(n+1)p
$$

This closes the induction. \\(\blacksquare\\)

**The binomial expansion**:

$$
(a+b)^n = \sum_{i=0}^{n} C_{i}^{n} a^{n-i} b^{i}
$$

where \\(C_i^n\\) is called an element of Pascal's Triangle. It can be recursively defined as \\(C_0^n = 1, C_n^n = 1\\), and

$$
C_i^n = C_{i-1}^{n-1} + C_i^{n-1}, (0 < i < n)
$$

Proof: When \\(n=0\\), \\((a+b)^0 = C_0^0 a^0 b^0 = 1\\), so the base case is proved. Now suppose the expansion holds for \\(n\\), then

$$
(a+b)^{n+1} = (a+b)^n(a+b) = [\sum_{i=0}^{n} C_{i}^{n} a^{n-i} b^{i}](a+b)
$$

We can expand it into this form:

$$
\begin{align}
C_0^n a^{n+1} b^0 & + C_1^n a^n b^1 + C_2^n a^{n-1} b^2 + \cdots + C_n^n a^1 b^n \\
    & + C_0^n a^n b^1 + C_1^n a^{n-1} b^2 + \cdots + C_{n-1}^n a^1 b^n + C_n^n a^0 b^{n+1} \\
\end{align}
$$

By the definition of Pascal's Triangle, we can rewrite this sum as

$$
\sum_{i=0}^{n+1} a^{n+1-i} b^i
$$

This closes the induction. \\(\blacksquare\\)

**The binomial theorem**:

$$
C_i^n = \frac{n!}{i!(n-i)!}
$$

Proof: \\(C_0^0 = 0!/(0!(0-0)!) = 1\\), \\(C_0^1 = 1!/(0!(1-0)!) = 1\\), and \\(C_1^1 = 1!/(1!(1-1)!) = 1\\), so the base case is proved. Now suppose \\(C_i^n = n!/(i!(n-i)!)\\), then

$$
\begin{align}
C_i^{n+1} = C_{i-1}^{n} + C_i^{n} & = \frac{n!}{(i-1)!(n-(i-1))!} + \frac{n!}{i!(n-i)!} \\
    & = \frac{i \cdot n!}{i!(n+1-i)!} + \frac{(n+1-i) \cdot n!}{i!(n+1-i)!} \\
    & = \frac{(n+1)!}{i!(n+1-i)!}
\end{align}
$$

This closes the induction. \\(\blacksquare\\)

Mathematical induction can let us verify a theorem, but it doesn't provide us any hint of gaining the theorem.

### Supplement to Chapter I. The Theory of Numbers

### Chapter II. The Number System of Mathematics

### Supplement to Chapter II. The Algebra of Sets

### Chapter III. Geometrical Constructions. The Algebra of Number Fields

### Chapter IV. Projective Geometry. Axiomatics. Non-Euclidean Geometries

### Chapter V. Topology

### Chapter VI. Functions and Limits

### Supplement to Chapter VI. More Examples on Limits and Continuity

### Chapter VII. Maxima and Minima

### Chapter VIII. The Calculus

### Supplement to Chapter VIII

### Chapter IX. Recent Developments
