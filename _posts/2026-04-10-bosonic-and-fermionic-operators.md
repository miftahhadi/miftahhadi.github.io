---
title: Bosonic and Fermionic Operators
excerpt_separator: "<!--more-->"
categories:
  - Quantum Tools
tags:
  - quantum
math: true
---

In the context of many-body quantum systems, the calculation is more efficient if we use the second quantization formulation. Instead of the standard many-body wave function, we use the so-called bosonic and fermionic operators. This post does not discuss the motivation on the second quantization, though. Here, I simply note some important identities.

### Bosonic Operators
The bosonic creation and annihilation operators are usually written as $$a^{\dagger}$$ and $$a$$, respectively. They follow the following **commutation relation**,
\begin{equation}
\boxed{\left[a_i, a_j \right] = [a_i^{\dagger}, a_j^{\dagger} ] = 0, \qquad [a_i, a_j^{\dagger} ] = \delta_{ij}}
\end{equation}
where $$[A, B] = AB - BA$$.

The commmutator has the following identity:

$$
[A, B] = AB - BA = - (BA - AB) = - [B, A]
$$

### Fermionic Operators
For the fermionic case, people usually denote the creation and annihilation by $$c^{\dagger}$$ and $$ c $$. They follow the **anti-commutation relation**

$$
\boxed{\{ c_i, c_j \}  = \{ c_i^{\dagger}, c_j^{\dagger} \} = 0, \quad \{ c_i, c_j^{\dagger} \} = \delta_{ij}}
$$

where $$ \{ A, B \} = AB + BA $$. It is called an anti-commutator. Because addition is commutative, so

$$
\{ A, B \} = AB + BA = BA + AB = \{ B, A \}
$$

From this identity, we can calculate the following:

$$
\{ c_i, c_i \} = c_i c_i + c_i c_i = 2 c_i^2 = 0
\\
\Rightarrow \boxed{c_i^2 = 0}
$$

Also, 

$$
\{ c_i^{\dagger}, c_i^{\dagger} \} = c_i^{\dagger} c_i^{\dagger} + c_i^{\dagger} c_i^{\dagger} = 2 (c_i^{\dagger})^2 = 0 \\

\Rightarrow \boxed{(c_i^{\dagger})^2 = 0}
$$

This identity has an interesting physical interpretation. Basically it shows us that we can't put two fermions in the same mode $$i$$ (or the same quantum mechanical state, the term _mode_ is more general). So, it captures the Pauli exclusion principle. Nice.

### Number Operator

Let us now define the number operator $$ n = a^{\dagger} a $$ or $$ n = c^{\dagger} c $$ which counts the number of bosons or fermions. Note that for the fermion case, $$ n $$ can only be 0 or 1 whereas for the bosonic case, $$ n $$ can be any non-negative numbers.

Let's now consider the following:

$$
[ab, c] = abc - cab = abc + (acb - acb) - cab =  (abc - acb) + (acb - cab) 
$$

or

$$
[ab, c] = (abc + acb) + (-acb - cab) 
$$

so now we have this identity

$$
\boxed{[ab,c] = a[b, c] + [a, c] b = a\{b, c\} - \{a, c \}b}
$$

The, considering the bosonic commutation relation, we get the following

$$
\begin{split}
[n_j, a_j] &= [a^{\dagger}_j a_j, a_j] \\
&= a_j^{\dagger}[a_j, a_j] + [a_j^{\dagger}, a_j]a_j \\
&= -a_j
\end{split}
$$

because $$[a_j^{\dagger}, a_j] = - [a_j, a_j^{\dagger}]$$. Also,

$$
\begin{split}
[n_j, a_j^{\dagger}] &= [a^{\dagger}_j a_j, a_j^{\dagger}] \\
&= a_j^{\dagger}[a_j, a_j^{\dagger}] + a_j [a_j^{\dagger}, a_j^{\dagger}]\\
&= a_j^{\dagger}
\end{split}
$$


Okay, now let's look at the fermionic case and calculate the commutator of $$n_j$$ with fermionic operators

$$
\begin{split}
[ n_j, c_j ] &= [ c_j^{\dagger}c_j, c_j ] \\
&= c_j^{\dagger}\{ c_j, c_j \} - \{ c_j^{\dagger}, c_j \} c_j \\
&= -c_j
\end{split}
$$

and

$$
\begin{split}
[ n_j, c_j^{\dagger}] &= [ c_j^{\dagger} c_j, c_j^{\dagger} ]\\
&= c_j^{\dagger} \{ c_j, c_j^{\dagger}\} - \{ c_j^{\dagger}, c_j^{\dagger} \} c_j \\
&= c_j^{\dagger}
\end{split}
$$

We can also calculate the following

$$
n_j^2 = (c_j^{\dagger} c_j)^2 = c_j^{\dagger} (c_j c_j^{\dagger}) c_j = c_j^{\dagger} (1 - c_j^{\dagger} c_j) c_j = c_j^{\dagger} c_j = n_j
$$

In summary, we have the following identities

$$
\begin{split}
\boxed{[n_j, a_j] = -a_j, \quad [n_j, a_j^{\dagger}] = a_j^{\dagger}, \\
[ n_j, c_j ] = -c_j, \quad [ n_j, c_j^{\dagger}] = c_j^{\dagger}, \\
n_j^2 = n_j
}
\end{split}
$$