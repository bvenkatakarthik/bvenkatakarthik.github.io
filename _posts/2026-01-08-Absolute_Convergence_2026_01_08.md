---
layout: post
title: "Absolute Convergence"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---


**Ref**: "Introduction to Hilbert Spaces" by Debnath, Mikusinski. 

Note that in ${ \mathbb{R} , }$ convergence of ${ \sum _{j = 1} ^{\infty} \vert x _j \vert }$ implies convergence of ${ \sum _{j = 1} ^{\infty} x _j . }$ 

**Q**) What are the normed spaces in which convergence of ${ \sum _{j = 1} ^{\infty} \lVert x _j \rVert }$ implies convergence of ${ \sum _{j = 1} ^{\infty} x _j }$? 

**Thm**: Let ${ E }$ be a normed space.    
Then ${ E }$ is complete if and only if absolute convergence implies convergence. 

**Pf**: ${ \underline{\implies} }$ Let ${ E }$ be a complete normed space. Let ${ \sum _{j = 1} ^{\infty} \lVert x _j \rVert }$ be a convergent series.

We are to show ${ \sum _{j = 1} ^{\infty} x _j }$ is a convergent series.

It suffices to show ${ \sum _{j = 1} ^{\infty} x _j }$ is a Cauchy sequence. 

Let ${ \varepsilon > 0 . }$ Note that ${ \sum _{j = 1} ^{\infty} \lVert x _j \rVert }$ is a Cauchy sequence. Hence there is an ${ N }$ such that 

$${ \sum _{j = 1} ^{m} \lVert x _j \rVert - \sum _{j = 1} ^{n} \lVert x _j \rVert < \varepsilon \quad \text{ for all } \quad m > n \geq N .  }$$ 

Note that 

$${ \left \lVert \sum _{j = 1} ^{m} x _j -  \sum _{j = 1} ^{n} x _j \right \rVert \leq \sum _{j = 1} ^{m} \lVert x _j \rVert - \sum _{j = 1} ^{n} \lVert x _j \rVert < \varepsilon  }$$ 

for all ${ m > n \geq N . }$ 

Hence ${ \sum _{j = 1} ^{\infty} x _j }$ is a Cauchy sequence, as needed. 

${ \underline{\impliedby} }$ Let ${ E }$ be a normed space. Suppose absolute convergence implies convergence. 

We are to show ${ E }$ is complete.  

Let ${ (x _n) }$ be a Cauchy sequence in ${ E . }$ We are to show ${ (x _n) }$ is convergent. 

It suffices to show ${ (x _n) }$ has a convergent subsequence ${ (x _{p _n}) . }$

Note that for every ${ k \in \mathbb{Z} _{> 0} }$ there is an ${ p _k }$ such that 

$${ \lVert x _m - x _n \rVert < 2 ^{-k} \quad \text{ for all } \quad m, n \geq p _k .  }$$ 

WLOG the ${ (p _k) }$s are strictly increasing. 

Note that by comparision with ${ \sum _{k =1} ^{\infty} 2 ^{-k},  }$

$${ \sum _{k =1} ^{\infty} ( x _{p _{k +1}} - x _{p _k} )  }$$ 

is absolutely convergent. 

Hence ${ (x _{p _k}) }$s converge to a point ${ x \in E , }$ as needed. 

Hence 

$${ \lVert x _n - x \rVert \leq \lVert x _n - x _{p _n} \rVert + \lVert x _{p _n} - x \rVert \to 0 }$$ 

because ${ (x _n) }$ is Cauchy. as needed