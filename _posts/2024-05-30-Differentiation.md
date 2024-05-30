---
layout: post
title: "Differentiation"
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
Updated: 30/5/24 

Sections: [Continuous linear maps](#1.); [Differentiation](#2.); [Differentiation of maps ${ \mathbb{R} ^n \to \mathbb{R} ^m }$](#3.);  [Integration of maps ${ f : [a, b] \to E }$](#4.); [Mean value theorem](#5.); [Second derivative](#6.); [Third derivative](#7.); [Higher derivatives](#8.); [Taylor’s theorem](#9.)


###### 1.

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

###### 2. 

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

###### 3. 

$${ \underline{\textbf{Differentiation of maps } \mathbb{R} ^n \to \mathbb{R} ^m} }$$

**Def** [Partial derivatives]: Let ${ f : U (\subseteq \mathbb{R} ^n \text{ open}) \to \mathbb{R} }$ and ${ x \in U .}$ The partial derivative of ${ f }$ at ${ x }$ in the direction ${ e _i }$ is 

$${ D _i f (x) = \frac{\partial f}{\partial x _i} (x) := \lim _{h \to 0} \frac{f(x + he _i) - f(x)}{h}.   }$$ 

**Thm**  [Derivative and partials, ${ \mathbb{R} ^n \to \mathbb{R} }$ case]: 

Consider ${ f : U (\subseteq \mathbb{R} ^n \text{ open}) \to \mathbb{R} }$ and ${ x \in U .}$    

**i)** Say ${ f }$ is differentiable at ${ x .}$ Then all the partial derivatives ${ D _i f (x) }$ exist, and the derivative looks like 

$${ Df (x) = (D _1 f (x), \ldots , D _n f (x) )   .}$$ 

**ii)** Conversely, say all the partial derivatives ${ D _i f }$ exist in a neighbourhood of ${ x ,}$ and are continuous at ${ x }$. Then ${ f }$ is differentiable at ${ x }$ (and as above, the derivative looks like ${ Df (x) = (D _1 f (x), \ldots, D _n f (x)) }$).    

**Pf**: **i)** Say ${ f }$ is differentiable at ${ x , }$ that is ${ Df (x) }$ exists. Now (implicitly for ${ h }$ in a neighbourhood of ${ 0 }$) 

$${ \begin{align*} &f(x+h) = f(x) + Df(x) h + \lVert h \rVert \varphi(h) \text{ with } \\ &\varphi(0) = 0 \text{ and } \varphi \text{ continuous at } 0 . \end{align*} }$$

Putting ${ h = t e _i }$ we see (for ${ t }$ in a neighbourhood of ${ 0 }$) 

$${ f(x + te _i) = f(x) + Df(x) te _i + \vert t \vert \varphi(te _i).  }$$ 

Dividing by ${ t \neq 0 }$ we see 

$${ \left\vert \frac{f(x + t e _i) - f(x)}{t} - Df (x) e _i \right\vert = \underbrace{\vert \varphi (t e _i) \vert} _{\to 0 \text{ as } t \to 0} , }$$ 

giving that 

$${ \text{Each } D _i f (x) \text{ exists, and is } D _i f (x) = Df (x) e _i.   }$$ 

Now ${ Df (x) }$ looks like 

$${ \begin{align*} Df(x) &= (Df(x) \, e _1, \ldots, Df(x) \, e _n) \\ &= (D _1 f (x), \ldots, D _n f (x)), \end{align*} }$$ 

as needed. 

**ii)** Say all the partial derivatives ${ D _i f }$ exist in a neighbourhood of ${ x },$ and are continuous at ${ x .}$ We will show that ${ (D _1 f (x), \ldots, D _n f (x)) }$ works as the derivative at ${ x .}$    

Using 1D mean value theorem repeatedly, (for ${ h }$ in a neighbourhood of ${ 0 }$) 

$${ \begin{align*} &f(x _1 + h _1, \ldots, x _n + h _n) \\ = &f(x _1 , x _2 + h _2, \ldots, x _n + h _n) + D _1 f (x _1 + \theta _1 h _1, x _2 + h _2, \ldots, x _n + h _n) \,  h _1 \\ = &f(x _1, x _2, x _3 + h _3, \ldots, x _n + h _n) + D _2 f (x _1 , x _2 + \theta _2 h _2, x _3 + h _3, \ldots, x _n + h _n) \, h _2 \\ &+ D _1 f (x _1 + \theta _1 h _1, x _2 + h _2, \ldots, x _n + h _n) \,  h _1 \\ \vdots \\ = &f(x) + \sum _{i=1} ^{n} D _i f (x _1 , \ldots, x _{i-1}, x _i + \theta _i h _i, x _{i+1} + h _{i+1},  \ldots, x _n + h _n) \, h _i   \end{align*}   }$$ 

with each ${ \theta _i = \theta _i ( h) \in (0, 1) .}$ 

By continuity of each ${ D _i f }$ at ${ x, }$ 

$${ \begin{align*} &D _i f (x _1 , \ldots, x _{i-1}, x _i + \theta _i h _i, x _{i+1} + h _{i+1},  \ldots, x _n + h _n) =  D _i f (x) + \psi _i (h) \\ &\text{with } \psi _i (h) \text{ continuous at 0} . \end{align*} }$$ 

Combining both, 

$${ \begin{align*} &f(x+h) \\ = &f(x) +   \sum _{i=1} ^{n} D _i f (x _1 , \ldots, x _{i-1}, x _i + \theta _i h _i, x _{i+1} + h _{i+1},  \ldots, x _n + h _n) \, h _i \\ = &f(x) + \sum _{i=1} ^{n} \left( D _i f (x) + \psi _i (h) \right) \, h _i  \\ = &f(x) + \underbrace{\sum _{i=1} ^{n} D _i f (x) \, h _i} _{(D _1 f (x) \, , \, \ldots \, , \, D _n f (x)) \, h}  +  \underbrace{\sum _{i=1} ^{n} \psi _i (h) \,  h _i } _{\varepsilon(h)} .  \end{align*}  }$$ 

The error ${ \varepsilon(h)  = \sum _{i=1} ^{n} \psi _i (h) \,  h _i }$ satisfies ${ \varepsilon(0) = 0 }$ and 

$${ \begin{align*} \frac{\vert \varepsilon(h) \vert}{\lVert h \rVert} &\leq  \frac{\sum _{i=1} ^{n} \vert h _i \vert \vert \psi _i (h) \vert}{\lVert h \rVert}  \\ &\leq \frac{\lVert h \rVert \sqrt{\sum _{i=1} ^{n} \vert \psi _i (h) \vert ^2}}{\lVert h \rVert } \\ &= \left(\sum _{i=1} ^n \vert \psi _i (h) \vert ^2 \right) ^{\frac{1}{2}} \to 0 \text{ as } h \to 0 .  \end{align*} }$$ 

So 

$${  (D _1 f (x), \ldots, D _n f(x)) }$$ 

works as the derivative of ${ f }$ at ${ x .}$ ${ \blacksquare }$ 

**Thm** [Derivative and partials, ${ \mathbb{R} ^n \to \mathbb{R} ^m }$ case]:  

Consider ${ f : U (\subseteq \mathbb{R} ^n \text{ open}) \to \mathbb{R} ^m ,}$ ${ f = (f _1, \ldots, f _m) ^T }$ and ${ x \in U .}$ 

**i)** Say ${ f }$ is differentiable at ${ x .}$ Then all the partial derivatives ${ D _j f _i (x) }$ exist, and the derivative looks like 

$${ Df(x) = \begin{pmatrix} D _1 f _1 (x) &\cdots &D _n f _1 (x) \\ D _1 f _2 (x) &\cdots &D _n f _2 (x) \\ \vdots &\ddots &\vdots \\ D _1 f _m (x) &\cdots &D _n f _m (x) \end{pmatrix}  .   }$$ 

**ii)** Conversely, say all the partial derivatives ${ D _j f _i }$ exist in a neighbourhood of ${ x },$ and are continuous at ${ x .}$ Then ${ f }$ is differentiable at ${ x }$ (and as above, the derivative is the ${ m \times n }$ matrix with entries ${ (Df (x)) _{i, j} = D _j f _i (x) }$). 

**Pf**: **i)** Say ${ f }$ is differentiable at ${ x ,}$ that is ${ Df (x) }$ exists.    
Now (implicitly for ${ h }$ in a neighbourhood of ${ 0 }$) 

$${ \begin{align*} &f(x+h) = f(x) + D f (x) h + \lVert h \rVert \varphi(h) \text{ with } \\ &\varphi(0) = 0 \text{ and } \varphi \text{ continuous at } 0 . \end{align*}  }$$ 

Looking at the ${ i ^{\text{th}} }$ coordinate of above equation, 

$${ \begin{align*} &f _i (x + h) = f _i (x) + (i ^{\text{th}} \text{ row of } Df(x)) h + \lVert h \rVert \varphi _i (h) \\ &\text{with } \varphi _i (0) = 0 \text{ and } \varphi _i \text{ continuous at } 0 .  \end{align*}  }$$ 

So ${ f _i }$ is differentiable at ${ x }$ with derivative 

$${ D f _i (x) = (i ^{\text{th}} \text{ row of } Df (x)) .}$$ 

Applying the previous result to ${ f _i },$ we see all partials ${ D _j f _i (x) }$ exist and ${ D f _i (x) }$ looks like 

$${ (D _1 f _i (x), \ldots, D _n f _i (x)) =   Df _i (x) = (i ^{\text{th}} \text{ row of } Df (x)) , }$$ 

as needed. 

**ii)** Say all the partial derivatives ${ D _j f _i }$ exist in a neighbourhood of ${ x }$ and are continuous at ${ x . }$

Applying the previous result to ${ f _i ,}$ we see ${ (D _1 f _i (x), \ldots, D _n f _i (x)) }$ works as the derivative of ${ f _i }$ at ${ x }$ that is 

$${ \begin{align*} &f _i (x + h) = f _i (x) + (D _1 f _i (x), \ldots, D _n f _i (x)) \, h +  \lVert h \rVert \varphi _i (h) \\ &\text{with } \varphi _i (0) = 0 \text{ and } \varphi _i \text{ continuous at } 0. \end{align*}  }$$ 

Stacking these results and using ${ \varphi (h) = (\varphi _1 (h), \ldots, \varphi _m (h) ) ^T ,}$ we see

$${ \begin{align*} &f(x + h) = f(x) + \begin{pmatrix} D _1 f _1 (x) &\cdots &D _n f _1 (x) \\ \vdots &\ddots &\vdots \\ D _1 f _m (x) &\cdots &D _n f _m (x)  \end{pmatrix} h + \lVert h \rVert \varphi(h) \\ &\text{with } \varphi(0) = 0 \text{ and } \varphi \text{ continuous at } 0 . \end{align*}  }$$ 

So the ${ m \times n }$ matrix with ${ (i, j) ^{\text{th}} }$ entry ${  D _j f _i (x)  }$ works as the derivative of ${ f }$ at ${ x .}$  

###### 4. 

$${ \underline{\textbf{Integration of maps } f : [a, b] \to E} }$$ 

