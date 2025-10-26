---
layout: post
title: "Strong Duality"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Ref**: "Foundations of Applied Mathematics, Vol 2" by Humpherys, Jarvis, Evans.

Consider the optimization problem 

$${ {\begin{aligned} \text{minimize} \quad &\, f(x) \\ \text{subject to} \quad &\, g _1 (x) \leq 0, \\ &\, \quad  \vdots \\ &\, g _m (x) \leq 0 \end{aligned}}  }$$ 

where ${ f ,}$ ${ g _i }$s are convex on ${ \mathbb{R} ^n . }$ (${ f }$ is allowed to take values in ${ \mathbb{R} \cup \lbrace +\infty \rbrace  }$). 

Consider the feasible set 

$${ \mathcal{F} = \lbrace x \in \mathbb{R} ^n : x \in \text{dom}(f), G(x) \preceq 0 \rbrace  . }$$ 

Let ${ x ^{\ast} \in \mathcal{F} }$ be a minimizer with ${ f (x ^{\ast}) = p ^{\ast} . }$ 


The goal is to study ${ p ^{\ast} . }$ 

