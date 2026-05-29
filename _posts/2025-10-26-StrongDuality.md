---
layout: post
title: "Strong Duality"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Updated**: 29/5/26

**Ref**: "Foundations of Applied Mathematics, Vol 2" by Humpherys, Jarvis, Evans.

Consider the optimization problem 

$${ {\begin{aligned} \text{minimize} \quad &\, f(x) \\ \text{subject to} \quad &\, g _1 (x) \leq 0, \\ &\, \quad  \vdots \\ &\, g _m (x) \leq 0 \end{aligned}}  }$$ 

where ${ f ,}$ ${ g _i }$s are convex functions on ${ \mathbb{R} ^n . }$ (${ f }$ is allowed to take values in ${ \mathbb{R} \cup \lbrace +\infty \rbrace  }$). 

Suppose 

$${ g _{k + 1}, \ldots, g _m \, \text{ are affine}  }$$

with the affine inequalities appearing in pairs ${ \lbrace h _i \leq 0, - h _i \leq 0 \rbrace . }$ 


Consider the feasible set 

$${ \mathcal{F} = \lbrace x \in \mathbb{R} ^n : x \in \text{dom}(f), G(x) \preceq 0 \rbrace  . }$$ 

Note that ${ \mathcal{F} }$ is a convex set in ${ \mathbb{R} ^n . }$ 


Let ${ x ^{\ast} \in \mathcal{F} }$ be a minimizer with ${ f (x ^{\ast}) = p ^{\ast} . }$ 


The goal is to study ${ p ^{\ast} . }$ 

Consider the Lagrangian dual 

$${ \boxed{ \hat{f}(\mu) = \inf _{x \in \mathbb{R} ^n} (f(x) + \mu ^T G(x)) \in \mathbb{R} \cup \lbrace - \infty \rbrace } . }$$ 

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