Recall if a map is uniformly continuous and into a complete space, the domain of definition can be [expanded to its closure](https://math.stackexchange.com/a/4326834/303300) while preserving continuity of the map (and uniquely so). The extended map also turns out to be uniformly continuous. 

**Thm** [Extension of continuous linear maps]:    
Consider normed vector spaces ${ E }$ and ${ F, }$ with ${ E }$ complete. Let ${ F _0 \subseteq F }$ be a subspace, and ${ \lambda : F _0  \to E }$ a continuous linear map.    
Then ${ \lambda }$ has an extension ${ \overline{\lambda} : \overline{F _0} \to E }$ which is continuous linear. Also ${ \overline{\lambda}  }$ is the unique continuous map ${ \overline{F _0} \to E }$ which extends ${ \lambda ,  }$ and ${ \left\lVert \overline{\lambda} \right\rVert = \lVert \lambda \rVert }.$    

**Pf**: Firstly ${ \overline{F _0} }$ is also a vector subspace of ${ F :}$ Let ${ x, y \in \overline{F _0} }$ and ${ \alpha, \beta \in \mathbb{R} .}$ We are to show ${ \alpha x + \beta y \in \overline{F _0 } .}$ There are sequences ${ (x _n), (y _n) \subseteq F _0 }$ with ${ \lVert x _n - x \rVert \to 0, }$ ${ \lVert y _n - y \rVert \to 0 .}$ Now ${ \lVert (\alpha x _n + \beta y _n) - (\alpha x + \beta y) \rVert \to 0 }$ with sequence ${ (\alpha x _n + \beta y _n) \subseteq F _0 .}$ So ${ \alpha x + \beta y \in \overline{F _0 } .}$ 

Let ${ x \in \overline{F _0} .}$ (Equivalently, there is a sequence ${ (x _n) \subseteq F _0 }$ with ${ \lVert x _n - x \rVert \to 0 }$). If we show that    

* For any sequence ${ (x _n) \subseteq F _0 }$ with ${ \lVert x _n - x \rVert \to 0 ,}$ the limit ${ \lim _{n \to \infty} \lambda (x _n) }$ exists    
* For any two sequences ${ (x _n), (y _n) \subseteq F _0 }$ with ${ \lVert x _n - x \rVert \to 0, }$ ${ \lVert y _n - x \rVert \to 0 ,}$ the limits ${ \lim _{n \to \infty} \lambda(x _n) = \lim _{n \to \infty} \lambda(y _n) , }$ 

the natural extension map 

$${ \overline{\lambda} : \overline{F _0} \to E,  }$$ 

$${ \overline{\lambda}(x) := \left(\begin{align*} &\lim _{n \to \infty} \lambda(x _n), \text{ where } (x _n) \text{ is any sequence } \\  &\text{with } (x _n) \subseteq F _0 \text{ and }  \lVert x _n - x \rVert \to 0  \end{align*} \right) }$$ 

is well defined. 

These two properties are proved as in the previous result, so we have ${ \overline{\lambda} .}$ We are to show ${ \overline{\lambda} \in L(\overline{F _0}, E) .}$ 

Linearity of ${ \overline{\lambda} }$ is clear:    
Let ${ x , y \in \overline{F _0} .}$ There are sequences  ${ (x _n) , (y _n) \subseteq F _0 }$ with ${ \lVert x _n - x \rVert \to 0, }$ ${ \lVert y _n - y \rVert \to 0. }$ Now for any scalars ${ \alpha, \beta \in \mathbb{R}, }$ 

$${ \begin{align*} \overline{\lambda}(\alpha x + \beta y ) &= \lim _{n \to \infty} \lambda (\alpha x _n + \beta y _n) \quad (\text{as } \alpha x _n + \beta y _n  \to \alpha x + \beta y) \\ &= \lim _{n \to \infty} \alpha \lambda(x _n) + \beta \lambda (y _n) \\  &= \alpha \overline{\lambda}(x) + \beta \overline{\lambda}(y) . \end{align*} }$$ 

By the previous result, ${ \overline{\lambda} }$ is uniformly continuous. So ${ \overline{\lambda} \in L(\overline{F _0}, E) .}$ 

Uniqueness of the continuous extension ${ \overline{F _0} \to E }$ is clear. (Say ${ \lambda ^{’} : \overline{F _0} \to E }$ is another continuous extension of ${ \lambda .}$ Let ${ x \in \overline{F _0} .}$ There is a sequence ${ (x _n) \subseteq F _0 }$ with ${ \lVert x _n - x  \rVert \to 0 .}$ Now ${ \lambda ^{’} (x) }$ ${ = \lim _{n \to \infty} \lambda ^{’} (x _n) }$ ${ = \lim _{n \to \infty} \lambda  (x _n) }$ ${ = \overline{\lambda} (x) ,}$ as needed).

It is left to show that ${ \left\lVert \overline{\lambda} \right\rVert =  \lVert \lambda \rVert .  }$ Since 

$${ \left\lVert \overline{\lambda} \right\rVert = \sup _{v \in \overline{F _0}, v \neq 0} \frac{\left\lVert \overline{\lambda}(v) \right\rVert}{\lVert v \rVert} \geq \sup _{v \in F _0, v \neq 0} \frac{\left\lVert \overline{\lambda}(v) \right \rVert}{\lVert v \rVert} = \lVert \lambda \rVert  }$$

is clear, so we are to show ${ \left\lVert \overline{\lambda} \right\rVert \leq \lVert \lambda \rVert .}$ 

Let ${ v \in \overline{F _0 } .}$ There is a sequence ${ (x _n) \subseteq F _0 }$ with ${ \lVert x _n - v \rVert \to 0 .}$ As ${ \lVert \lambda (x _n) \rVert \leq \lVert \lambda \rVert \lVert x _n \rVert }$ and ${ \lim _{n \to \infty} \lambda(x _n) = \overline{\lambda}(v), }$ taking ${ n \to \infty }$ gives ${ \left\lVert \overline{\lambda}(v) \right\rVert }$ ${ \leq \lVert \lambda \rVert \lVert v \rVert .}$ So ${ \sup _{v \neq 0} \frac{\lVert \overline{\lambda} (v) \rVert}{\lVert v \rVert} \leq \lVert \lambda \rVert }$ that is ${ \left\lVert \overline{\lambda} \right\rVert \leq \lVert \lambda \rVert , }$ as needed. ${ \blacksquare }$ 

Consider reals ${ a < b , }$ and a complete normed space ${ E .}$ Recall the space of bounded functions ${ B([a, b], E) }$ with sup norm is [complete](https://bvenkatakarthik.github.io/UnifConv).    

We say ${ f : [a , b] \to E }$ is a step map if there is a partition ${ \mathcal{P} : a = x _0 < x _1 < \ldots < x _n = b }$ of ${ [a , b] }$ and elements ${ c _1, \ldots, c _n \in E }$ such that ${ f(t) = c _i }$ on each interval ${ (x _{i-1}, x _i) .}$ 

The set ${ \text{St}([a, b], E) }$ of step maps from ${ [a, b] }$ to ${ E }$ is a vector subspace of ${ B([a, b], E).  }$ The closure ${ \overline{\text{St}}([a , b], E) }$ is written as 

$${ \text{Reg}([a, b], E) := \overline{\text{St}}([a , b], E) ,}$$ 

and its elements are called regulated maps. 

**Thm** [Characterising regulated maps]:    

Consider reals ${ a < b }$ and a complete normed space ${ E .}$ Now the space of regulated maps 

$${ \text{Reg}([a, b], E) = \left\lbrace f \in B([a, b], E) \, : \,  \begin{align*} &\lim _{t \to x ^{+}} f(t) \text{ exists } \forall x \in [a, b), \\ &\lim _{t \to x ^{-}} f(t) \text{ exists } \forall x \in (a,b]   \end{align*} \right\rbrace . }$$ 

**Pf**: [Ref: Coleman’s book] 

${ \underline{\subseteq} }$: Let ${ f }$ be a regulated map. There is a sequence of step maps ${ (f _n) }$ converging to ${ f .}$ 

Let ${ x \in [a, b) .}$ We will show ${ \lim _{t \to x ^{+}} f(t) }$ exists. (A similar argument will show existence of left sided limits.) 

We are to show 

$${ \text{To show: } \lim _{t \to x ^{+}} f(t) \text{ exists} }$$

that is 

$${ \text{To show: } \quad \begin{align*} &\exists \ell \in E \text{ such that } \forall \text{ sequence } (t _n) \text{ in } (x, b] \\ &\text{with } \lim _{n \to \infty} t _n = x \text{ we have } \lim _{n \to \infty} f(t _n) = \ell  \end{align*} }$$ 

 that is 

$${ \begin{align*} &\text{To show: } \\ &{\color{red}{1)}} \, \forall \text{ sequence } (t _n) \text{ in } (x, b] \text{ converging to } x \text{ we have } \\ &\text{existence of } \lim _{n \to \infty} f(t _n)  \\ &{\color{blue}{2)}} \, \forall \text{ sequences } (s _n), (t _n) \text{ in } (x, b] \text{ converging to } x \text{ we have } \\ &\lim _{n \to \infty} f(s _n) = \lim _{n \to \infty} f(t _n) .  \end{align*} }$$ 

We will show a uniform-continuity-like condition 

$${ \text{Will show: } \quad \begin{align*} &\forall \varepsilon > 0 \, \exists \delta > 0 \text{ such that } \\ & p, q \in (x, x + \delta) \implies \lVert f(p) - f(q) \rVert < \varepsilon. \end{align*} }$$ 

Note that this guarantees both ${ 1) }$ and ${ 2) }$ above.    

For ${ {\color{red}{1)}} }$: Consider a sequence ${ (t _n) }$ in ${ (x, b] }$ with ${ \vert t _n - x \vert \to 0  .}$ We are to show sequence ${ (f(t _n)) }$ is Cauchy.    
Let ${ \varepsilon > 0 .}$ Pick a ${ \delta > 0 }$ such that ${ p, q \in (x, x + \delta) \implies \lVert f(p) - f(q) \rVert < \varepsilon. }$ Pick an ${ N }$ such that ${ n \geq N \implies t _n \in (x, x + \delta) .}$ Now 

$${ \begin{align*} m, n \geq N &\implies t _m, t _n \in (x, x + \delta) \\ &\implies \lVert f(t _m) - f(t _n) \rVert < \varepsilon, \end{align*} }$$

as needed. ${ {\color{red}{\blacksquare}} }$   
For ${ {\color{blue}{2)}} }$: Consider sequences ${ (s _n), (t _n) }$ in ${ (x, b] }$ with ${ \vert s _n - x \vert \to 0, }$ ${ \vert t _n - x \vert \to 0 .}$ By ${ 1) , }$ say ${ \lim _{n \to \infty} f(s _n) = \ell _s }$ and ${ \lim _{n \to \infty} f(t _n) = \ell _t .}$ We are to show ${  \ell _s = \ell _t .}$ Since  

$${ \begin{align*} &\lVert \ell _s - \ell _t  \rVert \\ \leq \, &\underbrace{\lVert \ell _s  - f(s _n) \rVert} _{\to 0} + \lVert f(s _n) - f(t _n) \rVert + \underbrace{\lVert f(t _n) - \ell _t  \rVert} _{\to 0},  \end{align*} }$$ 

it suffices to show ${ \lVert f(s _n) - f(t _n) \rVert \to 0 .}$    
Let ${ \varepsilon > 0 .}$ Pick a ${ \delta > 0 }$ such that ${ p, q \in (x, x + \delta) \implies \lVert f(p) - f(q) \rVert < \varepsilon. }$ Pick an ${ N }$ such that ${ n \geq N \implies s _n, t _n \in (x, x + \delta) .}$ Now 

$${ \begin{align*} n \geq N &\implies s _n, t _n \in (x, x + \delta) \\ &\implies \lVert f(s _n) - f(t _n) \rVert < \varepsilon, \end{align*}  }$$ 

as needed. ${ {\color{blue}{\blacksquare}} }$ 

We will show the uniform-continuity-like condition used for proving ${ {\color{red}{1)}} }$ and ${ {\color{blue}{2)}} .}$ 

$${ \text{To show: } \quad \begin{align*} &\forall \varepsilon > 0 \, \exists \delta > 0 \text{ such that } \\ & p, q \in (x, x + \delta) \implies \lVert f(p) - f(q) \rVert < \varepsilon. \end{align*} }$$ 

Let ${ \varepsilon > 0 .}$ There is an ${ N }$ such that ${ \lVert f _N - f \rVert < \varepsilon .}$ As ${ f _N }$ is a step map, there is a ${ \delta > 0 }$ such that ${ f _N }$ is constant over ${ (x, x + \delta) .}$ Now for ${ p, q \in (x, x + \delta) , }$ 

$${ \begin{align*} &\lVert f(p) - f(q) \rVert \\ \leq \, &\underbrace{\lVert f(p) - f _N (p) \rVert} _{ < \varepsilon \text{ as } \lVert f _N - f \rVert < \varepsilon}  +  \underbrace{\cancel{\lVert f _N (p) - f _N (q) \rVert}} _{f _N \text{ constant over } (x , x + \delta) } + \underbrace{\lVert f _N (q) - f (q) \rVert} _{< \varepsilon \text{ as } \lVert f _N - f \rVert < \varepsilon} \\ < \, &2\varepsilon,     \end{align*} }$$ 

as needed. 

${ \underline{\supseteq} }$: Say ${ f \in B([a, b], E) }$ satisfies the left and right limit criteria. Let ${ \varepsilon > 0 .}$ We are to show there is a step map ${ \phi }$ with ${ \lVert f - \phi \rVert < \varepsilon .}$ 

It suffices to show 

$${ \text{To show: } \quad \begin{align*} &\exists \text{ a partition } \mathcal{P} = (y _i) \text{ of } [a, b] \text{ such that } \\ &p, q  \in (y _{i-1}, y _i) \implies \lVert f(p) - f(q) \rVert < \varepsilon,  \end{align*} }$$ 

because then for example the map ${ \phi }$ where 

$${ \phi (t) = \begin{cases} f\left( \frac{y _{i-1} + y _i}{2} \right) &\text{ for } t \in (y _{i-1}, y _i) \\ f(t)  &\text{ for } t \in \mathcal{P} \end{cases}   }$$

works. 

For each ${ x \in [a, b), }$ as ${ \lim _{t \to x ^{+} } f(t) }$ exists, there is a ${ \delta _x > 0 }$ such that 

$${ p, q \in (x, x + \delta _x) \implies \lVert f(p) - f(q) \rVert < \varepsilon. }$$

For each ${ x \in (a, b], }$ as ${ \lim _{t \to x ^{-}} f(t) }$ exists, there is a ${ \Delta _x > 0 }$ such that 

$${ p, q \in (x - \Delta _x, x) \implies \lVert f(p) - f(q) \rVert < \varepsilon . }$$ 

These give an open cover 

$${ [a, b] =  [a, a + \delta _a) \cup (b - \Delta _b, b] \cup  \bigcup _{x \in (a, b)} (x - \Delta _x, x + \delta _x).   }$$ 

