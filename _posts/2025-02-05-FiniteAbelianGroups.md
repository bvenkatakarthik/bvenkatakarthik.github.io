---
layout: post
title: "Finite Abelian Groups"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Updated**: 22/2/25 

**Ref**: "Undergraduate Algebra" by Lang. 

The goal is to study the structure of finite abelian groups. 

Let ${ (A, +) }$ be a finite abelian group. We can ask ourselves: Can we express ${ A }$ in terms of its subgroups?  

Note that for every integer ${ n \in \mathbb{Z} _{> 0} }$ there is a group homomorphism ${ \varphi _n : A \to A , }$ ${ x \mapsto nx }$ with kernel 

$${ A _n := \ker (\varphi _n) = \lbrace x \in A : nx = 0  \rbrace .  }$$ 

We say ${ n }$ is an exponent of ${ A }$ if ${ A _n = A . }$ (By Lagrange's theorem, ${ \vert A \vert }$ is an exponent of ${ A }$). 

**Obs** [${ A = A _m \oplus A _{m ^{'}} }$]    
Let ${ (A, +) }$ be a finite abelian group with exponent ${ n . }$ Now if ${ n = m m ^{'} }$ is a factorisation with ${ (m, m ^{'}) = 1 , }$ we have 

$${ A = A _n = A _m \oplus A _{m ^{'}} . }$$ 

> Especially setting ${ n = \vert A \vert }$ and writing the prime factorisation ${ n = \prod p _i ^{r _i} , }$ we have 
> 
> $${ A = \bigoplus A _{p _i ^{r _i}} }$$ 

**Pf**: Let ${ n = m m ^{'} }$ be a factorisation with ${ (m, m ^{'}) = 1 . }$ Since ${ (m, m ^{'}) = 1 }$ there exist integers ${ r, s }$ such that ${ rm + s m ^{'} = 1 . }$    
Now for every ${ x \in A }$ we have 

$${ x = \underbrace{rmx} _{\in \, A _{m ^{'}}} + \underbrace{sm ^{'} x} _{\in \, A _m} .  }$$ 

Hence ${ A = A _m + A _{m ^{'}} . }$ This is a direct sum, because if ${ x \in A _m \cap A _{m ^{'}} }$ we have ${ x = r(mx) + s(m ^{'} x) }$ ${ = 0 . }$    
Hence 

$${ A = A _m \oplus A _{m ^{'}} }$$ 

as needed. ${ \blacksquare }$ 

We can ask ourselves: What is the structure of the factors ${ A _{p _i ^{r _i}} }$? 


Note that 

$${ {\begin{align} &\, A _{p _i ^{r _i}} \\ = &\, \lbrace x \in A : p _i ^{r _i} x = 0 \rbrace \\ = &\, \lbrace x \in A : \text{ord}(x) \text{ divides } p _i ^{r _i} \rbrace \\ = &\, \lbrace x \in A : \text{ord}(x) \text{ is a power of } p _i \rbrace \\ =: &\, A(p _i) .     \end{align}} }$$ 

**Obs**: Each factor ${ A _{p _i ^{r _i}} = A (p _i) }$ is a ${ p _i - }$group.    
**Pf**: By [Cauchy's theorem](https://en.wikipedia.org/wiki/Cauchy%27s_theorem_(group_theory)), for every prime divisor ${ p \mid \vert A(p _i) \vert  }$ there is an element of ${ A(p _i) }$ of order ${ p . }$ Hence the only prime divisor of ${ \vert A (p _i) \vert }$ is ${ p _i , }$ that is ${ \vert A(p _i) \vert }$ is a power of ${ p _i }$ as needed. ${ \blacksquare }$ 

It suffices to study the structure of finite abelian ${ p - }$groups. 

Let ${ (A, +) }$ be a finite abelian ${ p - }$group. We say ${ A }$ is of type ${ (p ^{r _1}, \ldots, p ^{r _s}) }$ if it is isomorphic to a product of cyclic subgroups of orders ${ p ^{r _i} }$ (${ i = 1, \ldots, s }$). 

**Thm** [Finite abelian ${ p - }$groups are products of cyclic ${ p - }$subgroups]    
Let ${ (A, +) }$ be a finite abelian ${ p - }$group. It is isomorphic to a product of cyclic ${ p - }$subgroups.    
If it is of type ${ (p ^{r _1}, \ldots, p ^{r _s}) }$ with ${ r _1 \geq \ldots r _s \geq 1 }$ then the sequence ${ r _1, \ldots, r _s }$ is uniquely determined.    
**Pf**: [Existence]    
Let ${ a _1 \in A }$ be an element of maximal order. WLOG ${ A }$ is not cyclic. Let ${ \text{ord}(a _1) = p ^{r _1}  . }$    
We can ask ourselves: How are the orders of elements in ${ A / \langle a _1 \rangle }$ and ${ A }$ related?    
**Lemma 1**: Let an element ${ p ^k b }$ have order ${ p ^m . }$ Then ${ b }$ has order ${ p ^{k + m} . }$    
**Pf**: Firstly ${ p ^{k + m} b = 0 . }$ Also if ${ p ^n b = 0 }$ then ${ n \geq k }$ (because otherwise ${ p ^k b }$ ${ = p ^{k - n} p ^n b = 0 }$, absurd) and further ${ n \geq k + m  }$ (because otherwise ${ p ^k b }$ has order less than ${ p ^m }$, absurd). Hence ${ b }$ has order ${ p ^{k + m} .}$ ${ {\color{blue}{\blacksquare}} }$    
**Lemma 2**: Let ${ [b] = b + \langle a _1 \rangle }$ be an element of ${ A / \langle a _1 \rangle }$ of order ${ p ^r . }$ Then there exists a representative ${ a }$ of ${ [b] }$ whose order is ${ p ^r . }$    
**Pf**: Let ${ b ^{'} }$ be any representative of ${ [b] . }$ So ${ p ^r [b ^{'}] = [0] ,}$ that is ${ p ^r b ^{'} = n a _1 }$ for some ${ n \geq 0 . }$    
If ${ n = 0 }$ we let ${ a := b ^{'} , }$ that is ${ b ^{'} }$ is an element of order ${ p ^r . }$ So let ${ n \neq 0 , }$ that is ${ n = p ^k t }$ for some  ${ k \geq 0, (p, t) = 1 . }$ WLOG ${ n < \text{ord}(a _1) }$ that is ${ k < r _1 . }$    
Note that ${ t a _1 }$ is also a generator of ${ \langle a _1 \rangle . }$ Hence ${ p ^k t a _1 }$ has order ${ p ^{r _1} / p ^k }$ ${ = p ^{r _1 - k } , }$ that is ${ p ^r b ^{'} }$ has order ${ p ^{r _1 - k} . }$ Hence by lemma 1, ${ b ^{'} }$ has order ${ p ^{r _1 + r - k} . }$ Since ${ a _1 }$ is a maximal order element we have ${ p ^{r _1 + r - k } \leq p ^{r _1} }$ that is ${ r \leq k . }$    
Hence ${ p ^r b ^{'} }$ ${ = p ^k t a _1 }$ ${ = p ^r p ^{k -r} t a _1 }$ that is ${ p ^r (b ^{'} - p ^{k - r} t a _1) = 0 . }$ Letting ${ a := b ^{'} - p ^{k - r} t a _1 }$ we see it is an element of order ${ p ^r . }$ (For example ${ (p ^r - 1 ) (b ^{'} - p ^{k - r} t a _1)  }$ is of the form an element not in ${ [0] }$ plus an element in ${ [0] , }$ and so is not in ${ [0] }$).    
Hence we are always able to pick a representative ${ a }$ of ${ [b] }$ of same order ${ p ^r . }$ ${ {\color{blue}{\blacksquare}} }$   
Now that we have proved the "lifting lemma" lemma 2, we can get back to the original proof. By induction hypothesis, we have 

$${ A / \langle a _1 \rangle = \langle [ \overline{a _2} ] \rangle \oplus \ldots \oplus \langle [\overline{a _s}] \rangle   }$$ 

where ${ \langle [\overline{a _2}] \rangle , \ldots , \langle [\overline{a _s}] \rangle }$ are cyclic subgroups of orders ${ p ^{r _2}, \ldots, p ^{r _s} }$ respectively such that ${ r _2 \geq \ldots \geq r _s . }$ By the lifting lemma we can pick representatives ${ a _2 \in [ \overline{a _2}], \ldots, a _s \in [\overline{a _s}] }$ with orders ${ p ^{r _2}, \ldots, p ^{r _s} }$ respectively. Rewriting the induction hypothesis we have 

$${ A / \langle a _1 \rangle = \langle [a _2] \rangle \oplus \ldots \oplus \langle [a _s] \rangle .   }$$ 

Now the claim is 

$${\text{To show: } \quad A = \langle a _1 \rangle \oplus \ldots \oplus \langle a _s \rangle .  }$$

Firstly, since ${ [a _j] }$ and ${ a _j }$ have the same orders the canonical homomorphism ${ x \mapsto [x] }$ induces an isomorphism ${ \langle a _j \rangle \overset{\cong}{\longrightarrow} \langle [a _j] \rangle .  }$    
We first show ${ A = \langle a _1 \rangle + \ldots + \langle a _s \rangle . }$ Let ${ x \in A . }$ There exist ${ [x _2] \in \langle [a _2] \rangle, \ldots , [x _s] \in \langle [a _s] \rangle }$ such that 

$${ [x] = [x _2] + \ldots + [x _s] .  }$$ 

Hence there is an ${ x _1 \in \langle a _1 \rangle }$ such that 

$${ x = x _1 + x _2 + \ldots + x _s , \quad \text{each } x _j \in \langle a _j \rangle  }$$ 

as needed. We now show the sum ${ A = \langle a _1 \rangle + \ldots + \langle a _s \rangle  }$ is direct.    
Suppose ${ x \in A }$ and 

$${ x = x _1 + \ldots + x _s = y _1 + \ldots + y _s, \quad x _i, y _i \in \langle a _i \rangle  .  }$$ 

Subtracting and letting ${ z _i = x _i - y _i , }$ we have 

$${ z _1 + \ldots + z _s = 0, \quad z _i \in \langle a _i \rangle. }$$ 

Hence 

$${ [z _2] + \ldots + [z _s] = [0], \quad [z _i] \in \langle [a _i] \rangle  }$$

giving that each ${ [z _2] = \ldots [z _s] = [0] . }$ By the isomorphism ${ \langle a _j \rangle \overset{\cong}{\longrightarrow} \langle [a _j] \rangle }$ we have ${ z _2 = \ldots = z _s = 0 }$ as needed.    
[Uniqueness]    
We prove uniqueness, by induction on the order of ${ A . }$ Suppose that ${ A }$ is written in two ways as a product of cyclic ${ p - }$subgroups, say of type 

$${ ( p ^{r _1}, \ldots, p ^{r _s}) \quad \text{ and } \quad (p ^{m _1}, \ldots, p ^{m _k})   }$$

with ${ r _1 \geq \ldots \geq r _s \geq 1 }$ and ${ m _1 \geq \ldots \geq m _k \geq 1 . }$ Now ${ pA }$ is also a finite abelian ${ p - }$group, of order strictly less than order of ${ A , }$ and of type 

$${ (p ^{r _1 - 1}, \ldots, p ^{r _s - 1}) \quad \text{ and } \quad (p ^{m _1 - 1}, \ldots, p ^{m _k - 1}) . }$$ 

Here it is understood that if any exponent ${ r _i - 1}$ or ${ m _j - 1 }$ is ${ 0 ,}$ the corresponding factor is the trivial group.    
Consider the subsequences ${ I = \lbrace i : r _i \geq 2 \rbrace }$ and ${ J = \lbrace j : m _j \geq 2 \rbrace . }$ By induction hypothesis the type of ${ p A }$ is unique, that is the subsequences 

$${ (p ^{r _i - 1}) _{i \in I} = (p ^{m _j - 1}) _{j \in J}  . }$$ 

Hence ${ A }$ is of type 

$${ ((p ^{r _i}) _{i \in I}, \underbrace{p , \ldots, p} _{\nu \text{ times}} ) \quad \text{ and } \quad ((p ^{m _j}) _{j \in J}, \underbrace{p, \ldots, p} _{\mu \text{ times}}) .  }$$ 

Now the order of ${ A }$ is 

$${ p ^{\sum _{i \in I} r _i} p ^{\nu} =  p ^{\sum _{j \in J} m _j} p ^{\mu}    }$$ 

hence ${ \nu = \mu }$, as needed. ${ \blacksquare  }$
