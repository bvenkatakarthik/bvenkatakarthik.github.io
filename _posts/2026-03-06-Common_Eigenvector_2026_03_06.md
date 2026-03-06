---
layout: post
title: "Simultaneous Triangularization"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

[This is a repetition of the answer [here](https://math.stackexchange.com/a/593291/303300)]

**Thm** [Commuting matrices share an eigenvector]    
Let ${ A, B \in \mathbb{C} ^{n \times n} . }$ Suppose ${ AB = BA . }$    
Then ${ A, B }$ share an eigenvector.

**Pf**: Let ${ \lambda }$ be an eigenvalue of ${ A . }$ 

Consider any eigenvector 

$${ v \in \ker(A - \lambda I) .  }$$ 

Note that 

$${ AB v = B A v .  }$$ 

Hence 

$${ A (Bv) = \lambda (Bv) .  }$$ 

Hence 

$${ Bv \in \ker(A - \lambda I)  }$$ 

as well. 

Hence 

$${ \ker(A - \lambda I) \, \text{ is a (nontrivial) B-invariant subspace.} }$$ 

Hence ${ B \vert _{\ker(A - \lambda I)} }$ admits an eigenvector ${ w . }$ 

Note that ${ w }$ is a common eigenvector of ${ A, B , }$ as needed. ${ \blacksquare }$ 

We can strengthen above result. 

**Thm** [Commuting matrices are simultaneously triangularizable]    
Let ${ A, B \in \mathbb{C} ^{n \times n} . }$ Suppose ${ AB = BA . }$    
Then ${ A, B }$ are simultaneously triangularizable. 

**Pf**: We will proceed by induction on ${ n . }$ 

Note that ${ A, B }$ have a common eigenvector ${ v _1 . }$ 

Construct a basis ${ P = (v _1; v _2 , \ldots, v _n) . }$ 

Note that 

$${ {\begin{aligned} &\, AP = P {\begin{pmatrix} m _{11} &M _{12} \\ 0 &M _{22} \end{pmatrix}} \\ &\, BP = P {\begin{pmatrix} n _{11} &N _{12} \\ 0 &N _{22} \end{pmatrix}} . \end{aligned}} }$$ 

Note that since ${ A, B }$ commute, we have 

$${ {\begin{pmatrix} m _{11} &M _{12} \\ 0 &M _{22} \end{pmatrix}} {\begin{pmatrix} n _{11} &N _{12} \\ 0 &N _{22} \end{pmatrix}} = {\begin{pmatrix} n _{11} &N _{12} \\ 0 &N _{22} \end{pmatrix}}{\begin{pmatrix} m _{11} &M _{12} \\ 0 &M _{22} \end{pmatrix}} .   }$$ 

Hence 

$${ M _{22} N _{22} = N _{22} M _{22} .  }$$ 

Hence by induction hypothesis, there is an invertible matrix ${ Q }$ such that 

$${ Q ^{-1} M _{22} Q, \quad Q ^{-1} N _{22} Q  }$$ 

are upper triangular. 

Note that 

$${  \begin{pmatrix} 1 &0 \\ 0 &Q \end{pmatrix}  ^{-1} \begin{pmatrix} m _{11} &M _{12} \\ 0 &M _{22} \end{pmatrix} \begin{pmatrix} 1 &0 \\ 0 &Q \end{pmatrix}  , \quad  \begin{pmatrix} 1 &0 \\ 0 &Q \end{pmatrix}  ^{-1} \begin{pmatrix} n _{11} &N _{12} \\ 0 &N _{22} \end{pmatrix} \begin{pmatrix} 1 &0 \\ 0 &Q \end{pmatrix}  }$$ 

are now upper triangular. 

Hence 

$${ \begin{pmatrix} 1 &0 \\ 0 &Q \end{pmatrix}  ^{-1} P ^{-1} A P \begin{pmatrix} 1 &0 \\ 0 &Q \end{pmatrix} , \quad \begin{pmatrix} 1 &0 \\ 0 &Q \end{pmatrix}  ^{-1} P ^{-1} B P \begin{pmatrix} 1 &0 \\ 0 &Q \end{pmatrix}  }$$ 

are upper triangular. 

Hence 

$${ \left( P \begin{pmatrix} 1 &0 \\ 0 &Q \end{pmatrix} \right) ^{-1} A \left( P \begin{pmatrix} 1 &0 \\ 0 &Q \end{pmatrix} \right), \quad  \left( P \begin{pmatrix} 1 &0 \\ 0 &Q \end{pmatrix} \right) ^{-1} B  \left( P \begin{pmatrix} 1 &0 \\ 0 &Q \end{pmatrix} \right)  }$$ 

are upper triangular, as needed. ${ \blacksquare }$ 



