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

The addition is a repetition of increment.

> Definition 2.2.1 (Addition of natural numbers). Let \\(m\\) be a natural number. To add zero to \\(m\\), we define \\(0 + m := m\\). Now suppose inductively that we have defined how to add \\(n\\) to \\(m\\). Then we can add \\(n++\\) to \\(m\\) by defining \\((n++) + m := (n + m)++\\).

> Lemma 2.2.2. For any natural number \\(n\\), \\(n + 0 = n\\).

Proof: For \\(n=0\\), we have \\(0+0=0\\) since the definition of addition. Also, we have \\((n++)+0=(n+0)++\\) since the definition of addition. If we suppose \\(n + 0 = n\\), then we have \\((n++)+0 = n++\\). \\(\blacksquare\\)

> Lemma 2.2.3. For any natural numbers \\(n\\) and \\(m\\), \\(n + (m++) = (n + m)++\\).

Proof: For \\(n=0\\), we have \\(0+(m++)=m++=(0+m)++\\) since the definition of addition. Also, we have

$$
(n++) + (m++) = (n+(m++))++
$$

and

$$
((n++)+m)++ = ((n+m)++)++
$$

since the definition of addition.

So if we suppose \\(n+(m++) = (n+m)++\\), then we have

$$
(n++) + (m++) = ((n++)+m)++
$$

This closes the induction. \\(\blacksquare\\)

> Proposition 2.2.4 (Addition is commutative). For any natural numbers \\(n\\) and \\(m\\), \\(n+m=m+n\\).

Proof: For \\(n=0\\), we have \\(0+m=m\\) since the definition of addition, and have \\(m+0=m\\) since the Lemma 2.2.2. Thus, \\(0+m=m+0\\). Also, we have \\((n++)+m=(n+m)++\\) since the definition of addition, and have \\(m + (n++) = (m + n)++\\) since the Lemma 2.2.3. So if we suppose \\(n+m=m+n\\), then we have \\((n++)+m=m+(n++)\\). This closes the induction. \\(\blacksquare\\)

> Proposition 2.2.5 (Addition is associative). For any natural numbers \\(a,b,c\\), we have \\((a+b)+c=a+(b+c)\\).

Proof: For \\(a=0\\), we have \\((0+b)+c = b+c\\) and \\(0+(b+c) = b+c\\) since the definition of addition. Thus, \\((0+b)+c = 0+(b+c)\\). Also, we have

$$
((a++)+b)+c = ((a+b)++)+c = ((a+b)+c)++
$$

and

$$
(a++)+(b+c) = (a+(b+c))++
$$

since the definition of addition.

So if we suppose \\((a+b)+c = a+(b+c)\\), then we have

$$
((a++)+b)+c = (a++)+(b+c)
$$

This closes the induction. \\(\blacksquare\\)

> Proposition 2.2.6 (Cancellation law). Let \\(a,b,c\\) be natural numbers such that \\(a+b=a+c\\). Then we have \\(b=c\\).

Proof: For \\(a=0\\), we have \\(0+b = b\\) and \\(0+c = c\\) since the definition of addition. Thus, if \\(0+b = 0+c\\), we have \\(b = c\\). Also, we have \\((a++)+b = (a+b)++\\) and \\((a++)+c = (a+c)++\\) since the definition of addition. So

$$
(a++)+b = (a++)+c
$$

implies

$$
(a+b)++ = (a+c)++.
$$

By the Axiom 2.4, we know that it implies \\(a+b = a+c\\). So if we suppose \\(a+b = a+c\\) implies \\(b=c\\), then we know that \\((a++)+b = (a++)+c\\) implies \\(b=c\\) too. This closes the induction. \\(\blacksquare\\)

> Definition 2.2.7 (Positive natural numbers). A natural number \\(n\\) is said to be positive iff it is not equal to 0.

> Proposition 2.2.8. If \\(a\\) is positive and \\(b\\) is a natural number, then \\(a+b\\) is positive (and hence \\(b + a\\) is also, by Proposition 2.2.4).