The sets ${ [a, a + \delta _a) }$ and ${ (b - \Delta _b, b] }$ are open in the space ${ [a, b] .}$

As ${ [a, b] }$ is compact, the above open cover has a finite subcover. The finite subcover must have ${ [a, a + \delta _a) }$ and ${ (b - \Delta _b, b] }$: They are the only sets of the cover containing ${ a }$ and ${ b }$ respectively. 

So there is a finite subcover 
$${ [a, b] = [a, a + \delta _a) \cup (b - \Delta _b, b] \cup \bigcup _{i=1} ^{n} (x _i - \Delta _{x _i}, x _i +  \delta _{x _i})  }$$ 

with ${ x _1, \ldots, x _n \in (a, b) .}$ 

 Taking ${ \mathcal{P} }$ to be the partition produced by ordering the points 

 $${ \lbrace a , a + \delta _a; b - \Delta _b, b; x _1 - \Delta _{x _1}, x _1, x _1 + \delta _{x _1} ; \ldots; x _n - \Delta _{x _n}, x _n, x _n + \delta _{x _n}  \rbrace  }$$ 

 works: Say ${ \mathcal{P} = (y _i). }$ Now each interval ${ (y _{i-1}, y _{i}) }$ is contained in a set of the form ${ (x - \Delta _x, x) }$ or ${ (x, x + \delta _x)  }$ and hence satisfies 

 $${ p, q \in (y _{i-1}, y _i) \implies \lVert f(p) - f(q) \rVert < \varepsilon, }$$

as needed. ${ \blacksquare }$ 

A map ${ f : [a, b] \to E }$ is piecewise continuous if there is a partition ${ \mathcal{P} : a = x _0 < x _1 < \ldots < x _n = b }$ such that for each ${ i }$ the restriction ${ f   : (x _{i-1}, x _i) \to E }$ admits a continuous extension ${ f _i : [x _{i-1}, x _i] \to E .}$ 

By the above result, piecewise continuous maps ${ [a, b] \to E }$ into a complete space are regulated. 

We can now consider integrating step maps (This, along with linear extension theorem, will allow us to integrate regulated maps). 

**Def** [Integral of a step map wrt a partition]:    
Consider reals ${ a < b, }$ a complete normed space ${ E }$ and a step map ${ f : [a, b] \to E .}$    
Say ${ \mathcal{P} : a = x _0 < \ldots < x _n = b }$ is a partition wrt which ${ f }$ is a step map, and ${ f(t) = c _i }$ on each interval ${ t \in (x _{i-1}, x _i) .}$ Then the integral of ${ f }$ wrt ${ \mathcal{P} }$ is defined as 

$${ I _{\mathcal{P}} (f) := \sum _{i=1} ^n c _i (x _i - x _{i-1}) .  }$$ 

**Obs**: Consider reals ${ a < b, }$ a complete normed space ${ E }$ and a step map ${ f : [a, b] \to E .}$    
Say ${ f }$ is a step map wrt partition ${ \mathcal{P} : a = x _0 < \ldots < x _n = b ,}$ and ${ \hat{x} \in (a, b) .}$    
Then ${ f }$ is a step map wrt the partition described by points ${ \mathcal{P} \cup \lbrace \hat{x} \rbrace,  }$ and 

$${ I _{\mathcal{P} \cup \lbrace \hat{x} \rbrace} (f) = I _{\mathcal{P}} (f). }$$    

**Pf**: If ${ \hat{x} }$ is some ${ x _j  }$ then ${ \mathcal{P} \cup \lbrace \hat{x} \rbrace = \mathcal{P} }$ and we are done, so say ${ \hat{x} }$ lies in some ${ (x _{j-1}, x _j) .}$    
Say ${ f(t) = c _i }$ on each interval ${ t \in (x _{i-1}, x _i ) .}$ We see ${ f }$ is a step map wrt partition ${ \mathcal{P} \cup \lbrace \hat{x} \rbrace,  }$ and 

$${ \begin{align*} I _{\mathcal{P} \cup \lbrace \hat{x} \rbrace } (f) = &\sum _{i < j} c _i (x _i - x _{i-1}) + c _{j} (\hat{x} - x _{j-1}) + c _j (x _j - \hat{x}) \\ &\, + \sum _{i > j}  c _i (x _i - x _{i-1}) \\ = &\sum _{i} c _i (x _{i+1} - x _i) \\ = &I _{\mathcal{P}} (f)  \end{align*} }$$ 

as needed. 

**Obs**: Consider reals ${ a < b, }$ a complete normed space ${ E }$ and a step map ${ f : [a, b] \to E .}$    
If ${ f }$ is a step map wrt both partitions ${ \mathcal{P} }$ and ${ \mathcal{Q}, }$ then

$${ I _{\mathcal{P}} (f) = I _{\mathcal{Q}} (f) .}$$ 

**Pf**: Adding finitely many points to a partition ensures ${ f }$ is still a step map wrt new partition and integral of ${ f }$ wrt new partition is same as the old one.    
So ${ f }$ is a step map wrt partition described by points ${ \mathcal{P} \cup \mathcal{Q}, }$ and 

$${ I _{\mathcal{P}} (f) = I _{\mathcal{P} \cup \mathcal{Q}} (f) = I _{\mathcal{Q}} (
f) }$$ 

as needed. 

**Def** [Integral of a step map]:    
Consider reals ${ a < b, }$ a complete normed space ${ E }$ and a step map ${ f : [a, b] \to E .}$    
By the above observation, we can define the integral of ${ f }$ as 

$${ I(f) := I _{\mathcal{P}} (f) ,}$$ 

where ${ \mathcal{P} }$ is any partition wrt which ${ f }$ is a step map.   

**Obs** [Linearity of integral for step maps]:    
Consider reals ${ a < b }$ and a complete normed space ${ E .}$ The integration operation on step maps 

$${ I : \text{St}([a, b], E) \longrightarrow E }$$ 

is continuous linear with ${ \lVert I(f) \rVert \leq (b-a) \lVert f \rVert. }$ 

**Pf**: Say ${ f , g : [a, b] \to E }$ are step maps wrt partitions ${ \mathcal{P} _f, \mathcal{P} _g }$ respectively, and ${ \alpha, \beta \in \mathbb{R} .}$    
Now ${ \alpha f + \beta g , f, g }$ are step maps wrt the partition described by points ${ \mathcal{P} _f \cup \mathcal{P} _g .}$ Say the partition described by points ${ \mathcal{P} _f \cup \mathcal{P} _g }$ is ${ a = x _0 < \ldots < x _n = b , }$ and ${ f(t) = c _i, g(t) = d _i }$ on each interval ${ t \in (x _{i-1}, x _i) .}$ This gives 

$${ \begin{align*} I(\alpha f + \beta g) = &\sum _{i=1} ^{n} (\alpha c _i + \beta d _i) (x _{i} - x _{i-1}) \\ = &\alpha \sum _{i=1} ^{n} c _i (x _i - x _{i-1}) + \beta \sum _{i=1} ^{n} d _i (x _i - x _{i-1}) \\ =  &\alpha I(f) + \beta I(g), \end{align*} }$$ 

so ${ I }$ is linear. Further 

$${ \begin{align*} \lVert I(f) \rVert \leq &\sum _{i=1} ^{n} \lVert c _i \rVert  (x _i - x _{i-1}) \\ \leq &\, \lVert f \rVert \sum _{i=1} ^{n} (x _i - x _{i-1}) \\ = &\, \lVert f \rVert (b-a)  ,  \end{align*} }$$ 

so especially ${ I }$ is continuous. ${ \blacksquare }$ 

Consider reals ${ a < b }$ and a complete normed space ${ E .}$ By linear extension theorem, we can extend the above map to a continuous linear map 

$${ I : \overline{\text{St}}([a, b], E)  \longrightarrow E,  }$$ 

$${ I(f) := \left( \begin{align*} &\lim _{n \to \infty} I(f _n), \text{ where } (f _n) \text{ is any sequence} \\  &\text{in } \text{St}([a, b], E) \text{ with }  \lVert f _n - f \rVert \to 0  \end{align*} \right) . }$$ 

We write ${ I(f) }$ as 

$${ I(f) = \int _{a} ^{b} f .}$$ 

**Obs**: Consider reals ${ a < b ,}$ a complete normed space ${ E }$ and a step map ${ f : [a, b] \to E .}$    
If ${ c \in [a, b], }$ then both ${ f \vert _{[a, c]} }$ and ${ f \vert _{[c, b]} }$ are step maps and 

$${ I(f \vert _{[a, b]}) = I(f \vert _{[a, c]}) + I(f \vert _{[c, b]}) . }$$    

**Pf**: Say ${ f : [a, b] \to E }$ is a step map wrt partition ${ \mathcal{P} : a = x _0 < \ldots < x _n = b ,}$ and ${ c \in [a, b] .}$ If ${ c }$ is some ${ x _j }$ the result is clear, so say ${ c }$ lies in some ${ (x _{j-1}, x _j) .}$ 

Say ${ f(t) = c _i }$ on each interval ${ t \in (x _{i-1}, x _i) .}$ We see ${ f \vert _{[a, b]}, f \vert _{[a, c]} , f \vert _{[c, b]} }$ are step maps wrt partition ${ \mathcal{P} \cup \lbrace c \rbrace }$ restricted to ${ [a, b], [a, c], [c, b] }$ respectively. Also 

$${ \begin{align*} I(f \vert _{[a, b]}) = &\sum _{i=1} ^{n} c _i (x _i - x _{i-1}) \\ = &\sum _{i < j} c _i (x _i - x _{i-1}) +  c _j (c - x _{j-1}) \\ &+ c _j (x _j - c) + \sum _{i > j} c _i (x _i - x _{i-1}) \\ = &I(f \vert _{[a, c]}) + I(f \vert _{[c, b]}) \end{align*} }$$ 

as needed. 

**Obs** [Monotonicity of integral for step maps]:    
Consider reals ${ a < b , }$ and step maps ${ f, g : [a, b] \to \mathbb{R} .}$ Then 

$${ f \leq g \implies I(f) \leq I(g). }$$ 

**Pf**: Say ${ f, g : [a, b] \to \mathbb{R} }$ are step maps wrt partitions ${ \mathcal{P} _f, \mathcal{P} _g }$ respectively. Now both ${ f, g }$ are step maps wrt the partition defined by points ${ \mathcal{P} _f \cup \mathcal{P} _g .}$ Say the partition described by points ${ \mathcal{P} _f \cup \mathcal{P} _g }$ is ${ a = x _0 < \ldots < x _n = b , }$ and ${ f(t) = c _i, g(t) = d _i }$ on each interval ${ t \in (x _{i-1}, x _i) .}$

Let ${ f \leq g . }$ So each ${ c _i \leq d _i .}$ Then 

$${ \begin{align*} I(f) = &\sum _{i=1} ^{n} c _i (x _i - x _{i-1}) \\ \leq &\sum _{i=1} ^{n} d _i (x _i - x _{i-1}) \\ = &\, I(g) ,  \end{align*} }$$ 

as needed. 

**Def**: Consider reals ${ \alpha < \beta , }$ a complete normed space ${ E }$ and a regulated map ${ f : [\alpha, \beta] \to E .}$    
For ${ a \leq b }$ in ${ [\alpha, \beta],  }$  note ${ f \vert _{[a, b]} }$ is regulated too. (If step maps ${ f _n }$ are uniformly convergent to ${ f ,}$ the step maps ${ f _n \vert _{[a, b]} }$ are uniformly convergent to ${ f \vert _{[a, b]} }$). We define 

$${ \int _{b} ^{a} f := - \int _{a} ^{b} f . }$$  

**Thm**: Consider reals ${ \alpha < \beta , }$ a complete normed space ${ E }$ and a regulated map ${ f : [\alpha, \beta] \to E .}$    
Then for ${a, b, c \in [\alpha, \beta], }$ 

$${ \int _{a} ^{b} f = \int _{a} ^{c} f +  \int _{c} ^{b} f . }$$ 

**Pf**:  As ${ f }$ is regulated, there are step maps ${ f _n : [\alpha, \beta] \to E }$ uniformly converging to ${ f : [\alpha, \beta] \to E .}$ 

Consider first the case ${ a \leq c \leq b .}$ So step maps ${ f _n \vert _{[a, b]}, }$ ${ f _n \vert _{[a, c]}, }$ ${ f _n \vert _{[c, b]}   }$ are uniformly convergent to ${ f \vert _{[a, b]} , }$ ${ f \vert _{[a, c]} , }$ ${ f \vert _{[c, b]} }$ respectively. We are to show ${ \int _{a} ^{b} f = \int _{a} ^{c} f + \int _{c} ^{b} f }$ that is ${ \lim I(f _n \vert _{[a, b]}) =  \lim I(f _n \vert _{[a, c]}) + \lim I(f _n \vert _{[c, b]}),  }$ which is true. 

