---
layout: post
title: "Cartan Dieudonne"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Ref**: Marc van Leeuwen’s answer here: [Link](https://math.stackexchange.com/a/4083452/303300). 

Let ${ E }$ be an ${ n }$ dimensional Euclidean space. 

What are the origin and distance preserving maps ${ f : E \longrightarrow E }$? 

**Obs**: Let ${ E }$ be an ${ n }$ dimensional Euclidean space. Let ${ f : E \longrightarrow E . }$ Then the following are equivalent: 

* ${ \lVert f(x) - f(y) \rVert = \lVert x - y \rVert }$ for all ${ x, y \in E , }$ and ${ f(0) = 0 . }$ 

* ${ f(x) \cdot f(y) = x \cdot y }$ for all ${ x, y \in E . }$ 

Further any such map is linear and bijective.    
**Pf**: Similar to the proof here: [Link](https://math.stackexchange.com/a/3972686/303300). 

The origin and distance preserving maps ${ f : E \longrightarrow E }$ are called the orthogonal transformations of ${ E . }$    
Note that they form a group under composition, called the orthogonal group ${ O(E) . }$ 

Note that reflections are simple orthogonal transformations. 

**Def** [Reflections]    
Let ${ E }$ be an ${ n }$ dimensional Euclidean space. Let ${ F \subseteq E }$ be a hyperplane (that is, an ${ n - 1 }$ dimensional subspace). Note that 

$${ E = F \oplus F ^{\perp} . }$$ 

The map sending 

$${ x = p _F (x) + p _{F ^{\perp}} (x) \longmapsto p _F (x) - p _{F ^{\perp}} (x)  }$$ 

that is 

$${ x \longmapsto p _F (x) - (x - p _F (x))  }$$ 

that is 

$${ x \longmapsto  2 p _F (x) - x }$$ 

is called a reflection about ${ F . }$ 

**Obs**: Let ${ E }$ be an ${ n }$ dimensional Euclidean space. Consider a hyperplane ${ F \subseteq E, }$ and the reflection about ${ F }$ 

$${ r(x) = 2 p _F (x) - x . }$$ 

Then ${ r(x) }$ is an orthogonal transformation.    
**Pf**: Note that 

$${ {\begin{aligned} &\, r(x) \cdot r(y) \\ = &\, (p _F (x) - p _{F ^{\perp}} (x)) \cdot (p _F (y) - p _{F ^{\perp}} (y)) \\ = &\, p _F (x) \cdot p _F (y) + p _{F ^{\perp}} (x) \cdot p _{F ^{\perp}} (y) \\ = &\, (p _F (x) + p _{F ^{\perp}} (x)) \cdot (p _F (y) + p _{F ^{\perp}} (y)) \\ = &\, x \cdot y \end{aligned}}  }$$ 

for all ${ x, y \in E . }$    
Hence ${ r(x) }$ is an orthogonal transformation, as needed. ${ \blacksquare }$ 

Let ${ E }$ be an ${ n }$ dimensional Euclidean space. Let ${ f \in O(E) . }$ 

Note that reflections are simple orthogonal transformations. 

Can we express ${ f }$ as a composition of reflections? 

**Thm** [Cartan-Dieudonne]    

Let ${ E }$ be an ${ n }$ dimensional Euclidean space. Let ${ f \in O(E) .   }$    

Consider the space of fixed points of ${ f , }$ that is ${ \ker (f - \text{id}).  }$ Consider its dimension ${ d _f = \dim (\ker (f - \text{id}) ) . }$ 

Then ${ f }$ can be expressed as a composition of ${ n - d _f }$ reflections. 

**Pf**: We will proceed by induction on ${ n - d _f . }$ 

The base case is clear. Suppose ${ n - d _f = 0. }$ Hence ${ \ker(f - \text{id}) = E }$ that is ${ f = \text{id} . }$ Hence ${ f }$ is a composition of ${ 0 }$ reflections. 

Hence let ${ n - d _f > 0 . }$ 

Hence ${ \ker(f - \text{id}) \neq E  . }$ Hence there is a vector ${ v }$ such that ${ f(v) \neq v . }$ 

Consider the reflection sending ${ f(v) }$ to ${ v . }$ Consider the hyperplane ${ H := \text{span}(v - f(v)) ^{\perp} , }$ and the reflection about this hyperplane ${ r _H . }$ 

Note that ${ r _H \circ f }$ fixes ${ v . }$ We will study the spaces of fixed points of ${ f }$ and ${ f ^{’} := r _H \circ f . }$ 

Note that ${ \ker (f - \text{id}) \subseteq H . }$ 

> Suppose ${ f(x) = x . }$ Note that ${ x \cdot (v - f(v)) }$ ${ = x \cdot v - f(x) \cdot f(v) }$ ${ = 0 . }$ Hence ${ x \in H . }$ 

Note that 

$${ {\begin{aligned} &\, \ker(f ^{’} - \text{id}) \\ = &\, \lbrace x \in E : (r _H \circ f) (x) = x \rbrace \\ = &\, \lbrace x \in E : f(x) = r _H (x) \rbrace \\ \supseteq &\, \lbrace x \in E : f(x) = x = r _H (x) \rbrace \\ = &\, \ker(f - \text{id}) \cap H .  \end{aligned}}  }$$ 

Hence 

$${ \ker(f ^{’} - \text{id}) \supseteq \ker(f - \text{id}) \cap H .  }$$ 

Note that even ${ f = r _H \circ f ^{’} . }$ Hence 

$${ \ker(f  - \text{id}) \supseteq \ker(f ^{’}  - \text{id}) \cap H . }$$ 

Hence we have the observations 

* ${ \ker (f - \text{id}) \subseteq H . }$ 

* ${ \ker(f ^{’} - \text{id}) \supseteq \ker(f - \text{id}) \cap H = \ker(f - \text{id}) .}$ 

* ${ \ker(f  - \text{id}) \supseteq \ker(f ^{’}  - \text{id}) \cap H . }$ 

Note that the second observation can be strengthened to 

$${ \ker(f ^{’} - \text{id}) \supseteq  \ker(f - \text{id}) + \text{span}(v) }$$ 

where ${ v \not \in \ker(f - \text{id}) . }$ 

Note that taking dimension of the third observation 

${ {\begin{aligned}  &\, d _f \\ \geq &\, \dim(\ker(f ^{’}  - \text{id}) \cap H) \\ = &\, d _{f ^{’}} + (n-1) - \dim(\ker(f ^{’}  - \text{id}) +  H) \\ = &\, d _{f ^{’}} + (n-1) - n \\ = &\, d _{f ^{’}} - 1  \end{aligned}}  }$ 

that is 

$${ d _{f} \geq d _{f ^{’}} - 1  .}$$ 

Note that taking dimension of the second observation 

$${ d _{f ^{’}}  > d _f. }$$ 

Hence 

* ${  d _f + 1 \geq d _{f ^{’}} . }$ 

* ${ d _{f ^{’}} \geq d _f + 1 . }$ 

Hence 

$${ d _{f ^{’}} = d _f + 1 .  }$$ 

Hence by induction hypothesis on ${ f ^{’} , }$ ${ f ^{’} = r _H \circ f }$ can be expressed as a composition of ${ n - (d _f + 1) }$ many reflections. 

Hence ${ f = r _H \circ f ^{’} }$ can be expressed as a composition of ${ n - d _f  }$ many reflections, as needed. ${ \blacksquare }$

Note that the number of reflections ${ d _f }$ is optimal. 

**Obs**: Let ${ E }$ be an ${ n }$ dimensional Euclidean space. Let ${ f \in O(E) .   }$ 

Then ${ f }$ cannot be expressed as a composition of fewer than ${ n - d _f }$ reflections. 

**Pf**: Suppose ${ f }$ can be expressed as a composition of ${ \ell }$ many reflections 

$${ f = r _{\ell} \circ \ldots \circ r _1 .  }$$ 

Note that the space of fixed points 

$${ \ker( f - \text{id}) \supseteq \bigcap _{i=1} ^{\ell} \ker(r _i - \text{id} ) .   }$$ 

Note that each ${ \ker(r _i - \text{id}) }$ is a hyperplane, and hence is the kernel of a functional ${ f _i : E \longrightarrow \mathbb{R} . }$ 

Note that 

$${ \dim \left( \bigcap _{i=1} ^{\ell} \ker(r _i - \text{id} ) \right) =  \dim \left( \bigcap _{i=1} ^{\ell} \ker (f _i) \right) \geq n - \ell .  }$$ 

> Consider the linear map ${ F :  E \longrightarrow \mathbb{R} ^{\ell}, }$ ${ x \longmapsto (f _1 (x), \ldots, f _{\ell} (x)) . }$ 
> 
> Note that ${ \ker (F) = \cap _{i=1} ^{\ell}  \ker (f _i) . }$ 
> 
> Note that by rank-nullity 
> 
> $${ \dim(\ker(F)) = n - \dim(\text{im}(F)) \geq n - \ell   }$$ 
> 
> as needed. 

Hence taking dimension 

$${ d _f \geq  n - \ell . }$$ 

Hence 

$${ \ell \geq n - d _f . }$$ 

Hence ${ n - d _f }$ is the optimal number of reflections, as needed. ${ \blacksquare }$ 