Proof: For \\(b=0\\), we have \\(a+0=a\\) since the Lemma 2.2.2. Thus, \\(a+0\\) is positive. Also, we have \\(a+(b++) = (a+b)++\\) since the Lemma 2.2.3. By the Axiom 2.3, we know that \\((a+b)++ \neq 0\\), so \\(a+(b++)\\) is positive. (Notice that we get this result even if we haven't supposed \\(a+b\\) is positive.) This closes the induction. \\(\blacksquare\\)

> Corollary 2.2.9. If \\(a\\) and \\(b\\) are natural numbers such that \\(a + b = 0\\), then \\(a=0\\) and \\(b=0\\).

> Lemma 2.2.10. Let \\(a\\) be a positive number. Then there exists exactly one natural number \\(b\\) such that \\(b++ = a\\).

Proof: We first prove that the \\(b\\) is unique if it exists; suppose there is a \\(b'\\) such that \\(b'++ = a\\), then \\(b=b'\\) since the Axiom 2.4.

Now we prove the existence of \\(b\\). Let \\(P(a)\\) be "\\(a = 0\\) or there exists one natural number \\(b\\) such that \\(b++ = a\\)." Then \\(P(0)\\) is true. Now suppose \\(P(a)\\) is true. If \\(a=0\\), then \\(a++ = 0++\\), so \\(P(a++)\\) is true. If \\(a \neq 0\\), then we have \\(b++ = a\\), so \\((b++)++ = a++\\). \\(b++\\) is a natural number since the Axiom 2.2, thus, \\(P(a++)\\) is true. This closes the induction. \\(\blacksquare\\)

> Definition 2.2.11 (Ordering of the natural numbers). Let \\(n\\) and \\(m\\) be natural numbers. We say that \\(n\\) is greater than or equal to \\(m\\), and write \\(n \geq m\\) or \\(m \leq n\\), iff we have \\(n = m + a\\) for some natural number \\(a\\). We say that \\(n\\) is strictly greater than \\(m\\), and write \\(n > m\\) or \\(m < n\\), iff \\(n \geq m\\) and \\(n \neq m\\).

> Proposition 2.2.12 (Basic properties of order for natural numbers). Let \\(a, b, c\\) be natural numbers. Then
>
> - (a) (Order is reflexive) \\(a \geq a\\).
> - (b) (Order is transitive) If \\(a \geq b\\) and \\(b \geq c\\), then \\(a \geq c\\).
> - (c) (Order is anti-symmetric) If \\(a \geq b\\) and \\(b \geq a\\), then \\(a = b\\).
> - (d) (Addition preserves order) \\(a \geq b\\) if and only if \\(a+c \geq b+c\\).
> - (e) \\(a < b\\) if and only if \\(a++ \leq b\\).
> - (f) \\(a < b\\) if and only if \\(b=a+d\\) for some positive number \\(d\\).

Proof:

- (a) \\(a = a+0\\).
- (b) If \\(a \geq b\\) and \\(b \geq c\\), then there exist natural numbers \\(d,e\\) such that \\(a = b+d\\) and \\(b = c+e\\). Thus, \\(a = c+(e+d)\\).
- (c) If \\(a \geq b\\) and \\(b \geq a\\), then there exist natural numbers \\(d,e\\) such that \\(a = b+d\\) and \\(b = a+e\\). Thus, \\(a = a+(e+d)\\). By applying the cancellation law, we have \\(e+d=0\\). By applying Corollary 2.2.9, we have \\(e=0\\) and \\(d=0\\). Thus, \\(a=b\\).
- (d) Suppose \\(a \geq b\\), then there exists a natural number \\(d\\) such that \\(a = b + d\\). Thus, \\(a+c = b+c+d\\). So \\(a+c \geq b+c\\). In reverse, suppose \\(a+c \geq b+c\\), then there exists a natural number \\(d\\) such that \\(a+c = b+c+d\\). By applying the cancellation law, we have \\(a = b + d\\). Thus, \\(a \geq b\\).
- (f) Suppose \\(a < b\\), then \\(b=a+d\\) for some natural number \\(d\\) and \\(a \neq b\\). If \\(d=0\\), then \\(b=a\\), and this is contrary to the condition. Thus, \\(d\neq 0\\), i.e. \\(d\\) is positive. Reversely, suppose \\(b=a+d\\) for some positive number \\(d\\), then we have \\(a \leq b\\). If \\(a=b\\), then \\(d=0\\) since the cancellation law, and this is contrary to the condition. Thus, \\(a \neq b\\). So \\(a < b\\).
- (e) Since (f), proving (e) is equal to proving \\(a++ \leq b\\) iff \\(b=a+d\\) for some positive number \\(d\\). Suppose \\(a++ \leq b\\), then there exists a natural number \\(e\\) such that \\(b = (a++) + e\\). By the definition of addition and Lemma 2.2.3, we know that \\(b = a+(e++)\\). Let \\(d=e++\\), then we know that \\(d \neq 0\\) since Axiom 2.3. Reversely, we suppose \\(b=a+d\\) for some positive number \\(d\\). By Lemma 2.2.10, we know that there exists a natural number \\(e\\) such that \\(d = e++\\). By the definition of addition and Lemma 2.2.3, we have \\(b=a+(e++)=(a++)+e\\). Thus, \\(a++ \leq b\\).

> Proposition 2.2.13 (Trichotomy of order for natural numbers). Let \\(a\\) and \\(b\\) be natural numbers. Then exactly one of the following statements is true: \\(a < b\\), \\(a=b\\), or \\(a > b\\).

Proof: We first prove that no more than one of these statements is true. \\(a < b\\) and \\(a=b\\) cannot be true at the same time by the definition, and similarly, \\(a > b\\) and \\(a=b\\) cannot be true at the same time by the definition. If \\(a < b\\) and \\(a > b\\), then \\(a = b\\) by Proposition 2.2.12 (c), but this result is contrary to the definition. So no more than one of these statements is true.

Next, we prove that at least one of these statements is true. We induct on \\(a\\). For \\(a = 0\\), we have \\(0 \leq b\\) for any natural number \\(b\\) since \\(b = 0 + b\\). So either \\(b = 0\\) or \\(b > 0\\). Now suppose this proposition is true for \\(a\\). If \\(a > b\\), then \\(a++ > b\\) since \\(a++ > a\\) and Proposition 2.2.12 (b). If \\(a = b\\), then \\(a++ > b\\). If \\(a < b\\), then \\(a++ \leq b\\) since Proposition 2.2.12 (e), so either \\(a++ = b\\) or \\(a++ < b\\). This closes the induction. \\(\blacksquare\\)

> Proposition 2.2.14 (Strong principle of induction). Let \\(m_0\\) be a natural number, and let \\(P(m)\\) be a property pertaining to an arbitrary natural number \\(m\\). Suppose that for each \\(m \geq m_0\\), we have the following implication: if \\(P(m')\\) is true for all natural numbers \\(m_0 \leq m' < m\\), then \\(P(m)\\) is also true. (In particular, this means that \\(P(m_0)\\) is true, since in this case the hypothesis is vacuous.) Then we can conclude that \\(P(m)\\) is true for all natural numbers \\(m \geq m_0\\).

Proof: Let \\(Q(n)\\) be "\\(n \leq m_0\\) or \\(P(m)\\) is true for all natural numbers \\(m_0 \leq m < n\\)." \\(Q(0)\\) is true since \\(0 \leq m_0\\) for any natural number \\(m_0\\). Now suppose \\(Q(n)\\) is true, then we consider \\(Q(n++)\\). According to Proposition 2.2.13, we can consider three conditions: \\(n < m_0\\), \\(n = m_0\\), and \\(n > m_0\\). If \\(n < m_0\\), then \\(n++ \leq m_0\\) since Proposition 2.2.12 (e), so \\(Q(n++)\\) is true. If \\(n = m_0\\), then \\(P(m)\\) is true for all natural numbers \\(m_0 \leq m < m_0 ++\\) since \\(P(m_0)\\) is true, so \\(Q(n++)\\) is true. If \\(n > m_0\\), then according to the implication in this proposition, we know \\(P(m)\\) is true for all natural numbers \\(m_0 \leq m < n++\\), so \\(Q(n++)\\) is true. Thus \\(Q(n)\\) is true for every natural number \\(n\\). \\(\blacksquare\\)

> Exercise 2.2.6. Let \\(n\\) be a natural number, and let \\(P(m)\\) be a property pertaining to the natural numbers such that whenever \\(P(m++)\\) is true, then \\(P(m)\\) is true. Suppose that \\(P(n)\\) is also true. Prove that \\(P(m)\\) is true for all natural numbers \\(m \leq n\\); this is known as the principle of backwards induction. (Hint: apply induction to the variable \\(n\\).)

Proof: When \\(n = 0\\), then only \\(m=0\\) satisfies \\(m \leq n\\), and \\(P(0)\\) is true by assumption. Now suppose \\(P(m)\\) is true for all natural numbers \\(m \leq n\\) and \\(P(n++)\\) is true. Then \\(P(n)\\) is true by the implication in this exercise, so \\(P(m)\\) is true for all natural numbers \\(m \leq n++\\). This closes the induction. \\(\blacksquare\\)

### 2.3 Multiplication