Consider the case ${ a \leq b \leq c .}$ We are to show ${ \int _{a} ^{b} f = \int _{a} ^{c} f + \int _{c} ^{b} f }$ that is ${ \lim I(f _n \vert _{[a, b]}) = \lim I(f _n \vert _{[a, c]}) + (-\lim I(f _n \vert _{[b, c]}) ),  }$ which is true. 

One can verify the truth of ${ \int _{a} ^{b} f = \int _{a} ^{c} f + \int _{c} ^{b} f }$ for the remaining ${ 3! - 2 = 4 }$ orderings of ${ a, b, c \in [\alpha, \beta] }$ similarly. 

**Thm** [Monotonicity of integral]:    
Consider reals ${ a < b , }$ and regulated maps ${ f, g : [a, b] \to \mathbb{R} .}$ Now 

$${ f \leq g \implies \int _{a} ^{b} f  \leq \int _{a} ^{b} g .  }$$ 

**Pf**: As ${ f, g }$ are regulated, so is ${ g - f .}$ The proof of characterisation of ${ \text{Reg}([a, b], E) }$ gives, for every ${ \varepsilon > 0 }$ a specific step map ${ \phi _{\varepsilon} }$ such that ${ \lVert (g - f) - \phi _{\varepsilon} \rVert < \varepsilon .}$ 

Let ${ g - f \geq 0 . }$ With this, the considered step maps ${ \phi _{\varepsilon} }$ are also ${ \geq 0 .}$    

So the step maps ${ \phi _{\frac{1}{n}} }$ are ${ \geq 0 }$ and uniformly convergent to ${ g - f ,}$ giving 

$${ \int _{a} ^{b} (g-f) = \lim _{n \to \infty} I\left(\phi _{\frac{1}{n}}\right) \geq 0   }$$ 

as needed. 

**Obs** [Uniform limit and Integral]:    
Consider reals ${ a < b, }$ a complete normed space ${ E ,}$ and a sequence of regulated maps ${ f _n : [a, b] \to E }$ with ${ \lVert f _n - f \rVert \to 0 }$ for some ${ f : [a, b] \to E .}$    
Uniform limit of bounded maps [is bounded](https://bvenkatakarthik.github.io/UnifConv), so ${ f }$ is in ${ B([a, b], E) .}$ As ${ \text{Reg}([a, b], E) }$ is closed in ${ B([a, b], E), }$ the limit ${ f  }$ is in ${ \text{Reg}([a, b], E) . }$ As 

$${ \int _a ^b  : \text{Reg}([a, b] , E) \longrightarrow E  }$$ 

is continuous linear, 

$${ \int _a ^b f _n \longrightarrow \int _{a} ^{b} f .  }$$ 

So uniform limit of regulated maps is regulated, and here integral of limit is limit of integrals. 

**Obs**: 

**Thm** [Bound for integral]:    
Consider reals ${ \alpha < \beta , }$ a complete normed space ${ E }$ and a regulated map ${ f : [\alpha, \beta] \to E . }$    
Then for ${ x, c \in [\alpha, \beta], }$ 

$${ \left\lVert \int _{c} ^{x} f \right\rVert \leq \vert x - c \vert \lVert f \rVert .  }$$ 

For ${ c \in [\alpha, \beta] ,}$ the map ${ F: [\alpha, \beta] \to E , }$ ${ F(t) =  \int _{c} ^{t} f }$ is uniformly continuous. 

**Pf**: As ${ f }$ is regulated, there is a sequence of step maps ${ f _n : [\alpha, \beta] \to E }$ uniformly converging to ${ f : [\alpha, \beta] \to E .}$    
**i**) It suffices to show the inequality for ${ c \leq x }$ case. Note step maps ${ f _n \vert _{[c, x]} }$ uniformly converge to ${ f \vert _{[c, x]} .}$ Each step map ${ f _n \vert _{[c, x]} }$ satisfies 

$${ \begin{align*}  \lVert I(f _n \vert _{[c, x]}) \rVert \leq &(x-c) \lVert f _n \vert _{[c, x]} \rVert \\ \leq &(x - c) \lVert f _n \rVert,  \end{align*} }$$ 

so limit ${ n \to \infty }$ gives 

$${ \left\lVert \int _{c} ^{x} f \right\rVert \leq  (x - c) \lVert f \rVert  }$$ 

as needed.    
**ii**) The map ${ F: [\alpha, \beta] \to E , }$ ${ F(t) =  \int _{c} ^{t} f }$ is uniformly continuous because for all ${ x, y \in [\alpha, \beta], }$ 

$${  \lVert F(x) - F(y) \rVert = \left\lVert \int _{y} ^{x} f \right\rVert \leq \vert x - y \vert \lVert f \rVert .  }$$ 

**Thm**: A map ${ f : [a, b] \to \mathbb{R} ^k , }$ ${ f = (f _1, \ldots, f _k) ^T }$ is regulated if and only if each ${ f _i }$ is regulated. In this case, 

$${ \int _a ^b f = \left( \int _a ^b f _1, \ldots, \int _a ^b f _k  \right) .}$$ 

**Pf**: ${ \underline{\Rightarrow} }$ Say ${ f : [a, b] \to \mathbb{R} ^k , }$ ${ f = (f _1, \ldots, f _k) ^T }$ is regulated. So there are step maps ${ s _n : [a, b] \to \mathbb{R} ^k, }$ ${ s _n  = ((s _n) _1, \ldots, (s _n) _k) ^T }$ with ${ \lVert s _n - f \rVert \to 0 .}$    
Now for each ${ i = 1, \ldots, k, }$ 

$${ \begin{align*} \lVert (s _n ) _i - f _i \rVert = &\sup _{x \in [a, b]}  \vert (s _n) _i (x) - f _i (x) \vert \\ \leq &\sup _{x \in [a, b]} \sqrt{\sum _{j=1} ^{k} \vert (s _n) _j (x) - f _j (x) \vert ^2} \\ = &\lVert s _n - f \rVert \to 0 \end{align*}  }$$ 

with ${ (s _n) _i  }$ step maps. Especially each ${ f _i }$ is regulated.   

Note if ${ s _n : [a, b] \to \mathbb{R} ^k }$ is step map wrt partition ${ \mathcal{P} _n ,}$ then ${ (s _n) _1, \ldots, (s _n) _k : [a, b] \to \mathbb{R}  }$ are step maps wrt same partition, and 

$${ I _{\mathcal{P} _n} (s _n) = \left( I _{\mathcal{P} _n} ((s _n) _1), \ldots, I _{\mathcal{P} _n} ((s _n) _k ) \right) }$$ 

that is 

$${ I  (s _n) = \left( I ((s _n) _1), \ldots, I ((s _n) _k ) \right) .  }$$ 

Since ${ \lVert s _n - f \rVert \to 0 }$ and each ${ \lVert (s _n) _i - f _i \rVert \to 0, }$ taking ${ n \to \infty }$ gives 

$${   \int _a ^b f = \left( \int _a ^b f _1, \ldots, \int _a ^b f _k  \right) .}$$ 

${ \underline{\Leftarrow} }$: Say ${ f : [a, b] \to \mathbb{R} ^k , }$ ${ f = (f _1, \ldots, f _k) ^T }$ is such that each ${ f _i }$ is regulated. We are to show ${ f }$ is regulated.    
For each ${ f _i }$ there are step maps ${ (s _i) _n : [a, b] \to \mathbb{R} }$ with ${ \lVert (s _i) _n - f _i \rVert \to 0 .}$    
If ${ (s _1) _n, \ldots, (s _k) _n : [a, b] \to \mathbb{R} }$ are step maps wrt partitions ${ \mathcal{P} _{1, n}, \ldots, \mathcal{P} _{k,n} }$ then 

$${ S _n := ((s _1) _n, \ldots, (s _k) _n) }$$

is a step map wrt partition described by points ${ \mathcal{P} _n := \mathcal{P} _{1, n} \cup \ldots \cup \mathcal{P} _{k, n} .}$ Further, 

$${ \begin{align*} \lVert S _n - f \rVert = &\sup _{x \in [a, b]} \sqrt{\sum _{i=1} ^{k} [(s _i) _n (x) - f _i (x)] ^2  } \\ \leq &\sqrt{\sum _{i=1} ^{k} \lVert (s _i) _n (x) - f _i \rVert ^2 } \to 0 \end{align*}   }$$ 

so ${ f }$ is regulated, as needed. 

**Thm** [Integral as antiderivative]:    
Consider reals ${ a < b ,}$ a complete normed space ${ E }$ and a regulated map ${ f : [a, b] \to E .}$ Let 

$${ F : [a, b] \to E, \quad F(x) := \int _a ^x f .}$$ 

If ${ f }$ is continuous at ${ c \in [a, b] , }$ then 

$${  F ^{’} (c) = f(c) . }$$ 

> For ${ E = \mathbb{R} }$ it is intuitively clear: Area ${ F(c + h) \approx F(c) + f(c) h . }$ 

**Pf**: Say ${ f }$ is continuous at ${ c \in [a, b] .}$    
For ${ h }$ such that ${ h \neq 0, }$ ${ c + h \in [a, b] }$ we have 

$${ \begin{align*} \frac{F(c+h) - F(c)}{h} - f(c) = &\frac{1}{h} \left(\int _{c} ^{c+h} f \right) - f(c) \\ = &\frac{1}{h} \int _{c} ^{c+h} (f - f(c)).   \end{align*} }$$ 

Let ${ \varepsilon > 0 .}$ By continuity at ${ c,}$ there is a ${ \delta > 0 }$ such that 

$${ x \in [a, b], \,  \vert x - c \vert < \delta \implies \lVert f(x) - f(c) \rVert < \varepsilon .}$$ 

Recall segment notation ${ [[ \alpha, \beta ]] := \lbrace \alpha + t(\beta - \alpha) : t \in [0, 1] \rbrace .}$ Now 

$${ \begin{align*} \left\lVert  \frac{F(c+h) - F(c)}{h} - f(c) \right\rVert = &\, \frac{1}{\vert h \vert}  \left\lVert \int _{c} ^{c+h} (f - f(c)) \right\rVert \\ \leq &\sup _{x \in [[c, c+h]]} \lVert f(x) - f(c) \rVert \\ {\color{blue}{\leq}} &\, \varepsilon \end{align*} }$$ 

for ${ h }$ such that ${ h \neq 0, }$ ${ c + h \in [a, b] }$ and ${ {\color{blue}{\vert h \vert < \delta}} . }$ So 

$${ \frac{F(c+h) - F(c)}{h} \longrightarrow f(c) }$$ 

as ${ c + h \in [a, b], }$ ${ h \to 0 .}$ ${ \blacksquare }$ 

**Thm** [Integral as the only antiderivative, upto constants]:    
Consider reals ${ a < b ,}$ a complete normed space ${ E }$ and a continuous map ${ f : [a, b] \to E .}$ Let 

$${ F : [a, b] \to E, \quad F(x) := \int _a ^x f .}$$  

By the above observations, ${ F : [a, b] \to E }$ is a continuous antiderivative of ${ f , }$ that is 

$${ \left\lbrace \begin{align*} &F \text{ is continuous on } [a, b]; \\  &D F  (x) = f(x) \text{ for all } x \in (a, b) \end{align*} \right\rbrace .}$$ 

Say ${ \hat{F} : [a, b] \to E }$ is another continuous antiderivative of ${ f . }$ Then ${ F, \hat{F} : [a, b] \to E }$ differ by a constant. 

> So ${ \int _{a} ^{x} f = \hat{F}(x) + c   ,}$ and setting ${ x =  a }$ gives 
> 
> $${ \int _{a} ^{x} f = \hat{F}(x) - \hat{F}(a) .}$$ 
> 
> Especially 
> 
> $${ \int _a ^b f = \hat{F}(b) - \hat{F}(a). }$$ 

**Pf**: We have ${ D (F - \hat{F})  (x) = 0 }$ for all ${ x \in (a, b) .}$ By the lemma below, ${ F - \hat{F} }$ is constant on ${ (a, b) .}$  But ${ F - \hat{F} }$ is continuous on ${ [a, b], }$ so it is constant on ${ [a, b] .  }$ 

**Lem**: Consider reals ${ a < b , }$ a complete normed space ${ E }$ and a map ${ f : [a, b] \to E .}$    
If ${ Df(t) = 0 }$ for all ${ t \in (a, b) , }$ then ${ f }$ is constant on ${ (a, b) .}$    

**Pf**: Consider points ${ \alpha < \beta }$ in ${ (a, b) .}$ We will show ${ f(\alpha) = f(\beta) .}$    

Let ${ \varepsilon > 0 .}$ For every ${ t \in [\alpha, \beta] }$ there is a ${ \delta _t > 0 }$ such that 

$${ \vert h \vert  < \delta _t \implies \lVert f(t + h) - f(t) - \cancel{Df(t) h} \rVert  \leq \varepsilon \vert h \vert }$$ 

that is 

$${ x \in (t - \delta _t, t + \delta _t)  \implies \lVert f(x) - f(t) \rVert \leq \varepsilon \vert x - t \vert .}$$ 

This is local information for every ${ t \in [\alpha, \beta], }$ but compactness lets us work with it. 

Consider the open cover 

