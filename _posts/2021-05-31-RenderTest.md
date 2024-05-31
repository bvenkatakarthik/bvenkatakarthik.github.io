---
layout: post
title: "Render Test"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

$${ \underline{\textbf{References}} }$$ 

* “Undergraduate Analysis” by Lang.
* “Foundations of Applied Mathematics, Vol 1” by Humpherys, Jarvis, Evans.  
* “Analysis Vol 2” by Amann, Escher.  
* “Calculus on Normed Vector Spaces” by Coleman. 
* “Differential Calculus” by Cartan.


**ROUGH NOTES (!)**    
Updated: 31/5/24

Sections: [Continuous linear maps](#1); [Differentiation](#2); [Differentiation of maps ${ \mathbb{R} ^n \to \mathbb{R} ^m }$](#3);  [Integration of maps ${ f : [a, b] \to E }$](#4); [Mean value theorem](#5); [Second derivative](#6); [Third derivative](#7); [Higher derivatives](#8); [Taylor’s theorem](#9)


###### 1

$${ \underline{\textbf{Continuous linear maps}} }$$ 

**Thm** [Continuity of a linear map]: Let ${ E, F }$ be normed vector spaces and ${ \lambda : E \to F }$ a linear map. Now  

$${ \begin{align*} &(\lambda \text{ is continuous}) \\ \iff &\Bigg( \sup _{\lVert u \rVert = 1} \lVert \lambda(u) \rVert = \sup _{v \neq 0} \frac{\lVert \lambda(v) \rVert}{\lVert v \rVert} < \infty \Bigg). \end{align*}  }$$    

**Pf**: ${ \underline{\Leftarrow} }$ Say ${ C = \sup _{v \neq 0} \frac{\lVert \lambda (v) \rVert}{\lVert v \rVert} < \infty .}$ Now ${ \lVert \lambda (x) - \lambda(y) \rVert }$ ${ = \lVert \lambda (x - y) \rVert }$ ${ \leq C \lVert x - y \rVert }$ for all ${ x, y \in E.}$ If ${ C = 0 }$ the map is anyways ${ \lambda = 0 ,}$ and if ${ C > 0 }$ the map is uniformly continuous.    
${ \underline{\Rightarrow} }$ Say ${ \lambda }$ is continuous. So there is a ${ \delta > 0 }$ such that ${ x \in E,  \lVert x \rVert \leq \delta }$ implies ${ \lVert \lambda (x) \rVert < 1 . }$ Now for any ${ x \in E, x \neq 0 }$ the stretch 

$${ \begin{align*} \frac{\lVert \lambda (x) \rVert}{\lVert x \rVert} &= \frac{1}{\delta} \bigg\lVert \lambda \bigg( \underbrace{\frac{x}{\lVert x \rVert} \delta} _{\text{of norm } \delta} \bigg)  \bigg\rVert \\ &< \frac{1}{\delta}, \end{align*} }$$

so ${ \sup _{x \neq 0} \frac{\lVert \lambda(x) \rVert}{\lVert x \rVert} < \infty.   }$ 

**Eg** [A linear map which isn’t continuous]: Consider the space of polynomial functions on ${ [0, 1 ] }$ 

$${ V = \lbrace p \in C[0, 1] : p \text{ is polynomial} \rbrace \subseteq C [0, 1]  }$$

and the differentiation operator 

$${ D : V \to V, \quad p \mapsto p ^{’} .  }$$ 

Linearity of ${ D }$ is clear. But for every positive integer ${ n }$ 

$${ \sup _{v \in V, v \neq 0} \frac{\lVert D(v) \rVert}{\lVert v \rVert} \geq \frac{\lVert D(x ^n) \rVert}{\lVert x ^n \rVert} = n,  }$$ 

so ${ D }$ isn’t continuous. 

**Obs**: Let ${ F }$ be a normed vector space. Any linear map ${ \lambda : \mathbb{R} ^n \to F }$ is continuous.    
**Pf**: For any ${ x \in \mathbb{R} ^n, }$ 

$${ \begin{align*} \lVert \lambda (x) \rVert &= \bigg\lVert \sum _{i=1} ^{n} x _i \lambda ( e _i ) \bigg\rVert \\ &\leq  \sum _{i=1} ^{n} \vert x _i \vert \lVert \lambda (e _i) \rVert  \\ &\leq \lVert x \rVert _{u} \sqrt{\sum _{i=1} ^n \lVert \lambda(e _i) \rVert ^2 }  ,   \end{align*} }$$

so ${ \lambda }$ is uniformly continuous. 

**Def** [Space of continuous linear maps]:    
Let ${ E, F }$ be normed vector spaces. The space of continuous linear maps from ${ E }$ to ${ F }$ is written 

$${ L(E, F) := \lbrace \text{continuous linear maps } E \to F \rbrace.}$$

It is a vector space. Such spaces can be given the (submultiplicative) norm 

$${ \lVert \lambda \rVert := \sup _{ x \neq 0} \frac{ \lVert \lambda (x) \rVert}{\lVert x \rVert} < \infty, \quad \text{ for } \lambda \in L(E, F). }$$ 

Here, if ${ F }$ is complete so is ${ L(E, F) .}$ 

**Thm** [Completeness of ${ L(E, F) }$]:    
Let ${ E, F }$ be normed vector spaces. Now 

$${ F \text{ is complete} \implies L(E, F) \text{ is complete}. }$$ 

**Pf**: Say ${ F }$ is complete. Let ${ (\lambda _n) }$ be a Cauchy sequence in ${ L(E, F). }$ We are to show a ${ \lambda \in L(E, F)}$ for which ${ \lVert \lambda _n - \lambda \rVert \to 0 }$ as ${ n \to \infty . }$    
Pick an ${ x \in E, x \neq 0 .}$ The sequence ${ (\lambda _n (x)) }$ is Cauchy, because 

$${ \lVert \lambda _m (x) - \lambda _n (x) \rVert \leq \lVert \lambda _m - \lambda _n \rVert \lVert x \rVert  }$$ 

and ${ (\lambda _n) }$ is Cauchy.  As ${ F }$ is complete, the Cauchy sequence ${ (\lambda _n (x) ) }$ converges to a limit, which we can call ${ \lambda (x) .}$ We now have the pointwise limit 

$${ \begin{align*} &\lambda : E \to F , \\ &x \mapsto \lambda(x) := \lim _{n \to \infty} \lambda _n (x) . \end{align*} }$$ 

It suffices to show 

$${ \text{To show: } \lambda \in L(E,F), \quad \lVert \lambda _n - \lambda \rVert \to 0.  }$$ 

That ${ \lambda }$ is linear is clear: 

$${ \begin{align*} \lambda (\alpha   x  + \beta y) &= \lim _{n \to \infty} \lambda _n (\alpha x + \beta y) \\ &= \lim _{n \to \infty} (\alpha  \lambda _n (x) + \beta \lambda _n (y))  \\ &= \alpha \lambda (x) + \beta \lambda (y).  \end{align*}  }$$ 

We are to show ${ \lambda }$ is continuous, that is ${ \sup _{x \neq 0} \frac{\lVert \lambda(x) \rVert}{\lVert x \rVert} < \infty .}$    
Let ${ x \in E, x \neq 0 .}$ Note  

$${ \frac{\lVert \lambda _n (x) \rVert}{\lVert x \rVert} \leq \lVert \lambda _n \rVert . }$$ 

 Since ${ (\lambda _n) }$ is bounded by some ${ C > 0  }$ (because it is Cauchy), we have 

$${ \frac{\lVert \lambda _n (x) \rVert}{\lVert x \rVert} \leq C .  }$$ 

Since ${ \lVert \lambda _n (x) \rVert \to \lVert \lambda (x) \rVert }$ (because ${ \vert \lVert \lambda _n (x) \rVert - \lVert \lambda (x) \rVert \vert}$ ${ \leq \lVert \lambda _n (x) - \lambda (x) \rVert \to 0 }$), letting ${ n \to \infty }$ gives 

$${ \frac{\lVert \lambda  (x) \rVert}{\lVert x \rVert} \leq C .   }$$

So ${ \sup _{x \neq 0} \frac{\lVert \lambda(x) \rVert}{\lVert x \rVert} < \infty }$ as needed. 

It is left to show 

$${ \text{To show: } \lVert \lambda _n - \lambda \rVert \to 0 \text{ as } n \to \infty. }$$ 

Let ${ \epsilon > 0 .}$ Since ${ (\lambda _n) }$ is Cauchy, there is an ${ N }$ such that ${ \lVert \lambda _m - \lambda _n \rVert < \epsilon }$ whenever ${ m , n \geq N .}$ Equivalently 

$${ \frac{\lVert \lambda _m (x) - \lambda _n (x) \rVert}{\lVert x \rVert}  < \epsilon \text{ whenever } m, n \geq N \text{ and } x \in E, x \neq 0 . }$$

Fix a choice of ${ x \neq 0, m \geq N }$ and let ${ n \to \infty .}$ This gives 

$${ \frac{\lVert \lambda _m (x) - \lambda (x) \rVert}{\lVert x \rVert} \leq \epsilon  \text{ for every choice of } m \geq N, x \neq 0 . }$$ 

Equivalently

$${ \lVert \lambda _m - \lambda  \rVert \leq \epsilon \text{ for every choice of } m \geq N.  }$$ 

So ${ \lVert \lambda _m - \lambda \rVert \to 0 }$ as ${ m \to \infty, }$ as needed. ${ \blacksquare }$ 

 Completeness of ${ L(E, F) }$ is important when considering integrals of maps ${ f : [a, b] \to L(E, F) .}$ 

**Thm** [Continuity of a bilinear map]:    

Let ${ E, F, G }$ be normed vector spaces and ${ \lambda : E \times F \to G }$ a bilinear map. 

Equip ${ E \times F }$ with say the sup norm ${ \lVert (x, y) \rVert := \max \lbrace \lVert x \rVert, \lVert y \rVert \rbrace }$ or the norm ${ \lVert (x,y) \rVert _{u} := \sqrt{\lVert x \rVert ^2 + \lVert y \rVert ^2 } .}$  (They are equivalent norms as ${ \lVert (x, y) \rVert \leq \lVert (x, y) \rVert _u \leq \sqrt{2} \lVert (x, y) \rVert }$). For concreteness, the sup norm. 

Now 

$${ \begin{align*} &(\lambda \text{ is continuous}) \\ \iff &\Bigg(\sup _{\lVert u \rVert = \lVert v \rVert = 1} \lVert \lambda (u, v) \rVert = \sup _{u \neq 0, v \neq 0} \frac{\lVert \lambda (u, v) \rVert}{\lVert u \rVert \lVert v \rVert} < \infty \Bigg) .  \end{align*}  }$$    

**Pf**: ${ \underline{\Rightarrow} }$ Say ${ \lambda }$ is continuous. So there is a ${ \delta > 0 }$ such that ${ \lVert (x, y) \rVert \leq \delta }$ implies ${ \lVert \lambda (x, y) \rVert < 1 .}$ Now for ${ (x, y) \in E \times F }$ with ${ x \neq 0, y \neq 0 }$ the stretch 

$${ \begin{align*} \frac{\lVert \lambda(x, y) \rVert}{\lVert x \rVert \lVert y \rVert} &= \frac{1}{\delta ^2} \bigg\lVert \lambda \bigg( \underbrace{\delta \frac{x}{\lVert x \rVert}, \delta \frac{y}{\lVert y \rVert}} _{\text{of norm } \delta}  \bigg)\bigg\rVert \\ &< \frac{1}{\delta ^2}.   \end{align*}  }$$ 

So ${  \sup _{x \neq 0, y \neq 0} \frac{\lVert \lambda (x, y) \rVert}{\lVert x \rVert \lVert y \rVert} < \infty. }$  

${ \underline{\Leftarrow} }$ Say ${ C =  \sup _{u \neq 0, v \neq 0} \frac{\lVert \lambda (u, v) \rVert}{\lVert u \rVert \lVert v \rVert} < \infty. }$ Now 

$${ \lVert \lambda(u, v) \rVert \leq C \lVert u \rVert \lVert v \rVert \text{ for all } (u, v) \in E \times F,  u \neq 0, v \neq 0 .}$$ 

As ${ \lambda (u , 0) = 0 }$ because ${ \lambda(u, 0+0) = \lambda(u, 0) + \lambda(u, 0) ,}$ and ${ \lambda(0, v) = 0 ,}$ we have 

$${ \lVert \lambda (u, v) \rVert \leq C \lVert u \rVert \lVert v \rVert \text{ for all } (u, v) \in E \times F .}$$

We are to show continuity of ${ \lambda .}$    
Say a sequence ${ (x _n , y _n) \to (x, y) }$ in ${ E \times F.}$ We are to show ${ \lambda(x _n, y _n) \to \lambda(x, y) .}$ We see  

$${ \begin{align*} \lVert \lambda(x _n, y _n) - \lambda(x, y) \rVert &\leq  \lVert \lambda(x _n, y _n) - \lambda(x _n, y) \rVert + \lVert \lambda(x _n, y) - \lambda(x, y) \rVert \\ &= \lVert \lambda (x _n, y _n - y) \rVert + \lVert \lambda (x _n - x , y) \rVert \\ &\leq C(\lVert x _n \rVert \lVert y _n - y \rVert + \lVert x _n - x \rVert \lVert y \rVert) \to 0,    \end{align*} }$$ 

so ${ \lambda(x _n, y _n) \to \lambda(x, y) }$ as needed. ${ \blacksquare }$ 

A similar observation holds for multilinear maps. 

For normed spaces ${ E _1, \ldots, E _n ; F }$ the set ${ L(E _1, \ldots, E _n ; F) }$ of continuous multilinear maps ${ E _1 \times \ldots \times E _n \to F }$ is a vector space and given the norm 

$${ \lVert \lambda \rVert := \sup \lbrace \lVert \lambda (x _1, \ldots, x _n) \rVert : \lVert x _1 \rVert = \ldots = \lVert x _n \rVert = 1 \rbrace < \infty . }$$

Here, if ${ E _1 = \ldots = E _n = E , }$ we write the space as ${ L ^n (E; F) . }$ For now the focus is on continuous linear maps. 

###### 2

$${ \underline{\textbf{Differentiation}} }$$ 

Let ${ E, F }$ be normed spaces, ${ f : U (\subseteq E \text{ open}) \to F , }$ and ${ p \in U .}$ It is useful to have a continuous affine map (i.e. a map of the form ${  a + \lambda(x) }$ with ${ \lambda \in L(E, F) }$) which approximates ${ f }$ well near ${ p .}$ 

First we need to fix a notion of “approximating well near ${ p }$”. 

Consider functions ${ f, g : \mathbb{R} \to \mathbb{R} }$ differentiable at ${ p \in \mathbb{R} .}$ We can say “${ f(x) \approx g(x) }$ near ${ p }$ to first order” if the tangent line approximations at ${ p }$ agree, that is ${ f(p) + f ^{’} (p) (x-p) = g(p) + g ^{’} (p) (x-p) ,}$ that is ${ \lbrace f(p) = g(p), f ^{’} (p) = g ^{’} (p) \rbrace .}$

Now consider functions ${ f, g : \mathbb{R} ^n \to \mathbb{R}  }$ and a point ${ p \in \mathbb{R} ^n .}$ A first attempt is to say “${ f(x) \approx g(x) }$ near ${ p }$ to first order” if for every unit vector ${ e }$ the slices 

$${ t \mapsto f(p + te), \quad t \mapsto g(p + te) }$$

agree approximately near ${ 0 }$ in the above ${1}$D sense. (Say all directional derivatives ${ \frac{d}{dt} \big\vert _{t=0} f(p + te),  }$ ${ \frac{d}{dt} \big\vert _{t=0} g(p + te)  }$ exist). The condition is equivalent to asking 

$${ \left\lbrace \begin{align*} &f(p) = g(p), \text{ and} \\ &\frac{d}{dt} \bigg\vert _{t=0} f(p+te) = \frac{d}{dt} \bigg\vert _{t=0} g(p+te) \text{ for every unit vector } e \in \mathbb{R} ^n  \end{align*} \right\rbrace }$$ 

that is 

$${ \left\lbrace \begin{align*} &f(p) = g(p), \text{ and} \\ &\lim _{t \to 0} \frac{f(p+te) - g(p+te)}{t} = 0 \text{ for every unit vector } e \in \mathbb{R} ^n \end{align*} \right\rbrace  .}$$ 

A sort of strengthening of this gives the actual definition. 

**Def** [Approximation to first order]: Let ${ E, F }$ be normed spaces, ${ f, g : U (\subseteq E \text{ open}) \to F ,}$ and ${ p \in U .}$ We say 

$${ f(x) \approx g(x)  \text{ near } p \text{ to first order} }$$

if, for ${ h }$ in a neighbourhood of ${ 0 ,}$ we have 

$${ \left\lbrace \begin{align*} &f(p) = g(p), \text{ and} \\ &\text{the error }  \varepsilon(h) := f(p+h) - g(p+h) \text{ satisfies } \lim _{h \to 0} \frac{\varepsilon(h)}{\lVert h \rVert}  = 0  \end{align*} \right\rbrace  }$$ 

that is 

$${ \left\lbrace \begin{align*} &f(p+h) =  g(p+h) + \varepsilon(h) \text{ with } \\ &\varepsilon(0) = 0 \text{ and } \lim _{h \to 0} \frac{\varepsilon(h)}{\lVert h \rVert} = 0  \end{align*} \right\rbrace }$$ 

that is 

$${ \left\lbrace \begin{align*} &f(p+h) = g(p+h) + \lVert h \rVert \varphi(h)  \text{ with } \\ &\varphi(0) = 0 \text{ and } \varphi \text{ continuous at } 0 \end{align*} \right\rbrace .  }$$ 

Let ${ E, F }$ be normed spaces, ${ f : U (\subseteq E \text{ open}) \to F ,}$ and ${ p \in U .}$ Any continuous affine map ${ a + \lambda(x) }$ such that “${ f(x) \approx a + \lambda(x) }$ near ${ p }$ to first order” must have ${ f(p) = a + \lambda(p) ,}$ and so must look like ${ f(p) + \lambda(x - p)  }$ with ${ \lambda \in L(E, F) .}$

**Def** [Derivative]: Let ${ E, F }$ be normed spaces, ${ f : U (\subseteq E \text{ open}) \to F },$ and ${ p \in U .}$    
A derivative of ${ f }$ at ${ p \in U }$ (if it exists) is a continuous linear map 

$${ Df(p) = f ^{’} (p)  \in L(E, F) }$$

such that 

$${  \, ^{``} f(x) \approx f(p) + f ^{’} (p)  (x - p)  \text{ near } p \text{ to first order} ^{"} }$$

that is (for ${ h }$ in a neighbourhood of ${ 0 }$) 

$${ \left\lbrace \begin{align*}  &f(p+h) = f(p) + f ^{’} (p) h + \lVert h \rVert \varphi(h) \text{ with} \\ &\varphi(0) = 0 \text{ and } \varphi \text{ continuous at } 0 \end{align*} \right\rbrace.  }$$ 

**Obs**: In the above setup, if an ${ f ^{’} (p) }$ exists, taking limit of ${ f(p+h) }$ as ${ h \neq 0, h \to 0 }$ (using continuity of ${ f ^{’} (p) }$ and ${ \varphi }$ at ${ 0 }$) gives ${ \lim _{h \to 0} f(p+h) = f(p) .}$ So differentiability at ${ p }$ implies continuity at ${ p .}$ 

**Thm** [Uniqueness of Derivative]:    
Let ${ E, F }$ be normed spaces, ${ f : U (\subseteq E \text{ open}) \to F , }$ and ${ p \in U .}$ Say ${ \lambda _1, \lambda _2 \in L(E, F) }$ are both derivatives of ${ f }$ at ${ p .}$ Then ${ \lambda _1 = \lambda _2 }$.   

**Pf**: We have (implicitly for ${ h }$ in a neighbourhood of ${ 0 }$) 

$${ \begin{align*} f(p+h) &= f(p) + \lambda _1 (h) + \lVert h \rVert \varphi _1 (h) \\ &= f(p) + \lambda _2 (h) +  \lVert h \rVert \varphi _2 (h) \end{align*}  }$$ 

with ${ \varphi _1 (0) = \varphi _2 (0) = 0 }$ and ${ \varphi _1, \varphi _2 }$ continuous at ${ 0 .}$    

Let ${ v \in E , v \neq 0 .}$ We are to show 

$${ \text{To show: } \lambda _1 (v) = \lambda _2 (v) .}$$

For ${ t }$ in a neighbourhood of ${ 0 ,}$ 

$${ f(p) + \lambda _1 (tv) + \lVert tv \rVert \varphi _1 (tv) = f(p) + \lambda _2 (tv) + \lVert tv \rVert \varphi _2 (tv) }$$ 

so

$${ \vert t \vert  \lVert \lambda _1 (v) - \lambda _2 (v) \rVert = \vert t \vert \lVert v \rVert \lVert \varphi _1 (tv) - \varphi _2 (tv) \rVert   . }$$ 

Dividing by ${ \vert t \vert \neq 0 }$ and letting ${ \vert t \vert \to 0, }$ we see 

$${ \lVert \lambda _1 (v) - \lambda _2 (v) \rVert = 0 }$$ 

as needed. 

**Thm** [Derivative of linear combination]:    
Let ${ E, F }$ be normed spaces, ${ f , g : U (\subseteq E \text{ open}) \to F ,}$ and ${ x \in U .}$ If ${ f, g }$ are differentiable at ${ x }$ and ${ c \in \mathbb{R}, }$ then so is ${ f + cg }$ with 

$${ D(f + cg) (x) = Df (x) + c Dg(x) . }$$ 

**Pf**: We have (for ${ h }$ in a neighbourhood of ${ 0 }$) 

$${ \begin{align*} &f(x + h) = f(x) + Df(x) h + \lVert h \rVert \varphi _f (h), \\ &g(x+h) = g(x) + Dg(x) h + \lVert h \rVert \varphi _g (h) \end{align*} }$$ 

with ${ \varphi _f (0) = \varphi _g (0) = 0 }$ and ${ \varphi _f, \varphi _g }$ continuous at ${ 0 .}$ 

Taking linear combination, 

$${ \begin{align*} (f + cg)(x+h) = \, &(f + cg)(x) + \underbrace{(Df(x) + c Dg(x))} _{\text{in } L(E, F)} h \\ &+ \lVert h \rVert (\varphi _f (h) + c \varphi _g (h))  \end{align*}  }$$ 

with ${ (\varphi _f + c \varphi _g) (0) = 0 }$ and ${ ( \varphi _f + c \varphi _g) }$ continuous at ${ 0 .}$ 

So ${ D(f + cg) (x) = Df(x) + c Dg(x) .}$ 

**Thm** [Derivative of product]:    
Say ${ E, F _1, F _2, G }$ are normed spaces, and ${ \bullet : F _1 \times F _2 \to G, }$ ${ (u, v) \mapsto u \bullet v }$ is a continuous bilinear map.    
If ${ f : U (\subseteq E \text{ open}) \to F _1 }$ and ${ g : U (\subseteq E \text{ open}) \to F _2 }$ are differentiable at ${ x \in U ,}$ then so is ${ f \bullet g : U (\subseteq E \text{ open}) \to G, }$ ${ t \mapsto f(t) \bullet g(t) }$ with 

$${ D (f \bullet g)   (x)  = Df(x) \bullet g(x)   + f(x) \bullet Dg(x) .  }$$ 

**Pf**: For ${ h }$ in a neighbourhood of ${ 0 ,}$ 

$${ \begin{align*} &f(x+h) = f(x) + Df(x) h + \lVert h \rVert \varphi _f (h), \\  &g(x+h) = g(x) + Dg(x) h + \lVert h \rVert \varphi _g (h) \end{align*} }$$ 

with ${ \varphi _f (0) = \varphi _g (0) = 0 }$ and ${ \varphi _f, \varphi _g }$ continuous at ${ 0 .}$

Now 

$${ \begin{align*} &f(x+h) \bullet g(x+h) \\ = &(f(x) + Df(x) h + \lVert h \rVert \varphi _f (h)) \bullet (g(x) + Dg(x)h + \lVert h \rVert \varphi _g (h)) \\ = &(f(x) + Df(x) h ) \bullet (g(x) + Dg(x) h) \\ &+ \underbrace{\lVert h \rVert \left[ (f(x) + Df(x) h) \bullet \varphi _g (h) + \varphi _f (h) \bullet (g(x) + Dg(x)h) \right] + \lVert h \rVert ^2 \varphi _f (h) \bullet \varphi _g (h)} _{=: \, \varepsilon _1 (h)}  \\ = &f(x) \bullet g(x) + (Df(x)h \bullet g(x) + f(x) \bullet Dg(x)h)  + \underbrace{Df(x) h \bullet Dg(x) h + \varepsilon _1 (h)} _{=: \, \varepsilon (h)} . \end{align*} }$$ 

We are to show the error ${ \varepsilon(h) }$ satisfies ${ \varepsilon(0) = 0 }$ and ${ \lim _{h \to 0} \frac{\varepsilon(h)}{\lVert h \rVert} = 0 .}$ To show the latter, one shows each term ${ t(h) }$ of ${ \varepsilon(h) }$ satisfies ${ \frac{t(h) }{\lVert h \rVert} \to 0 }$ as ${ h \to 0 .}$ For example, 

$${ \begin{align*} \frac{\lVert Df(x)h \bullet Dg(x)h \rVert}{\lVert h \rVert} &\leq \frac{\lVert \bullet \rVert \lVert Df(x) h \rVert \lVert Dg(x) h \rVert}{\lVert h \rVert} \\ &\leq \frac{\lVert \bullet \rVert \lVert Df(x) \rVert \lVert Dg(x) \rVert \lVert h \rVert ^2}{\lVert h \rVert} \to 0 \text{ as } h \to 0  \end{align*} }$$ 

and 

$${ \begin{align*} \frac{\left\lVert \lVert h \rVert (f(x) + Df(x) \, h) \bullet \varphi _g (h) \right\rVert}{\lVert h \rVert} &\leq \lVert \bullet \rVert \lVert f(x) + Df (x) \, h \rVert \lVert \varphi _g (h) \rVert \to 0 \text{ as } h \to 0 .   \end{align*} }$$ 

Now it is left to show 

$${ h \mapsto Df(x)h \bullet g(x) + f(x) \bullet Dg(x)h }$$

is in ${ L(E, G) .}$ Denote the maps 

$${ h \mapsto Df(x)h \bullet g(x) , \quad h \mapsto  f(x) \bullet Dg(x)h }$$

by ${ Df(x) \bullet g(x) }$ and ${ f(x) \bullet Dg(x) }$ respectively.  They are in ${ L(E, G) }$ because for example 

$${ \begin{align*} \frac{\lVert Df(x)h \bullet g(x)\rVert}{\lVert h \rVert} &\leq \frac{\lVert \bullet  \rVert \lVert Df(x) h \rVert \lVert g(x) \rVert }{\lVert h \rVert} \\ &\leq \lVert \bullet \rVert \lVert Df(x) \rVert \lVert g(x) \rVert . \end{align*}  }$$ 

Finally 

$${ D(f \bullet g) (x) = Df(x) \bullet g(x) + f(x) \bullet Dg(x)  . }$$ 

**Thm** [Derivative of composition]:    
Let ${ E, F , G }$ be normed spaces. Consider maps 

$${U (\subseteq E \text{ open}) \overset{f}{\longrightarrow} V (\subseteq F \text{ open}) \overset{g}{\longrightarrow} G ,  }$$ 

and a point ${ x \in U .}$ If ${ f }$ is differentiable at ${ x }$ and ${ g }$ is differentiable at ${ f(x) ,}$ then ${ g \circ f }$ is differentiable at ${ x }$ with 

$${ D(g \circ f)(x)  = D(g) (f(x)) \circ D(f)(x) . }$$ 

> Intuitively 
>
> $${ \begin{align*} g(f(x + h)) \approx &\, g(f(x) + Df(x) \, h)  \\ \approx &\, g(f(x)) +  Dg (f(x)) \,  Df(x)  h .  \end{align*} }$$ 

**Pf**: By differentiability of ${ f }$ at ${ x , }$ there is an ${ \eta _1  > 0 }$ such that 

$${ \begin{align*} &\text{For } \lVert h \rVert < \eta _1: \\ &f(x + h) = f(x) + D(f)(x) \, h + \lVert h \rVert \varphi _f (h) \\ &\text{with } \varphi _f (0) = 0 \text{ and } \varphi _f \text{ continuous at } 0.  \end{align*}  }$$ 

By differentiability of ${ g }$ at ${ f(x), }$ there is an ${ \eta _2 > 0 }$ such that 

$${ \begin{align*} &\text{For } \lVert k \rVert < \eta _2: \\ &g( f(x) + k) =  g(f(x)) + D(g)(f(x)) \, k + \lVert k \rVert \varphi _g (k) \\ &\text{with } \varphi _g (0) = 0 \text{ and } \varphi _g \text{ continuous at } 0.    \end{align*}  }$$ 

Using these, 

$${ \begin{align*} &(g \circ f)(x + h) \\ = &\, g( f(x+h) ) \\ {\color{red}{=}}  &\, g \bigg(f(x) + \underbrace{\boxed{D(f)(x) \, h + \lVert h \rVert \varphi _f (h)}} _{ \Box(h)} \bigg) \\ {\color{blue}{=}} &\, g(f(x)) + D(g)(f(x)) \, \Box (h) + \lVert \Box (h) \rVert  \varphi _g \left( \Box(h)  \right)  \end{align*} }$$ 

whenever ${ {\color{red}{\lVert h \rVert < \eta _1}} }$ and ${ {\color{blue}{ \left\lVert \Box (h)  \right\rVert} < \eta _2 } . }$ 

Since 

$${ \Box (h) := D(f)(x) \, h + \lVert h \rVert \varphi _f (h)  }$$

is continuous at ${ 0, }$ we can pick a small enough ${ \eta > 0 }$ such that for ${ \lVert h \rVert < \eta,  }$ both ${ \lVert h \rVert < \eta _1 }$ and ${  \left\lVert \Box (h)  \right\rVert  < \eta _2  }$ hold. 

Now for ${ \lVert h \rVert < \eta ,}$ 

$${ \begin{align*} &(g \circ f)(x+h) \\ = &g(f(x)) + D(g)(f(x)) \, \Box (h) + \lVert \Box (h) \rVert  \varphi _g \left( \Box(h)  \right) \\ = &(g \circ f)(x) + \big[ D(g)(f(x)) \circ D(f)(x) \big] \, h \\ &+  \underbrace{\lVert h \rVert D(g) (f(x)) \, \varphi _f (h) + \lVert \Box (h) \rVert \varphi _g (\Box (h))} _{=: \, \varepsilon(h) } .  \end{align*} }$$ 

Note  ${ \varepsilon(h) = 0 }$ and ${ \lim _{h \to 0} \frac{\varepsilon(h)}{\lVert h \rVert} = 0 .}$  The latter is because both 

$${ \begin{align*} \frac{\left\lVert  \lVert h \rVert D(g) (f(x)) \, \varphi _f (h) \right\rVert }{\lVert h \rVert} &\leq \lVert D(g) (f(x)) \rVert \lVert \varphi _f (h) \rVert \to 0 \text{ as } h \to 0  \end{align*} }$$ 

and 

$${ \begin{align*} \frac{\left\lVert \lVert \Box (h) \rVert \varphi _g (\Box (h))  \right\rVert}{\lVert h \rVert} \leq &\frac{1}{\lVert h \rVert} \left( \lVert D(f)(x) \rVert \lVert h \rVert + \lVert h \rVert \lVert \varphi _f (h) \rVert\right) \,  \lVert \varphi _g (\Box (h))  \rVert \\ &\to 0  \text{ as } h \to 0.    \end{align*} }$$ 

It is left to show ${ D(g)(f(x)) \circ D(f)(x) \in L(E, G).  }$ This is true because 

$${ \begin{align*} \frac{\lVert\left[ D(g)(f(x)) \circ D(f)(x) \right] h \rVert}{\lVert h \rVert} &\leq  \frac{\lVert D(g)(f(x)) \rVert \lVert D(f)(x) h \rVert}{\lVert h \rVert} \\ &\leq \lVert D(g) (f(x)) \rVert \lVert D(f)(x) \rVert.   \end{align*} }$$ 

Finally 

$${ D(g \circ f)(x)  = D(g) (f(x)) \circ D(f)(x).   }$$ 

Derivative of ${ g \circ f }$ at ${ x }$ is derivative of ${ g }$ at ${ f(x) }$ composed with derivative of ${ f }$ at ${ x .}$ 

**Eg**: Consider ${ C[0, 1], }$ and the map 

$${ Q : C[0, 1] \to \mathbb{R} , }$$ 

$${ Q(f) = \int _0 ^1 t f ^{3} (t) \, dt .  }$$ 

We can study if ${ Q }$ is differentiable at ${ \varphi \in C[0, 1] .}$ 

$${ \begin{align*} Q(\varphi + h) - Q(\varphi) = &\int _0 ^1 t \, (h ^{3} (t) + 3 \varphi ^{2} (t) h(t) + 3 \varphi(t) h ^{2} (t) ) \, dt \\ = &\underbrace{\int _0 ^{1} 3t  \varphi ^2 (t) h(t) \, dt} _{=: \,  L(h)}  +  \underbrace{\int _{0} ^{1} (t h ^{3} (t) + 3 t  \varphi(t) h ^{2} (t) ) \, dt} _{=: \, \varepsilon(h)}  .  \end{align*}  }$$ 

Note ${ L(h) }$ is continuous linear: Linearity is clear. For ${ h _1, h _2 \in C[0, 1],  }$ 

$${ \begin{align*} &\vert L(h _1) - L(h _2) \vert \\ = &\left\vert \int _0 ^1 3 t \varphi ^2 (t) (h _1 (t) - h _2 (t)) \, dt \right\vert \\ \leq &\sup _{t \in [0, 1]} \vert 3 t \varphi ^2 (t) ( h _1 (t) - h _2 (t))   \vert  \\ \leq &\left(\sup _{t \in [0, 1]} \vert 3t \varphi ^2 (t) \vert \right) \lVert h _1 - h _2  \rVert \end{align*}  }$$ 

so ${ L }$ is uniformly continuous. 

It is left to show the error ${ \varepsilon(h) }$ satisfies ${ \varepsilon(0) = 0 }$ and ${ \lim _{\lVert h \rVert \to 0} \frac{\varepsilon(h)}{\lVert h \rVert} = 0 .}$ Indeed for ${ h \neq 0 }$ 

$${ \begin{align*} \frac{\vert \varepsilon(h) \vert}{\lVert h \rVert} \leq &\frac{\lVert h \rVert ^3 + 3 \lVert \varphi \rVert \lVert h \rVert ^2   }{\lVert h \rVert} \to 0  \end{align*} }$$ 

as ${ \lVert h \rVert \to 0 .}$ 

So the derivative of ${ Q }$ at ${ \varphi }$ is

$${ DQ (\varphi) : C[0, 1] \to \mathbb{R},  }$$ 

$${ DQ(\varphi) \, h =  \int _0 ^1  3 t \varphi ^2 (t) h(t) \, dt .  }$$ 
