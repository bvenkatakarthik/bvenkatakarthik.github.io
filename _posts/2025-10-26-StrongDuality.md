---
layout: post
title: "Strong Duality"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Updated**: 27/10/25

**Ref**: "Foundations of Applied Mathematics, Vol 2" by Humpherys, Jarvis, Evans.

Consider the optimization problem 

$${ {\begin{aligned} \text{minimize} \quad &\, f(x) \\ \text{subject to} \quad &\, g _1 (x) \leq 0, \\ &\, \quad  \vdots \\ &\, g _m (x) \leq 0 \end{aligned}}  }$$ 

where ${ f ,}$ ${ g _i }$s are convex functions on ${ \mathbb{R} ^n . }$ (${ f }$ is allowed to take values in ${ \mathbb{R} \cup \lbrace +\infty \rbrace  }$). 

Suppose 

$${ g _1, \ldots, g _k \, \text{ are not affine}  }$$ 

and 

$${ g _{k + 1}, \ldots, g _m \, \text{ are affine}  }$$

with the affine inequalities appearing in pairs ${ \lbrace h _i \leq 0, - h _i \leq 0 \rbrace . }$ 


Consider the feasible set 

$${ \mathcal{F} = \lbrace x \in \mathbb{R} ^n : x \in \text{dom}(f), G(x) \preceq 0 \rbrace  . }$$ 

Note that ${ \mathcal{F} }$ is a convex set in ${ \mathbb{R} ^n . }$ 


Let ${ x ^{\ast} \in \mathcal{F} }$ be a minimizer with ${ f (x ^{\ast}) = p ^{\ast} . }$ 


The goal is to study ${ p ^{\ast} . }$ 

Consider the Lagrangian dual 

$${ \hat{f}(\mu) = \inf _{x \in \mathbb{R} ^n} (f(x) + \mu ^T G(x)) \in \mathbb{R} \cup \lbrace - \infty \rbrace . }$$ 

Note that ${ \hat{f} }$ is an infimum over affine functions in ${ \mu, }$ and hence is concave.

Note that if ${ \mu \succeq 0 , }$ we have 

$${ f(x ^{\ast}) + \mu ^T G(x ^{\ast}) \leq p ^{\ast} .  }$$

Hence if ${ \mu \succeq 0 , }$ we have 

$${ \hat{f}(\mu) \leq p ^{\ast} .  }$$

Hence 

$${ \boxed{ \sup _{\mu \succeq 0} \hat{f}(\mu) \leq p ^{\ast} } .  }$$

**Q**) Is the above bound an equality? 

Equivalently, 

**Q**) Is

$${ \quad d ^{\ast} := \sup _{\mu \succeq 0} \hat{f}(\mu) = p ^{\ast} .   }$$ 

It turns out imposing a mild constraint ensures that the supremum ${ d ^{\ast} }$ is attained and is equal to ${ p ^{\ast} . }$ 

Suppose there is a point 

$${ {\begin{aligned} &\, x ^{'} \in \text{int}(\text{dom}(f)), \quad x ^{'} \in \mathcal{F}, \\ &\, g _j (x ^{'}) < 0 \, \, \text{ for each } g _j \text{ which is not affine.}  \end{aligned}}  }$$ 

Then the supremum ${ d ^{\ast} }$ is attained and is equal to ${ p ^{\ast} . }$ 