$${ [\alpha, \beta] \subseteq \bigcup _{t \in [\alpha, \beta]} (t - \delta _t, t + \delta _t).  }$$ 

By compactness of ${ [\alpha, \beta] , }$ it has a finite subcover 

$${ [\alpha, \beta] \subseteq \bigcup _{i=1} ^{n} (t _i - \delta _{t _i}, t _i + \delta _{t _i})  .}$$ 

WLOG no element of the cover is contained in another element of the cover (because if so, the element contained can be removed). Order the centers ${ t _i }$ so that 

$${ \alpha \leq t _1 < \ldots < t _n \leq \beta .}$$ 
 
Note if some ${ (t _i - \delta _i, t _i + \delta _i) }$ and ${ (t _{i+1} -  \delta _{i+1}, t _{i+1} + \delta _{i+1}) }$ do not intersect, that is ${ t _i + \delta _i <  t _{i+1} -  \delta _{i+1} , }$ then the segment ${ [ t _i + \delta _i, t _{i+1} -  \delta _{i+1}  ] }$ doesnt intersect any of ${ (t _1 - \delta _1, t _1 + \delta _1), \ldots, (t _n - \delta _n, t _n + \delta _n) , }$ a contradiction. 

So for each ${ i = 1, \ldots, n -1  }$ we can pick an ${ {\color{blue}{x _i}}  \in (t _{i}, t _{i+1}) }$ in the intersection of ${ (t _i - \delta _i, t _i + \delta _i) }$ and ${ (t _{i+1} -  \delta _{i+1}, t _{i+1} + \delta _{i+1}) . }$ 

This gives 

$${ \alpha \leq t _1 < {\color{blue}{x _1}} < t _2 < \ldots < t _{n-1} < {\color{blue}{x _{n-1}}} < t _n \leq \beta  }$$ 

with each ${ \lVert f({\color{blue}{x _i}}) - f(t _i) \rVert \leq \varepsilon ({\color{blue}{x _i}} - t _i) }$ and ${ \lVert f(t _{i+1}) - f({\color{blue}{x _i}}) \rVert \leq \varepsilon (t _{i+1} - {\color{blue}{x _i}}) .}$ 

Now each term 

$${ \begin{align*} \lVert f(t _{i+1}) - f(t _i) \rVert \leq &\, \lVert f(t _{i+1}) - f({\color{blue}{x _i}}) \rVert + \lVert f({\color{blue}{x _i}}) - f(t _i)  \rVert \\ \leq &\, \varepsilon (t _{i+1} - {\color{blue}{x _i}}) + \varepsilon ({\color{blue}{x _i}} - t _i) \\ = &\, \varepsilon (t _{i+1} - t _i),   \end{align*} }$$ 

giving 

$${ \begin{align*} &\lVert f(\beta) - f(\alpha) \rVert \\ \leq &\, \lVert f(\beta) - f(t _n) \rVert + \sum _{i=1} ^{n-1} \lVert f(t _{i+1}) - f(t _i) \rVert + \lVert f(t _1) - f(\alpha) \rVert \\ \leq &\, \varepsilon(\beta - t _n) + \sum _{i=1} ^{n-1} \varepsilon (t _{i+1} - t _i) +  \varepsilon (t _1 - \alpha) \\ = &\, \varepsilon (\beta - \alpha).   \end{align*}  }$$ 

As ${ \varepsilon > 0 }$ was arbitrary, ${ f(\beta) = f(\alpha) }$ as needed. ${ \blacksquare }$ 

**Thm** [Integrating maps ${ [a, b] \to L(E, F) }$]:    
Consider reals ${ a < b , }$ and normed spaces ${ E, F }$ with ${ F }$ complete. (So ${ L(E, F) }$ is complete). Consider a continuous map ${ \alpha : [a, b] \to L(E, F) .}$ Now 

$${ \int _a ^b \alpha(t) \, dt  \quad \text{ in } L(E, F)   }$$ 

acts as  

$${ \left( \int _a ^b \alpha (t) \, dt \right) y = \int _a ^b \alpha(t) y   \, dt    }$$ 

for all ${ y \in E . }$    
**Pf**: Fix a ${ y \in E . }$ This gives a continuous linear map 

$${ T : L(E, F) \to F , \quad \lambda \mapsto \lambda (y) . }$$ 

Linearity is clear, and continuity is because 

$${ \sup _{\lambda \neq 0} \frac{\lVert T(\lambda) \rVert}{\lVert \lambda \rVert} = \sup _{\lambda \neq 0} \frac{\lVert \lambda(y) \rVert}{\lVert \lambda \rVert} \leq \lVert y \rVert . }$$ 

We have continuous maps 

$${ [a, b] \overset{\alpha}{\longrightarrow} L(E, F) \overset{T}{\longrightarrow} F  ,   }$$ 

$${ t \longmapsto \alpha(t) \longmapsto \alpha(t) y .}$$ 

We are to show 

$${ \text{To show: } \int _a ^b (T \circ \alpha) (t) \, dt = T \circ \left( \int _a ^b \alpha(t) \, dt   \right) .   }$$ 

There is a sequence of step maps ${ s _n : [a, b] \to L(E, F) }$ with ${ \lVert s _n - \alpha \rVert \to 0 .}$ Now ${ T \circ s _n : [a, b] \to F }$ are also step maps, and 

$${ \begin{align*} \lVert T\circ s _n - T \circ \alpha \rVert = &\, \sup _{t \in [a, b]} \lVert s _n (t) y - \alpha(t) y  \rVert \\ \leq &\, \lVert s _n - \alpha \rVert \lVert y \rVert \to 0 .  \end{align*}  }$$ 

It suffices to show 

$${ \text{Suffices to show: } \int _a ^b (T \circ s _n) (t) \, dt = T \circ \left( \int _a ^b s _n (t) \, dt \right) ,  }$$ 

because then letting ${ n \to \infty }$ gives ${ \int (T \circ \alpha) = T \circ \int \alpha  .}$ 

Say ${ s _n : [a, b] \to L(E, F) }$ is a step map wrt partition ${ \mathcal{P} _n : a = x _0 < \ldots < x _N = b ,}$ and ${ s _n (t) = c _i }$ on each interval ${ t \in (x _{i-1}, x _i) .}$ 

Now ${ T \circ s _n }$ is a step map wrt same partition, and 

$${ \begin{align*} \int _a ^b (T \circ s _n) (t) \, dt = &\sum _{i=1} ^{N} T(c _i) (x _i - x _{i-1}) \\ = &\, \sum _{i=1} ^{N} c _i y \, (x _i - x _{i-1}) \\ = &\, \left( \sum _{i=1} ^{N} c _i (x _i - x _{i-1})  \right) \, y \\ = &\, \left( \int _a ^b s _n (t) \, dt \right) \, y \\ = &\, T \circ \left( \int _a ^b s _n (t) \, dt \right) ,     \end{align*}  }$$ 

as needed. ${ \blacksquare }$ 

**Thm** [Integration by parts]:    
Let ${ E, F, G }$ be complete normed spaces, and 

$${ \bullet : E \times F \to G }$$

a continuous bilinear map.    
Let ${ I \subseteq \mathbb{R} }$ be an open interval, ${ a, b \in I , }$ and 

$${ f : I \to E, \quad g : I \to F  }$$ 

be ${ C ^1 }$ maps. Then 

$${ \begin{align*} &\int _a ^b f(t) \bullet D g (t) \, dt \\ = &\, f(b) \bullet g(b) - f(a) \bullet g(a) - \int _a ^b Df(t) \bullet g(t) \, dt \end{align*} }$$

**Pf**: By product rule, 

$${ D(f \bullet g)(t) = Df(t) \bullet g(t) + f(t) \bullet Dg(t) .  }$$ 

Integrating this gives the required identity.


**Eg**: Consider the map 

$${ A : [0, \pi] \longrightarrow (L(\mathbb{R} ^2, \mathbb{R} ^2), \lVert \ldots \rVert _{\text{op}}) ,    }$$ 

$${ t \longmapsto \begin{pmatrix} \cos(t) &t \\ \sin(t) &t ^2 \end{pmatrix} .  }$$ 

We can study ${ A ^{’} (t) }$ and ${ \int _0 ^\pi A(t) \, dt .}$ 

The map 

$${ A _F  : [0, \pi] \longrightarrow (L(\mathbb{R} ^2, \mathbb{R} ^2), \lVert \ldots \rVert _{F}) \cong (\mathbb{R} ^4, \lVert \cdots \rVert _u)  , }$$ 

$${ t \longmapsto \begin{pmatrix} \cos(t) &t \\ \sin(t) &t ^2 \end{pmatrix} }$$ 

can be readily differentiated and integrated due to the results on component wise differentiation and integration of  maps ${ [a, b] \to \mathbb{R} ^k :}$ 

$${ \begin{align*} &A _F ^{’} (t) = \begin{pmatrix} -\sin(t) &1 \\ \cos(t) &2t \end{pmatrix} \text{ for } t \in (a, b) , \\ &\int _0 ^\pi A _F (t) \, dt =  \begin{pmatrix} 0 &\pi ^2 /2 \\ 2 &\pi ^3 /3  \end{pmatrix} .  \end{align*} }$$ 

But ${ \lVert \cdots \rVert _{\text{op}} }$ and ${ \lVert \cdots \rVert _F }$ are equivalent norms on ${ L(\mathbb{R} ^2, \mathbb{R} ^2) .}$ 

Let ${ t \in (a, b) .}$ As 

$${ \begin{align*} &\frac{\lVert A(t+h) - A(t) - A _F ^{’}(t) h \rVert _{\text{op}} }{\vert h \vert} \\ \leq &\, K \frac{\lVert A(t+h) - A(t) - A _F ^{’}(t) h \rVert _{F} }{\vert h \vert} \to 0  \end{align*}  }$$ 

as ${ h \to 0 , }$ we see derivative 

$${ A ^{’} (t) = A _F ^{’} (t) = \begin{pmatrix} -\sin(t) &1 \\ \cos(t) &2t \end{pmatrix} \text{ for } t \in (a, b)  .}$$ 

There are step maps ${ s _n : [0, \pi] \to (L(\mathbb{R} ^2, \mathbb{R} ^2), \lVert \cdots \rVert _F) }$ with ${  \sup _{t \in [0, \pi]} \lVert s _n (t) - A (t) \rVert _F   \to 0  }$ and 

$${ \left\lVert \int _0 ^\pi s _n (t) \, dt - \int _0 ^\pi A _F (t) \, dt \right\rVert _F \longrightarrow 0 .  }$$ 

Due to equivalence of norms, ${ \sup _{t \in [0, \pi]} \lVert s _n (t) - A (t) \rVert _{\text{op}} \to 0 }$ and 

$${ \left\lVert \int _0 ^\pi s _n (t) \, dt - \int _0 ^\pi A _F (t) \, dt  \right\rVert _{\text{op}}   \to 0 .   }$$ 

So integral 

$${ \int _0 ^{\pi} A(t) \, dt = \int _0 ^{\pi} A _F (t) \, dt = \begin{pmatrix} 0 &\pi ^2 /2 \\ 2 &\pi ^3 /3  \end{pmatrix} .    }$$ 

###### 5. 

$${ \underline{\textbf{Mean value theorem}} }$$ 

**Def** [${ C ^1 }$ maps]: Let ${ E, F }$ be complete normed spaces, and ${ f : U (\subseteq E \text{ open}) \to F .}$    
We say ${ f }$ is ${ C ^1 }$ on ${ U }$ if it is differentiable on ${ U }$ and the derivative 

$${ Df : U \longrightarrow L(E, F)  }$$ 

is continuous. 

**Obs** [${ C ^1 }$ maps ${ \mathbb{R} ^n \to \mathbb{R} ^m }$ and partials]:    
Consider ${ f : U (\subseteq \mathbb{R} ^n \text{ open}) \to \mathbb{R} ^m .}$    
Now ${ f : U \to \mathbb{R} ^m  }$ is ${ C ^1 }$ if and only if all partials ${ D _j f _i : U \to \mathbb{R} }$ exist and are continuous.   

**Pf**: ${ \underline{\Rightarrow} }$ Say ${ f : U \to \mathbb{R} ^m }$ is ${ C ^1 . }$ So ${ Df : U \to L(\mathbb{R} ^n, \mathbb{R} ^m ) }$ exists as a continuous map.    
By previous observation (on differentiating maps ${ \mathbb{R} ^n \to \mathbb{R} ^m }$), for every ${ x \in U }$ all partials ${ D _j f _i (x) }$ exist and ${ Df(x) }$ looks like  

$${ Df(x) = \begin{pmatrix} D _1 f _1 (x) &\cdots &D _n f _1 (x) \\ \vdots &\ddots &\vdots \\ D _1 f _m (x) &\cdots &D _n f _m (x)  \end{pmatrix} .   }$$    
As ${ U \to (L(\mathbb{R} ^n, \mathbb{R} ^m), \lVert \cdots \rVert _{\text{op}}) ,}$   ${ x \mapsto Df(x) }$ is continuous, so is ${ U \to (L(\mathbb{R} ^n, \mathbb{R} ^m), \lVert \cdots \rVert _F ) \cong (\mathbb{R} ^{mn}, \lVert \cdots \rVert _u)  ,}$ ${ x \mapsto Df(x) .}$    
Hence each component ${ D _j f _i : U \to \mathbb{R} }$ is continuous.     