$${ {\begin{aligned} &\, x ^{'} \in \text{int}(\text{dom}(f)), \quad x ^{'} \in \mathcal{F}, \\ &\, g _j (x ^{'}) < 0 \, \, \text{ for } j = 1, \ldots, k. \end{aligned}}  }$$ 

Then the supremum ${ d ^{\ast} }$ is attained and is equal to ${ p ^{\ast} . }$ 

**Thm**: Consider the optimization problem 

$${ {\begin{aligned} \text{minimize} \quad &\, f(x) \\ \text{subject to} \quad &\, g _1 (x) \leq 0, \\ &\, \quad  \vdots \\ &\, g _m (x) \leq 0 \end{aligned}}  }$$ 

where ${ f ,}$ ${ g _i }$s are convex on ${ \mathbb{R} ^n . }$ 

Suppose 

$${ g _{k + 1}, \ldots, g _m \, \text{ are affine}  }$$

with the affine inequalities appearing in pairs ${ \lbrace h _i \leq 0, - h _i \leq 0 \rbrace . }$ 

Let ${ x ^{\ast} \in \mathcal{F} }$ be a minimizer with ${ f (x ^{\ast}) = p ^{\ast} . }$

Consider the Lagrangian dual 

$${ \hat{f}(\mu) = \inf _{x \in \mathbb{R} ^n} (f(x) + \mu ^T G(x)) \in \mathbb{R} \cup \lbrace - \infty \rbrace . }$$

Suppose there is a point 

$${ {\begin{aligned} &\, x ^{'} \in \text{int}(\text{dom}(f)), \quad x ^{'} \in \mathcal{F}, \\ &\, g _j (x ^{'}) < 0 \, \, \text{ for } j = 1, \ldots, k.  \end{aligned}}  }$$ 

Then 

$${ \boxed{ d ^{\ast} := \sup _{\mu \succeq 0} \hat{f}(\mu) = p ^{\ast} } .   }$$ 

**Pf**: Note that 

$${ g _1 (x ^{'}), \ldots, g _k (x ^{'}) < 0  }$$ 

and 

$${ g _{k + 1} (x ^{'}) = \ldots = g _m (x ^{'}) = 0 . }$$ 

Consider

$${ \tilde{G} = (g _1, \ldots, g _k) .  }$$

Consider 

$${ V = \lbrace (u, w) \in \mathbb{R} ^k \times \mathbb{R} : \exists x \quad \tilde{G}(x) \preceq u, f(x) \leq w \rbrace .  }$$ 

Note that 

$${ \boxed{ V = \lbrace (u, w) \in \mathbb{R} ^k \times \mathbb{R} : \exists x \quad (\tilde{G}(x), f(x)) \preceq (u,w) \rbrace } .    }$$ 

Note that ${ V }$ is a convex set. 

Note that if ${ (u, w) \in V }$ and ${ (u ^{'}, w ^{'}) \succeq (u, w) ,  }$ then ${ (u ^{'}, w ^{'}) \in V . }$ 

Note that for ${ (\lambda , 0) \in \mathbb{R} ^k \times \mathbb{R} ^{m - k},  }$ the dual function 

$${ {\begin{aligned} &\, g(\lambda, 0) \\ = &\, \inf _{x \in \mathbb{R} ^n} (f(x) + \lambda ^T \tilde{G}(x)) \\ = &\, \inf _{(u, w) \in V} \lambda ^T u + w \\ = &\, \inf _{(u , w) \in V} (\lambda, 1) ^T (u , w) .   \end{aligned}} }$$ 

Hence 

$${ \boxed{ g(\lambda , 0) = \inf _{(u, w) \in V} (\lambda , 1) ^T (u, w) } .  }$$ 

Note that it suffices to show 

$${ \boxed{ \text{To show:} \quad (\mu, 0) \succeq 0 \, \, \text{ such that } \, \, g(\mu, 0) \geq p ^{\ast} } .  }$$ 


Note that ${ (0, p ^{\ast}) }$ is in the boundary of ${ V . }$ 

Hence it suffices to show 

$${ \text{To show:} \quad (\mu, 0) \succeq 0 \, \, \text{ such that } \, \, \inf _{(u, w) \in V} (\mu, 1) ^T (u, w) \geq (\mu, 1) ^T(0,  p ^{\ast} ) . }$$ 

Note that ${ (0, p ^{\ast}) }$ is in the boundary of ${ V . }$  

Hence there exists a supporting hyperplane 

$${ h((u, w)) = \mu ^T u + \mu _0 w + b  }$$ 

of ${ \text{cl}(V) }$ at ${ (0, p ^{\ast}). }$ 

Note that WLOG the normal ${ (\mu, \mu _0) }$ is pointing inwards to ${ \text{cl}(V) . }$  

Hence 

$${ \mu ^T u + \mu _0 w + b \geq \mu ^T 0 + \mu _0 p ^{\ast} + b  }$$ 

for all ${ (u, w) \in \text{cl}(V) . }$

Hence 

$${ \mu ^T u + \mu _0 w \geq \mu _0 p ^{\ast}  }$$ 

for all  ${ (u, w) \in \text{cl}(V) . }$

Suppose 

$${ \text{Suppose:} \quad (\mu, \mu _0) \succeq 0, \quad \mu _0 > 0 .  }$$ 

Then 

$${ \left( \frac{\mu}{\mu _0} \right) ^T u + w \geq p ^{\ast}   }$$

for all ${ (u, w) \in \text{cl}(V) . }$ 


Hence  

$${  \left(\frac{\mu}{\mu _0}, 0 \right) \succeq 0, \quad g \left(  \frac{\mu}{\mu _0} , 0\right) \geq p ^{\ast}   }$$ 

as needed. 

Hence it suffices to show

$${ \text{To show:} \quad (\mu, \mu _0) \succeq 0, \quad \mu _0 > 0 .   }$$ 

Note that 

$${ \mu ^T u + \mu _0 w \geq \mu _0 p ^{\ast} }$$ 

for all ${ (u, w) \in \text{cl}(V) . }$ 

Note that if some component ${ \mu _i }$ of ${ \mu }$ were negative, we could increase ${ u _i }$ arbitrarily such that the above inequality is violated. 

Hence 

$${ \mu \succeq 0 . }$$ 

SImilarly 

$${ \mu _0 \geq 0 .  }$$ 

Hence 

$${ (\mu, \mu _0) \succeq 0 .  }$$ 

Suppose ${ \mu _0 = 0 . }$ 

Note that the supporting hyperplane inequality becomes 

$${ \mu ^T u \geq 0 }$$ 

for all ${ (u, w) \in \text{cl}(V) . }$ 

Note that setting 

$${ u = (g _1 (x ^{'}), \ldots, g _k (x ^{'}))  }$$ 

gives a contradiction. 

Hence 

$${ \mu _0 > 0  }$$ 

as needed. 

Hence 

$${ \left(\frac{\mu}{\mu _0}, 0 \right) \succeq 0, \quad g \left(  \frac{\mu}{\mu _0} , 0\right) \geq p ^{\ast}   }$$  

as needed. 

Hence 

$${ d ^{\ast} := \sup _{\mu \succeq 0} \hat{f}(\mu) = p ^{\ast} }$$ 

as needed.  ${ \blacksquare }$ 










