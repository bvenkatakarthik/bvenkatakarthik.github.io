---
layout: post
title: "Closed Graph Theorem"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Updated**: 25/2/26 

**Ref**:

* Functional Analysis lectures by Casey Rodriguez. Lecture on the Closed Graph Theorem. Link to the lecture: [Link](https://youtu.be/G3mAXHuoDSw?si=2msG_q3lx6jK8E1L). 

**Obs** [Product of Banach spaces] 

Let ${ B _1 , }$ ${ B _2 }$ be Banach spaces. Then ${ B _1 \times B _2 }$ under 

$${ \lVert (b _1, b _2) \rVert = \lVert b _1 \rVert + \lVert b _2 \rVert  }$$ 

is a Banach space. 

**Thm** [Closed Graph Theorem] 

Let ${ B _1 , }$ ${ B _2 }$ be Banach spaces. Let ${ T : B _1 \to B _2 }$ be a linear operator. 

Then ${ T \in \mathcal{B}(B _1, B _2) }$ if and only if the graph ${ \Gamma(T) = \lbrace (u, T(u)) : u \in B _1 \rbrace }$  is closed in ${ B _1 \times B _2 . }$ 

> Hence in terms of sequential criteria, 
> 
> ${( \forall u \in B _1 , \quad u _n \to u \implies T(u _n) \to T(u)) }$ 
> 
> is equivalent to  
> 
> ${ (\forall u \in B _1, \quad u _n \to u, T(u _n) \to v \implies v = T(u)) .  }$ 

**Pf**: ${ \underline{\implies} }$ Clear from the above sequential version.

${ \underline{\impliedby} }$ Let ${ \Gamma(T) }$ be closed in ${ B _1 \times B _2 . }$ 

Consider the commutative diagram 

<div align="center">
    <img src="https://c.l3n.co/UJssqc.jpeg" width="400" height="300"/> 
</div>

Here 

$${ {\begin{aligned} &\, \pi _1 : \Gamma(T) \longrightarrow B _1, \\ &\, \pi _1 (u,T(u)) = u \end{aligned}}  }$$ 

and 

$${ {\begin{aligned} &\, \pi _2 : \Gamma(T) \longrightarrow B _2, \\ &\, \pi _2 (u,T(u)) = T(u) \end{aligned}} }$$ 

Note that ${ \Gamma(T) }$ is a closed subspace of a Banach space, and hence is a Banach space. 

Note that ${ \pi _1, }$ ${ \pi _2 }$ are bounded linear operators. For example, ${ \lVert \pi _2 (u, Tu) \rVert }$ ${ = \lVert Tu \rVert }$ ${ \leq \lVert u \rVert + \lVert Tu \rVert }$ ${ = \lVert (u, Tu) \rVert . }$ 

Note that ${ \pi _1 }$ is a bijection. By the Open Mapping Theorem, ${ \pi _1 ^{-1} }$ ${ = s }$ is a bounded linear operator. 

Hence ${ T = \pi _2 \circ s }$ is a bounded linear operator, as needed. 



