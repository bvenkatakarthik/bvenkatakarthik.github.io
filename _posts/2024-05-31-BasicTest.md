---
layout: post
title: "Render test"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

.$${ \underline{\textbf{Taylor’s Theorem}} }$$ 

Recall the proof of Taylor’s theorem [for real functions](https://math.stackexchange.com/a/4201118/303300) (using integration by parts). It generalises as follows. 

**Thm** [Taylor’s theorem]:    

Consider complete normed spaces ${ E, F, }$ and a ${ C ^p }$ map ${ f : U (\subseteq E \text{ open}) \to F  .}$ Fix an ${ x \in U . }$    

Let ${ y \in U }$ be such that the segment ${ [[x, x + y]] = \lbrace x + ty : t \in [0, 1] \rbrace }$ is contained in ${ U . }$ Then, denoting by ${ y ^{(k)} }$ the ${ k -}$tuple ${ (y, \ldots, y), }$ we have 

$${ \begin{align*} &f(x+y) \\ = &\, f(x) + \frac{Df(x) y ^{(1)}}{1!} + \ldots +  \frac{D ^p f(x) y ^{(p)} }{p!} + R _p (y) \end{align*} }$$ 

where 

$${ R _p (y) = \int _0 ^1  \frac{(1-t) ^{p-1}}{(p-1)!} [ D ^p f(x + ty) - D ^p f (x)] y ^{(p)} \, dt .   }$$ 

> **Lem**: If ${ F }$ is a complete normed space and ${ f : [a, b] \to F }$ is regulated, then ${ \lVert f \rVert }$ is regulated and ${ \lVert \int _a ^b f \rVert \leq \int _a ^b \lVert f \rVert .}$    
**Pf**: There are step maps ${ s _n : [a,  b] \to F }$ converging uniformly to ${ f .}$ Now ${ \sup _{t \in [a, b]} \vert \lVert s _n (t) \rVert - \lVert f (t) \rVert \vert \leq \lVert s _n - f \rVert \to 0  }$ so step maps ${ \lVert s _n \rVert  }$ converge uniformly to ${ \lVert f \rVert  . }$ Also each term ${ \lVert \int _a ^b s _n \rVert \leq \int _a ^b \lVert s _n \rVert, }$ so letting ${ n \to \infty }$ gives ${ \lVert \int _a ^b f \rVert \leq \int _a ^b \lVert f \rVert  }$ as needed. 
> 
> Therefore the remainder ${ R _p (y) }$ can be bounded as 
> 
> $${ \begin{align*} \lVert R _p (y) \rVert \leq &\, \int _0 ^1  \frac{(1-t) ^{p-1} }{(p-1)!} \lVert [D ^p f(x + ty)  - D ^p f(x)] y ^{(p)} \rVert \, dt \\ \leq &\, \sup _{0 \leq t \leq 1} \lVert D ^p f (x + ty) - D ^p (x) \rVert \lVert y \rVert ^p \int _0 ^1 \frac{(1-t) ^{p-1}}{(p-1)!} \, dt \\ = &\, \sup _{0 \leq t \leq 1} \lVert D ^p f (x + ty) - D ^p (x) \rVert \frac{\lVert y \rVert ^p}{p!} . \end{align*}  }$$ 
> 
> Especially, 
> 
> $${ \lim _{y \to 0 } \frac{\lVert R _p (y) \rVert}{\lVert y \rVert ^p} = 0   }$$ 
>
> that is ${ R _p (y) }$ is ${ o(\lVert y \rVert ^p) . }$ 

**Pf**: Consider the continuous bilinear map 

$${ \bullet :  F \times \mathbb{R} \to F, \quad v \bullet a  = a v .  }$$ 

 Using this, we can integrate by parts any product ${ \varphi _1 (t) \bullet D\varphi _2  (t) }$ where ${ \varphi _1 : [0, 1] \to F }$ and ${ \varphi _2 : [0, 1] \to \mathbb{R} }$ are ${ C ^1  }$ maps. So, mimicking the proof for real functions, 

 
$${ \begin{align*} &f(x + y) \\ &\quad \\ = &\, f(x) + \int _0 ^1 \underbrace{Df(x + ty)y} _{\begin{aligned} &\varphi _1 (t) = (Df \circ \sigma )(t)y ; \\ &\sigma(t) = x + ty \end{aligned} }  \bullet \underbrace{1} _{ \begin{aligned} &D\varphi _2 (t);  \\ &\varphi _2 (t) = t-1  \end{aligned} }  \, dt  \\ &\quad \\ = &\, f(x) +  Df(x + ty)y  \bullet (t - 1) \Bigg\vert _0 ^1  \\ &-  \int _0 ^1 D ^2 f (x + ty) y y \bullet (t - 1) \, dt \\ &\quad \\ = &\, f(x) + Df(x) y \\ &- \left( D ^2 f(x + ty) y ^{(2)} \bullet \frac{(t-1) ^2}{2} \Bigg\vert _0 ^1  - \int _0 ^1 D ^3 f(x + ty) y ^{(3)} \bullet \frac{(t-1) ^2}{2} \, dt  \right) \\ &\quad \\ = &\, f(x) + Df(x) y +  \frac{D ^2 f (x) y ^{(2)}}{2} \\ &+ \int _0 ^1 D ^3 f (x + ty) y ^{(3)} \bullet \frac{(t-1) ^2}{2} \, dt  \\ &\quad \\ = &\, f(x) + Df(x) y +  \frac{D ^2 f (x) y ^{(2)}}{2} \\ &+ \left( D ^3 f(x + ty) y ^{(3)} \bullet \frac{(t-1) ^3}{2 \cdot 3 } \Bigg\vert _0 ^1 - \int _0 ^1  D ^4 f (x + ty) y ^{(4)} \bullet \frac{(t-1) ^3}{2 \cdot 3 } \, dt  \right) \\ &\quad \\ = &\, f(x) + Df(x)y + \frac{D ^2 f (x) y ^{(2)}}{2} +  \frac{D ^3 f (x) y ^{(3)} }{2 \cdot 3} \\ &- \int _0 ^1  D ^4 f (x + ty) y ^{(4)} \bullet \frac{(t-1) ^3}{2 \cdot 3 } \, dt \\ &\quad \\ &\quad \vdots \\ &\quad \\ = &\, f(x) + Df(x) y +   \frac{D ^2 f (x) y ^{(2)}}{2} + \ldots + \frac{D ^{p-1} f (x) y ^{(p-1)}}{(p-1)!} \\ &+ (-1) ^{p-1} \int _0 ^1 D ^p f(x + ty) y ^{(p)} \bullet \frac{(t-1) ^{p-1}}{(p-1)!} \, dt \\ &\quad \\ = &\, f(x) + Df(x) y +   \frac{D ^2 f (x) y ^{(2)}}{2} + \ldots + \frac{D ^{p-1} f (x) y ^{(p-1)}}{(p-1)!} \\ &+  \int _0 ^1 \frac{(1-t) ^{p-1}}{(p-1)!} D ^p f(x + ty ) y ^{(p)} \, dt \\ &\quad \\ = &\, f(x) + Df(x) y  + \ldots + \frac{D ^{p-1} f (x) y ^{(p-1)}}{(p-1)!} + \frac{D ^p f(x) y ^{(p)}}{p!} \\ &+ \int _0 ^1  \frac{(1-t) ^{p-1}}{(p-1)!} [ D ^p f(x + ty) - D ^p (x)] y ^{(p)} \, dt   \end{align*} }$$ 

as needed. ${ \blacksquare }$ 