${ \underline{\Leftarrow} }$ Say all partials ${ D _j f _i : U \to \mathbb{R} }$ exist and are continuous. By previous observation (on differentiating maps ${ \mathbb{R} ^n \to \mathbb{R} ^m }$), for every ${ x \in U , }$ 

$${ \begin{pmatrix} D _1 f _1 (x) &\cdots &D _n f _1 (x) \\ \vdots &\ddots &\vdots \\ D _1 f _m (x) &\cdots &D _n f _m (x)  \end{pmatrix}  }$$ 

works as the derivative of ${ f }$ at ${ x .}$ Continuity of components ${ D _j F _i : U \to \mathbb{R} }$ gives continuity of ${ U \to (L(\mathbb{R} ^n, \mathbb{R} ^m), \lVert \cdots \rVert _F ) , }$ ${ x \mapsto Df(x) .}$ Hence ${ U \to (L(\mathbb{R} ^n, \mathbb{R} ^m), \lVert \cdots \rVert _{\text{op}} ) , }$ ${ x \mapsto Df(x) }$ is continuous, that is ${ f }$ is a ${ C ^1  }$ map.  

**Thm** [Mean value theorem]:    
Let ${ E, F }$ be complete normed spaces, and ${ f : U (\subseteq E \text{ open}) \to F }$ a ${ C ^1 }$ map.     
Consider a segment ${ [[x, y]] = \lbrace x + t(y-x) : t \in [0, 1] \rbrace }$ contained in ${ U .}$ Then

$${ \begin{align*} f(y) - f(x) = &\int _0 ^1 Df(x+t(y-x)) (y-x) \, dt \\ = &\left( \int _0 ^1 Df(x+t(y-x)) \, dt \right) \cdot (y-x) . \end{align*} }$$ 

> Especially 
> 
> $${ \begin{align*} \lVert f(y) - f(x) \rVert \leq &\sup _{t \in [0, 1]} \lVert Df(x + t(y-x)) \rVert \lVert y - x \rVert \\ = &\sup _{v \in [[x, y]]} \lVert Df(v) \rVert \lVert y - x \rVert .  \end{align*} }$$
> 
> As ${ t \mapsto \lVert Df(x + t(y-x)) \rVert }$ is continuous on the compact set ${ [0, 1] , }$ the term 
>
> $${ \sup _{t \in [0, 1]} \lVert Df(x + t(y-x)) \rVert < \infty .}$$ 

**Pf**: Consider

$${ g : [0, 1] \to F, \quad g(t) = f(x + t(y-x)).  }$$

As ${ g ^{’} (t) =  Df(x+t(y-x)) \circ (y-x)  }$ is continuous, 

$${ g(1) - g(0) = \int _0 ^1 g ^{’}(t) \, dt  }$$ 

that is 

$${ f(y) - f(x) = \int _0 ^1 Df(x+t(y-x)) (y-x) \, dt, }$$ 

as needed. 

###### 6. 

$${ \underline{\textbf{Second derivative}} }$$

**Def** [${ C ^2 }$ maps]: Let ${ E, F }$ be complete normed spaces, and ${ f : U (\subseteq E \text{ open}) \to F .}$    
We say ${ f }$ is ${ C ^2 }$ if it is ${ C ^1 }$ and the derivative ${ Df : U \to L(E, F) }$ is ${ C ^1 , }$ that is if the derivatives  

$${ Df : U \longrightarrow L(E, F),  }$$ 

$${ D(Df) = D^2 f : U \longrightarrow L(E, L(E, F)) }$$ 

exist and are continuous. 

The codomain ${ L (E, L(E, F)) }$ above is infact the space of continuous bilinear maps ${ L ^2 (E; F) .}$ 

**Obs** [${ L(E, L(E, F)) \cong L ^2 (E; F)  }$ as normed spaces]:    
Let ${ E, F }$ be complete normed spaces. Recall ${ L ^k (E; F) }$ is the space of continuous multilinear maps ${ \underbrace{E \times \ldots \times E} _{k \text{ many}}  \to F . }$ Now 

$${ \Phi :  L(E, L(E, F)) \longrightarrow L ^{2} (E; F),  }$$ 

$${ \lambda \longmapsto ( (x _1, x _2) \mapsto \lambda (x _1) (x _2)  )  }$$ 

is an isomorphism of normed spaces. 

> Here ${ \lambda }$ in ${ L(E, L(E, F)) }$ takes inputs as ${ \lambda (\_) (\_) ,}$ and ${ \Phi (\lambda) }$ in ${ L ^2 (E; F) }$ takes inputs as ${ \Phi (\lambda) (\_ \, , \, \_) .}$    
> Writing (informally) ${ \Phi (\lambda) }$ as ${ \lambda (\_ \, , \_ ) ,}$ the normed space isomorphism is 
> 
> $${ \begin{align*} &\, L(E, L(E, F)) \overset{\cong}{\longleftrightarrow} L ^2 (E; F) , \\ &\, \quad \lambda (\_) (\_) \quad \longleftrightarrow \quad \lambda (\_ \, , \, \_) . \end{align*} }$$ 

**Pf**: Firstly, if ${ \lambda \in L(E, L(E, F)) }$ then 

$${  \Phi(\lambda) :  (x _1, x _2) \mapsto \lambda (x _1) (x _2) }$$

is in ${ L ^2 (E; F) }$: Bilinearity of ${ \Phi (\lambda) }$ is clear, and continuity of ${ \Phi(\lambda) }$ is because 

$${ \begin{align*} \lVert \lambda (x _1) (x _2) \rVert \leq &\, \lVert \lambda (x _1) \rVert \lVert x _2 \rVert \quad (\text{as } \lambda(x _1) \in L(E, F)) \\ \leq &\, \lVert \lambda \rVert \lVert x _1 \rVert \lVert x _2 \rVert  \quad (\text{as } \lambda \in L(E, L(E, F))).  \end{align*} }$$ 

So ${ \Phi }$ is well-defined. 

Linearity of ${ \Phi }$ is clear. 

The above inequality gives 

$${ \lVert \Phi (\lambda) \rVert \leq \lVert \lambda \rVert ,   }$$ 

but even 

$${ \begin{align*} \lVert \lambda \rVert = &\, \sup _{x _1 \neq 0} \frac{\lVert \lambda (x _1) \rVert _{L(E, F)} }{\lVert x _1 \rVert} \\ = &\, \sup _{x _1\neq 0} \left( \sup _{x _2  \neq 0} \frac{\lVert \lambda(x _1)(x _2)\rVert}{\lVert x _1 \rVert \lVert x _2  \rVert}   \right) \\ \leq &\, \sup _{x _1 \neq 0} \lVert \Phi (\lambda) \rVert   = \lVert \Phi (\lambda) \rVert ,    \end{align*} }$$ 

so 

$${ \lVert \Phi (\lambda) \rVert = \lVert \lambda \rVert   }$$ 

that is ${ \Phi }$ preserves norms. 

It is left to show that ${ \Phi }$ is a bijection. 

Surjectivity of ${ \Phi }$: Say ${ f \in L ^2 (E; F) . }$ We want an ${ f _0 \in L(E, L(E, F)) }$ such that ${ \Phi (f _0) = f .}$    
Informally, defining ${ f _0 := f(\_) (\_) }$ works. Formally, consider 

$${ f _0 : E \longrightarrow L(E, F) , }$$ 

$${ x _1 \longmapsto (x _2  \mapsto f(x _1, x _2)) . }$$ 

Each ${ f _0 (x _1 ) }$ is in ${ L(E, F) , }$ because linearity of ${ f _0 (x _1) : E \to F  }$ is clear and  

$${ \sup _{x _2\neq 0} \frac{\lVert f _0 (x _1) (x _2) \rVert}{\lVert x _2 \rVert} = \sup _{x _2 \neq 0} \frac{\lVert f(x _1, x _2) \rVert}{\lVert x _2 \rVert} \leq \lVert f \rVert \lVert x _1 \rVert < \infty .  }$$

Now ${ f _0 \in L(E, L(E, F)) , }$ because linearity of ${ f _0 }$ is clear and 

$${ \begin{align*} \sup _{x _1 \neq 0} \frac{\lVert f _0 (x _1) \rVert _{L(E, F)}}{\lVert x _1 \rVert} = &\, \sup _{x _1 \neq 0} \left( \sup _{x _2 \neq 0} \frac{\lVert f _0 (x _1) (x _2)  \rVert }{\lVert x _1 \rVert \lVert x _2  \rVert}  \right) \\ \leq &\sup _{x _1 \neq 0} \lVert f \rVert = \lVert f \rVert < \infty . \end{align*}  }$$ 

Finally ${ \Phi(f _0) = f }$ because 

$${ \begin{align*} \Phi(f _0) \, (x _1, x _2) = &\, f _0 (x _1) (x _2)  \\ = &\, f \, (x _1, x _2)  \end{align*}  }$$ 

for all ${ x _1, x _2 \in E .  }$ 

Injectivity of ${ \Phi }$: Say ${ \Phi(\lambda _1) = \Phi (\lambda _2) }$ for some ${ \lambda _1, \lambda _2 \in L(E, L(E, F) ) .}$ Now 

$${ \begin{align*} \lVert \lambda _1 - \lambda _2 \rVert = &\, \lVert \Phi (\lambda _1 - \lambda _2) \rVert \\ = &\, \lVert \Phi(\lambda _1) - \Phi (\lambda _2) \rVert  \\ = &\, 0, \end{align*} }$$ 

so ${ \lambda _1 = \lambda _2 . }$  

Therefore ${ \Phi }$ is an isomorphism of normed spaces, as needed. ${ \blacksquare }$ 

**Obs**: Any bilinear map 

$${ \lambda : \mathbb{R} ^n \times \mathbb{R} ^n \to \mathbb{R} ^m , \quad \lambda = (\lambda _1, \ldots, \lambda _m) ^T  }$$ 

is continuous because each component 

$${   \lambda _i (x _1, x _2) = \sum _{j _1, j _2  \in [n]}  (x _1) _{j _1} (x _2) _{j _2}   \lambda _i (e _{j _1}, e _{j _2})   }$$

is continuous. 

**Obs** [${ C ^2 }$ maps ${ \mathbb{R} ^n \to \mathbb{R} ^m }$]:    
Consider ${ f : U (\subseteq \mathbb{R} ^n \text{ open}) \to \mathbb{R} ^m .}$    
From the previous result on ${ C ^1 }$ maps ${ \mathbb{R} ^n \to \mathbb{R} ^m ,}$

$${ \begin{align*} &(f : U \to \mathbb{R} ^m \text{ is } C ^2) \\ \iff &\left(f \text{ is } C ^1 \text{ and } Df: U \to L(\mathbb{R} ^n, \mathbb{R} ^m) \text{ is } C ^1 \right) \\ \iff &\left(f \text{ is } C ^1 \text{ and } Df: U \to (L(\mathbb{R} ^n, \mathbb{R} ^m), \lVert \cdots \rVert _F) \cong \mathbb{R} ^{mn} \text{ is } C ^1  \right) \\ \iff &\left(\begin{aligned} &\text{All partials } D _{j _1} f _i : U \to \mathbb{R} \text{ exist and are continuous;} \\ &\text{All partials } D _{j _1} D _{j _2} f _i : U \to \mathbb{R} \text{ exist and are continuous} \end{aligned}    \right)  . \end{align*} }$$    

**Thm** [${ D ^2 f }$ for ${ C ^2 }$ maps ${\mathbb{R} ^n \to \mathbb{R} ^m }$]:    
Let ${ f : U (\subseteq \mathbb{R} ^n \text{ open}) \to \mathbb{R} ^m }$ be a ${ C ^2 }$ map and ${ x \in U . }$ Then the second derivative 

$${ D^2 f (x) \in  L(\mathbb{R} ^n, L(\mathbb{R} ^n, \mathbb{R} ^m)) \cong L ^2 (\mathbb{R} ^n; \mathbb{R} ^m)    }$$ 

is given by its action on basis vectors 

$${  D ^2 f (x) : \mathbb{R} ^n \times \mathbb{R} ^n \to \mathbb{R} ^m \text{ bilinear,}  }$$ 

$${ \boxed{\begin{align*} D ^2 f (x) \quad  \underbrace{(e _{{\color{red}{j _1}}})} _{\text{in } \mathbb{R} ^n} \quad \underbrace{(e _{{\color{blue}{j _2}}})} _{\text{in } \mathbb{R} ^n} = &\, \underbrace{\begin{pmatrix} D _{{\color{red}{j _1}}}  D _{{\color{blue}{j _2}}} f _1 (x) \\ \vdots \\ D _{{\color{red}{j _1}}}  D _{{\color{blue}{j _2}}}  f _m (x)   \end{pmatrix}} _{\text{in } \mathbb{R} ^m} \end{align*} }   }$$ 

that is 

$${ D ^2 f (x) (x _1) (x _2) = \sum _{j _1, j _2 \in [n]} (x _1) _{j _1} (x _2) _{j _2} \begin{pmatrix} D _{j _1} D _{j _2} f _1 (x) \\ \vdots \\ D _{j _1} D _{j _2} f _m (x) \end{pmatrix}   . }$$ 

> For ${ m = 1 , }$ this second derivative looks like 
> 
 > $${ D ^2 f (p) : \mathbb{R} ^n \times \mathbb{R} ^n \to \mathbb{R} \text{ bilinear,} }$$ 
>
>  $${ \begin{align*} D ^2 f (p) \, (x) (y) = &\, \sum _{i, j} x _i y _j D ^2 f (p) (e _i) (e _j) \\ = &\, \sum _{i, j} x _i y _j D _i D _j f(p) \\ = &\, x ^T \begin{pmatrix} D _1 D _1 f(p) &\cdots &D _1 D _n f(p) \\ \vdots &\ddots &\vdots \\ D _n D _1 f(p) &\cdots &D _n D _n f(p)  \end{pmatrix} y  \\ = &\, x ^T H f (p) y \end{align*} }$$ 
> 
 > and ${ H f (p) = [D _i D _j f(p)]  }$ is called the Hessian. 

 **Pf**: Let ${ f : U (\subseteq \mathbb{R} ^n \text{ open}) \to \mathbb{R} ^m }$ be ${ C ^2 }$ and ${ x \in U . }$ By the definition of derivative, for ${ h }$ in a neighbourhood of ${ 0, }$ 

 $${ \begin{align*} &Df(x+h) = Df(x) + D ^2 f(x) \, h + \lVert h \rVert \varphi (h) \text{ in } L(\mathbb{R} ^n, \mathbb{R} ^m) \\ &\, \text{with } \varphi(0) = 0 \text{ and } \varphi (h) \text{ continuous at } 0 .    \end{align*} }$$

 So (for ${ t _1 }$ in a neighbourhood of ${ 0 }$) 

 $${ \begin{align*} Df(x + t _1 e _{j _1}) \, e _{j _2} = &\, Df (x) \, e _{j _2}  + D ^2 f (x) (t _1 e _{j _1}) (e _{j _2}) \\  &\, + \lVert t _1 e _{j _1} \rVert \varphi (t _1 e _{j _1}) \, e _{j _2}  \end{align*}   }$$ 

 that is 

 $${ \begin{align*} \begin{pmatrix} D _{j _2} f _1 (x + t _1 e _{j _1}) \\ \vdots \\ D _{j _2} f _m (x + t _1 e _{j _1})  \end{pmatrix}   = &\, \begin{pmatrix} D _{j _2} f _1 (x) \\ \vdots \\ D _{j _2} f _m (x) \end{pmatrix} + t _1 D ^2 f (x) (e _{j _1}) (e _{j _2}) \\ &\, +  \vert t _1 \vert \varphi (t _1 e _{j _1})  \, e _{j _2} . \end{align*}   }$$ 

 Dividing by ${ t _1 \neq 0 }$ and letting ${ t _1 \to 0  }$ gives  

 $${ D ^2 f (x) (e _{j _1}) (e _{j _2}) = \begin{pmatrix} D _{j _1} D _{j _2} f _1 (x) \\ \vdots \\ D _{j _1} D _{j _2} f _m (x) \end{pmatrix}  }$$ 

 as needed. ${ \blacksquare }$ 

 **Thm** [Second derivatives are symmetric]:    
 Let ${ E, F }$ be complete normed spaces and ${ f : U (\subseteq E \text{ open}) \to F }$ a ${ C ^2 }$ map.    
 Then for every ${ x \in U, }$ the bilinear map ${ D ^2 f(x) }$ is symmetric that is 

 $${ D ^2 f (x) (v) (w) = D ^2 f (x) (w) (v). }$$ 

 > So especially if ${ f : U (\subseteq \mathbb{R} ^n \text{ open}) \to \mathbb{R} }$ is ${ C ^2 ,}$ its Hessian at every point is symmetric. 

 **Pf**: Let ${ x \in U . }$ There is an ${ r > 0 }$ such that ${ B(x, r) \subseteq U .}$    
 
 Pick any ${ v, w \in E }$ with lengths ${ \lVert v \rVert, \lVert w \rVert < \frac{r}{2} .}$ The length constraint is so that the points ${ x, x + v, x + w, x + v+w }$ are all in the ball. 
 
 As ${ D ^2 f (x) }$ scales as ${ D ^2 f (x) (\lambda v) (\mu w) = \lambda \mu D ^2 f (x) (v) (w) ,}$ it suffices to show 

 $${ \text{To show: } D ^2 f (x) (v) (w) = D ^2 f (x) (w) (v) . }$$ 

 > **Heuristic**: We have two approximations 
> 
> $${ \begin{align*} f(x + v + w) \approx &\, f(x + v) + Df(x+v) \, w \\ \approx &\, f(x) + Df(x) \, v \\ &\, + [ Df(x) + D ^2 f(x) (v)  ] w  \end{align*} }$$ 
>
> and 
> 
> $${ \begin{align*} f(x + v + w) \approx &\, f(x + w) + Df(x+w) \, v \\ \approx &\, f(x) + Df(x) \, w \\ &\, + [ Df(x) + D ^2 f(x) (w)  ] v . \end{align*}  }$$ 
> 
> Comparing both, one expects 
> 
> $${ D ^2 f (x) (v) (w) = D ^2 f (x) (w) (v)  }$$
> 
> to hold. 

 Consider the difference maps 

 $${ G _v, G _w  : B (x, r/2) \longrightarrow F,   }$$ 

 $${ G _v (t) := f(t+v) - f(t), }$$ 
 
 $${ G _w (t) := f(t+w) - f(t) . }$$ 

 Applying ${ C ^1 }$ mean value theorem twice, 

 $${ \begin{align*} &\, G _v (x+w) - G _v (x) \\ = &\, \left( \int _0 ^1 DG _v (x+tw) \, dt \right) \cdot w  \\ = &\,   \int _0 ^1 [ Df (x + tw + v) -  Df (x + tw ) ] \, dt  \cdot w \\ = &\, \int _0 ^1  \left[ \int _0 ^1 D ^2 f (x + tw + sv) \cdot v \, ds \right] \, dt \cdot w \\ = &\, \int _0 ^1  \left[ \int _0 ^1 D ^2 f (x + tw + sv) \, ds \right] \, dt \, (v) (w)  \end{align*}   }$$ 

 and similarly 

 $${ \begin{align*} &G _w (x + v) - G _w (x) \\ = &\, \int _0 ^1  \left[ \int _0 ^1 D ^2 f (x + tv + sw) \, ds \right] \, dt \, (w) (v).   \end{align*} }$$ 

 But note the differences 

 $${ G _v (x + w) - G _v (x) = f(x+w+v) - f(x+w) - (f(x+v) - f(x))  }$$ 

 $${ G _w (x + v) - G _w (x ) = f(x + v + w) - f(x+v) - (f(x+w) - f(x))  }$$ 

 are equal, so 

 $${ \begin{align*} &\int _0 ^1  \left[ \int _0 ^1 D ^2 f (x + tw + sv) \, ds \right] \, dt \, (v) (w) \\ = &\, \int _0 ^1  \left[ \int _0 ^1 D ^2 f (x + tv + sw) \, ds \right] \, dt \, (w) (v) \end{align*}  }$$ 

that is 

$${ \begin{align*} &\, D ^2 f (x) (v) (w) + \underbrace{\int _0 ^1  \left[ \int _0 ^1 D ^2 f (x + tw + sv) - D ^2 f (x)  \, ds \right] \, dt \, (v) (w)} _{=: \, \Phi (v, w)} \\ = &\, D ^2 f (x) (w) (v) +  \underbrace{\int _0 ^1  \left[ \int _0 ^1 D ^2 f (x + tv + sw) - D ^2 f (x) \, ds \right] \, dt \, (w) (v)} _{=: \, \Psi (v, w)} .  \end{align*} }$$ 

The residues ${ \Phi (v, w) , \Psi (v, w)  }$ are bounded by 

$${ \begin{align*} &\lVert \Phi (v, w) \rVert \\ \leq &\, \left\lVert \int _0 ^1  \left[ \int _0 ^1 D ^2 f (x + tw + sv) - D ^2 f (x)  \, ds \right] \, dt \right\rVert \lVert v \rVert \lVert w \rVert  \\ \leq &\, \sup _{0 \leq t \leq 1} \left\lVert \int _0 ^1 D ^2 f (x + tw + sv) - D ^2 f (x)  \, ds\right\rVert \lVert v \rVert \lVert w \rVert \\ \leq &\, \sup _{0 \leq t \leq 1} \left( \sup _{0 \leq s \leq 1} \left\lVert D ^2 f (x + tw + sv) - D ^2 f (x) \right\rVert   \right) \lVert v \rVert \lVert w \rVert \\ \leq &\, \sup _{0 \leq t \leq 1} \left( \sup _{0 \leq s, t \leq 1} \left\lVert D ^2 f (x + tw + sv) - D ^2 f (x) \right\rVert   \right) \lVert v \rVert \lVert w \rVert \\ = &\, \sup _{0 \leq s, t \leq 1} \left\lVert D ^2 f (x + tw + sv) - D ^2 f (x) \right\rVert \lVert v \rVert \lVert w \rVert  \end{align*} }$$ 

and 

$${ \lVert \Psi (v, w) \rVert \leq \sup _{0 \leq s, t \leq 1}  \left\lVert D ^2 f (x + tv + sw) - D ^2 f (x)  \right\rVert \lVert w \rVert \lVert v \rVert .  }$$ 

So 

$${ \begin{align*} &\lVert D ^2 f(x) (v)(w) - D ^2 f (x) (w) (v) \rVert \\ = &\, \lVert \Phi (v, w) - \Psi (v, w) \rVert \\ \leq &\, 2 \sup _{0 \leq s, t \leq 1}  \left\lVert D ^2 f (x + tw + sv) - D ^2 f (x) \right\rVert \lVert v \rVert \lVert w \rVert .  \end{align*}  }$$ 

Replacing ${ v, w }$ with ${ \tau v, \tau w }$ (where ${ \tau \in (0, 1) }$) in the above inequality and using continuity of ${ D ^2 f , }$

$${ \begin{align*} &\lVert D ^2 f(x) (v)(w) - D ^2 f (x) (w) (v) \rVert \\ \leq &\, 2 \sup _{0 \leq s, t \leq 1}  \left\lVert D ^2 f (x + \tau(tw + sv)) - D ^2 f (x) \right\rVert \lVert v \rVert \lVert w \rVert \\ &\, \to 0 \text{ as } \tau \to 0 .  \end{align*}  }$$ 

Therefore 

$${ D ^2 f (x) (v) (w) = D ^2 f (x) (w) (v) }$$

as needed. ${ \blacksquare }$ 

###### 7. 

$${ \underline{\textbf{Third derivative}} }$$ 

**Def** [${ C ^3 }$ maps]: Let ${ E, F }$ be complete normed spaces, and ${ f : U (\subseteq \mathbb{E} \text{ open}) \to F .}$    
We say ${ f }$ is ${ C ^3 }$ if it is ${ C ^2 }$ and the second derivative is ${ C ^1 , }$ that is if the derivatives 

$${ Df : U \longrightarrow L(E, F) , }$$ 

$${D(Df) = D ^2 f : U \longrightarrow L (E, L(E, F)),   }$$ 

$${ D (D ^2 f) = D ^3 f : U \longrightarrow L(E, L (E, L(E, F)))  }$$ 

exist and are continuous. 

We saw ${ L(E, L(E, F)) \cong L ^2 (E; F)  }$ as normed spaces. This can be generalised. 

**Obs** [${ L (E, L ^k (E; F)) \cong L ^{k+1} (E; F) }$ as normed spaces]:    
Let ${ E, F }$ be complete normed spaces. Then

$${ \Phi : L(E, L ^k (E; F)) \longrightarrow L ^{k+1} (E; F),  }$$ 

$${ \lambda \mapsto ((x _1, \ldots, x _{k+1}) \mapsto \lambda (x _1) (x _2, \ldots, x _{k+1})) }$$ 

is an isomorphism of normed spaces.    

> Here ${ \lambda }$ in ${ L(E, L ^k (E; F)) }$ takes inputs as ${ \lambda (\_) (\_ \, , \, \ldots \, , \_) , }$ and ${ \Phi (\lambda) }$ in ${ L ^{k+1} (E; F) }$ takes inputs as ${ \Phi (\lambda) (\_ \, , \, \_ \, , \, \ldots \, , \, \_ ) . }$    
> Writing (informally) ${ \Phi (\lambda) }$ as ${ \lambda (\_ \, , \, \ldots \, , \_) , }$ the normed space isomorphism is 
> 
> $${ \begin{align*} &L (E, L ^k (E; F)) \overset{\cong}{\longleftrightarrow} L ^{k+1} (E; F) , \\ &\lambda (\_) (\_ \, , \, \ldots \, , \, \_) \longleftrightarrow \lambda (\_ \, , \, \ldots \, , \_) . \end{align*} }$$ 

**Pf**: Similar to the previous proof/verification that ${  L (E, L(E, F)) \cong L ^2 (E; F)  }$ as normed spaces. 

**Obs** [${ L(E, \ldots, L(E, L(E, F)) \ldots ) \cong L ^k (E; F) }$ as normed spaces]:    
Let ${ E, F }$ be complete normed spaces. Repeatedly using the above result gives 

$${ \begin{align*} \underbrace{L(E, \ldots , L(E, L(E, L(E, F))) \ldots )} _{k \text{ many } Es} \cong &\, \underbrace{L(E, \ldots, L(E, L ^2 (E; F)) \ldots )} _{k-1 \text{ many } Es} \\  \cong &\, \, \cdots \\ \cong &\, L ^k (E; F) \end{align*} }$$ 

as normed spaces. The composed isomorphism is 

$${\Phi : \underbrace{L(E, \ldots, L(E, F) \ldots)} _{k \text{ many } Es} \longrightarrow L ^k (E; F) ,   }$$ 

$${ \lambda \mapsto ((x _1, \ldots, x _k) \mapsto \lambda (x _1) \ldots (x _k)) .  }$$ 

For example when ${ k = 3, }$ 

$${ \begin{align*} &L(E, L(E, L(E, F))) \overset{\cong}{\longleftrightarrow} L(E, L ^2 (E; F)) \overset{\cong}{\longleftrightarrow} L ^3 (E; F), \\ &\, \quad \lambda (\_) (\_) (\_) \quad \longleftrightarrow \quad \lambda (\_) ( \_ \, , \, \_ ) \quad \longleftrightarrow \quad \lambda (\_ \, , \, \_ \, , \_ ) .  \end{align*}  }$$ 

**Obs**: Any multilinear map 

$${ \lambda : \underbrace{\mathbb{R} ^n \times \ldots \times \mathbb{R} ^n} _{k \text{ many}} \to \mathbb{R} ^m, \quad \lambda = (\lambda _1, \ldots, \lambda _m) ^T }$$ 

is continuous because each component 

$${ \lambda _i (x _1, \ldots, x _k ) = \sum _{j _1 , \ldots, j _k \in [n]} (x _1) _{j _1} \ldots (x _k) _{j _k} \lambda _i (e _{j _1}, \ldots, e _{j _k})  }$$ 

is continuous. 

**Obs**: Any ${ \lambda \in L ^k (\mathbb{R} ^n; \mathbb{R} ^m) }$ expands as above. Note

$${ \Phi : L ^k (\mathbb{R} ^n ; \mathbb{R} ^m) \longrightarrow \lbrace \text{maps } [n] ^k \times [m] \to \mathbb{R} \rbrace,  }$$ 

$${ \lambda \longmapsto \left( (j _1, \ldots, j _k; i) \mapsto \lambda _i (e _{j _1}, \ldots, e _{j _k}) \right)   }$$ 

is linear and bijective, making it an isomorphism of vector spaces.    
Especially ${ L ^k (\mathbb{R} ^n ; \mathbb{R} ^m) }$ is ${ n ^k m }$ dimensional and all norms on it [are equivalent](https://bvenkatakarthik.github.io/EquivNorms).    
The right hand side has the Frobenius norm 

$${ \lVert f \rVert _F = \sqrt{\sum f(j _1, \ldots, j _k; i) ^2 },  }$$ 

therefore 

$${ \lVert \lambda \rVert _{\text{Mult } F} := \lVert \Phi (\lambda) \rVert _F = \sqrt{\sum \lambda _i (e _{j _1}, \ldots, e _{j _k}) ^2 }  }$$ 

is a valid norm on ${ L ^k (\mathbb{R} ^n ; \mathbb{R} ^m ) }$ and makes ${ \Phi }$ an isomorphism of normed spaces. 

**Obs** [${ C ^3 }$ maps ${ \mathbb{R} ^n \to \mathbb{R} ^m }$]:    
Let ${ f : U (\subseteq \mathbb{R} ^n \text{ open}) \to \mathbb{R} ^m .}$ Say ${ f }$ is already ${ C ^2 , }$ that is all partials ${  D _{j _1 } f _i : U \to \mathbb{R}  }$ and ${ D _{j _1} D _{j _2} f _i : U \to \mathbb{R} }$ exist and are continuous.    
Now ${ f }$ is ${ C ^3 }$ if and only if ${ D ^2 f : U \to L ^2 (\mathbb{R} ^n ; \mathbb{R} ^m) }$ is ${ C ^1  , }$ if and only if ${ D ^2 f : U \to (L ^2 (\mathbb{R} ^n ; \mathbb{R} ^m) , \lVert \ldots \rVert _{\text{Mult } F} ) }$ is ${ C ^1 , }$ if and only if 

$${ U \longrightarrow (\lbrace \text{maps } [n] ^2 \times [m] \to \mathbb{R} \rbrace, \lVert \ldots \rVert _F) }$$ 

$${ x \longmapsto \left(\begin{align*} (j _1, j _2; i) \mapsto &\, D ^2 f _i (x) (e _{j _1}) (e _{j _2}) \\  &\, = D _{j _1} D _{j _2} f _i (x) \end{align*} \right) }$$ 

is ${ C ^ 1 , }$ if and only if all partials ${ D _{j _1} D _{j _2} D _{j _3} f _i : U \to \mathbb{R} }$ exist and are continuous. 

**Thm** [${ D ^3 f }$ for ${ C ^3 }$ maps ${ \mathbb{R} ^n \to \mathbb{R} ^m }$]:    
Let ${ f : U (\subseteq \mathbb{R} ^n \text{ open}) \to \mathbb{R} ^m }$ be a ${ C ^3 }$ map and ${ x \in U . }$    
Then the third derivative 

$${ D ^3 f (x) \in L (\mathbb{R} ^n , L(\mathbb{R} ^n, L(\mathbb{R} ^n, \mathbb{R} ^m))) \cong L ^3 (\mathbb{R} ^n; \mathbb{R} ^m) }$$ 

is given by its action on basis vectors 

$${ D ^3 f : \mathbb{R} ^n \times \mathbb{R} ^n \times \mathbb{R} ^n \to \mathbb{R} ^m \quad \text{multilinear},  }$$ 

$${ \boxed{D ^3 f (x) (e _{{\color{red}{j _1}}}) (e _{{\color{blue}{j _2}}}) (e _{{\color{green}{j _3}}}) =  \begin{pmatrix} D _{{\color{red}{j _1}}} D _{{\color{blue}{j _2}}} D _{\color{green}{j _3}} f _1 (x) \\ \vdots \\ D _{{\color{red}{j _1}}} D _{{\color{blue}{j _2}}} D _{\color{green}{j _3}} f _m (x)  \end{pmatrix} } }$$ 

that is 

$${ \begin{align*} &D ^3 f (x) (x _1) (x _2) (x _3) \\ = &\, \sum _{j _1, j _2, j _3 \in [n]} (x _1) _{j _1} (x _2) _{j _2} (x _3) _{j _3} \begin{pmatrix} D _{j _1} D _{j _2} D _{j _3} f _1 (x) \\ \vdots \\ D _{j _1} D _{j _2} D _{j _3} f _m (x)   \end{pmatrix}. \end{align*}  }$$ 

**Pf**: Let ${ f : U (\subseteq \mathbb{R} ^n \text{ open}) \to \mathbb{R} ^m }$ be ${ C ^3 }$ and ${ x \in U . }$    
By the definition of derivative, for ${ h }$ in a neighbourhood of ${ 0 , }$ 

$${ \begin{align*} &D ^2 f (x + h) = D ^2 f(x) + D ^3 f (x) \, h + \lVert h \rVert \varphi (h) \\ &\, \text{with }  \varphi (0) = 0 \text{ and } \varphi \text{ continuous at } 0 . \end{align*} }$$ 

So (for ${ t _1 }$ in a neighbourhood of ${ 0  }$)

$${ \begin{align*} &D ^2 f(x + t _1 e _{j _1}) \,  (e _{j _2}) (e _{j _3}) \\ = &\, D ^2 f (x) \, (e _{j _2}) (e _{j _3}) + D ^3 f (x) (t _1 e _{j _1}) \,  (e _{j _2}) (e _{j _3}) \\ &+ \lVert t _1 e _{j _1} \rVert \varphi (t _1 e _{j _1}) \, (e _{j _2}) (e _{j _3}) \end{align*}  }$$ 

that is 

$${ \begin{align*} &\begin{pmatrix} D _{j _2} D _{j _3} f _1 (x + t _1 e _{j _1}) \\ \vdots \\ D _{j _2} D _{j _3} f _m (x + t _1 e _{j _1})  \end{pmatrix} \\ = &\, \begin{pmatrix} D _{j _2} D _{j _3} f _1 (x) \\ \vdots \\ D _{j _2} D _{j _3} f _m (x)  \end{pmatrix}  + t _1  D ^3 f (x) (e _{j _1}) (e _{j _2}) (e _{j _3}) \\ &\, + \vert t _1 \vert \varphi (t _1 e _{j _1}) \, (e _{j _2}) (e _{j _3}) .  \end{align*} }$$ 

Dividing by ${ t _1 \neq 0 }$ and letting ${ t _1 \to 0 }$ gives 

$${ D ^3 f (x) (e _{j _1}) (e _{j _2}) (e _{j _3}) = \begin{pmatrix} D _{j _1} D _{j _2} D _{j _3} f _1 (x) \\ \vdots \\  D _{j _1} D _{j _2} D _{j _3} f _m (x) \end{pmatrix}   }$$ 

as needed. ${ \blacksquare }$ 

###### 8. 

$${ \underline{\textbf{Higher derivatives}} }$$ 

**Def** [${ C ^k }$ maps]: Let ${ E, F }$ be complete normed spaces, and ${ f : U (\subseteq E \text{ open}) \to F .}$    
We say ${ f }$ is ${ C ^k }$ if the derivatives 

$${ Df : U \longrightarrow L(E, F),  }$$ 

$${ D ^2 f : U \longrightarrow L (E, L(E, F)) \cong L ^2 (E; F), }$$ 

$${ \vdots  }$$ 

$${ D ^k f : U \longrightarrow \underbrace{L(E, \ldots L(E, F) \ldots )} _{k \text{ many } Es}  \cong L ^k (E; F)  }$$ 

exist and are continuous. 

**Obs** [${ C ^k }$ maps ${ \mathbb{R} ^n \to \mathbb{R} ^m }$]:    
Let ${ f : U (\subseteq \mathbb{R} ^n \text{ open}) \to \mathbb{R} ^m .}$ Then ${ f }$ is a ${ C ^k }$ map if and only if all partials ${ D _{j _1} f _i : U \to \mathbb{R}, }$ ${ D _{j _1} D _{j _2} f _i : U \to \mathbb{R}, }$ ${ \ldots, }$  ${ D _{j _1} \ldots D _{j _k} f _i : U \to \mathbb{R} }$ exist and are continuous.    
**Pf**: Proof by induction. Similar to the proof for ${ C ^2 }$ and ${ C ^3 }$ maps. 

**Obs** [${ D ^k f }$ for ${ C ^k }$ maps ${ \mathbb{R} ^n \to \mathbb{R} ^m }$]:    
Let ${ f : U (\subseteq \mathbb{R} ^n \text{ open}) \to \mathbb{R} ^m }$ be a ${ C ^k }$ map and ${ x \in U . }$    
Then the ${ k ^{\text{th}} }$ derivative 

$${ D ^k f (x) \in \underbrace{L(\mathbb{R} ^n \ldots L(\mathbb{R} ^n, \mathbb{R} ^m)  \ldots )} _{k \text{ nestings}} \cong L ^k (\mathbb{R} ^n; \mathbb{R} ^m)   }$$ 

is given by its action on basis vectors 

$${ D ^k f (x) : \underbrace{\mathbb{R} ^n \times \ldots \times \mathbb{R} ^n} _{k \text{ many}} \longrightarrow \mathbb{R} ^m \quad \text{ multilinear},  }$$ 

$${ \boxed{D ^k f(x) (e _{j _1}) \ldots (e _{j _k}) = \begin{pmatrix} D _{j _1} \ldots D _{j _k} f _1 (x) \\ \vdots \\ D _{j _1} \ldots D _{j _k} f _m (x)  \end{pmatrix} }  }$$ 

that is 

$${ \begin{align*} D ^k f (x) (x _1) \ldots (x _k)  =  &\, \sum _{j _1, \ldots, j _k \in [n]}  (x _1) _{j _1} \ldots (x _k) _{j _k} \begin{pmatrix} D _{j _1} \ldots D _{j _k} f _1 (x) \\ \vdots \\ D _{j _1} \ldots D _{j _k} f _m (x)  \end{pmatrix} .   \end{align*} }$$ 

**Pf**: Similar to the proof for ${ C ^2 }$ and ${ C ^3 }$ maps.  

###### 9. 

$${ \underline{\textbf{Taylor’s Theorem}} }$$ 

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


