---
layout: post
title: "Entropy Power Inequality"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Ref**: 
* “On the similarity of the Entropy Power Inequality and the Brunn Minkowski inequality” by Costa, Cover. 
* “The Convolution Inequality for Entropy Powers” by Blachman. 
* “Simple Proof of the Concavity of the Entropy Power with respect to added Gaussian Noise” by Dembo.  
* “Stochastic Models, Information Theory, and Lie Groups, Vol 1” by Chirikjian. 

Let ${ X, Y }$ be independent random variables. Suppose we know the entropies ${ H(X), H(Y) . }$ 

Can we bound the entropy ${ H(X + Y) }$? 

Let ${ \hat{X}, \hat{Y} }$ be independent centered Gaussians which have the same entropies as ${ X, Y }$ respectively. 

Note that it is straightforward to compute ${ H(\hat{X} + \hat{Y}) . }$ Note that 

$${ {\begin{aligned} &\, H(\hat{X} + \hat{Y}) \\ =  &\, \frac{1}{2} \ln \left( e 2 \pi \left( \sigma _{\hat{X}} ^2 + \sigma _{\hat{Y}} ^2 \right) \right) \\ = &\, \frac{1}{2} \ln \left( e 2 \pi \left( \frac{1}{e 2 \pi} e ^{2 H(X) } + \frac{1}{e 2 \pi} e ^{2 H(Y) } \right) \right) \\ = &\, \frac{1}{2} \ln \left(e ^{2 H(X)} + e ^{2 H(Y)}  \right) . \end{aligned}} }$$ 

Does ${ H(\hat{X} + \hat{Y}) }$ provide a bound for ${ H(X + Y) }$? 

It turns out yes. 

**Thm** [Entropy Power Inequality]    
Let ${ X, Y }$ be independent random variables. Let ${ \hat{X}, \hat{Y} }$ be independent centered Gaussians with the same entropies as ${ X, Y }$ respectively. Then 

$${ \boxed{ H(X + Y) \geq H(\hat{X} + \hat{Y}) } . }$$ 

Equivalently, 

$${ e ^{2 H(X + Y)} \geq e ^{2 H(X)}  +  e ^{2 H(Y) } .  }$$ 

**Pf**: Will prove later. 

[**Entropy of Gaussian perturbations**] 

Let ${ X }$ be a random variable. Consider Gaussian perturbations 

$${ X + Z _t, \quad Z _t \sim N(0, t).   }$$ 

How does the entropy ${ H(X + Z _t) }$ vary with ${ t }$? 

**Obs**: Note that 

$${ \boxed{ \frac{d}{dt} H(X + Z _t) = \frac{1}{2} J(X + Z _t) }  }$$ 

where 

$${ J(Z) = \int  \frac{(p ^{’} _Z )^2 }{p _Z} = \mathbb{E} _Z \left[ \frac{(p ^{’} _Z ) ^2 }{p _Z ^2} \right] .  }$$ 

**Pf**: Note that 

$${ {\begin{aligned} &\, \frac{d}{dt} H(X + Z _t) \\ = &\, - \frac{d}{dt} \int p _t (x) \ln (p _t (x) ) \, dx \\ = &\, - \int \left[ \partial _t p _t (x) \ln (p _t (x) )  + p _t (x) \frac{\partial _t p _t (x) }{p _t (x)} \right] \, dx \end{aligned}}  }$$ 

where ${ p _t  }$ is the density of ${ X + Z _t . }$ 

Note that 

$${ {\begin{aligned} &\, p _t (x) \\ = &\, (p \ast g _t) (x)  \\ =  &\, \int p(y) \frac{1}{\sqrt{2 \pi t}}  \exp \left( {- \frac{1}{2t} (x - y) ^2} \right) \, dy \end{aligned}} }$$ 

where ${ p , g _t }$ are the densities of ${ X , Z _t }$ respectively. 

Hence 

$${ {\begin{aligned} &\, \frac{d}{dt} H(X + Z _t) \\ = &\, - \int \left[ \partial _t p _t (x) \ln (p _t (x) )  + \partial _t p _t (x)  \right] \, dx \\ = &\, - \int \left[ (p \ast \partial _t g _t) \ln (p \ast g _t)  + (p \ast \partial _t g _t) \right] . \end{aligned}}  }$$ 

Note that ${ g _t }$ satisfies the one dimensional heat equation 

$${ \partial _t g _t (x) = \frac{1}{2} \partial _{x} ^2 g _t (x) .  }$$ 

> Note that 
> 
> $${ {\begin{aligned} &\, \partial _t g _t (x) \\ = &\, \partial _t \frac{1}{\sqrt{2 \pi t}} \int \exp \left( -\frac{x ^2}{2t} \right) \, dx \\ = &\,  \frac{1}{\sqrt{2 \pi}} \left( - \frac{1}{2} t ^{- 3/2} \right) \int \exp \left( -\frac{x ^2}{2t} \right) \, dx \\ &\, + \frac{1}{\sqrt{2 \pi t}} \int \exp \left( - \frac{x ^2}{2t} \right) \frac{x ^2}{2t ^2} \, dx \\ = &\, \frac{1}{\sqrt{2 \pi t }} \frac{1}{t} \int \exp \left( - \frac{x ^2}{2t} \right) \left( - \frac{1}{2} + \frac{x ^2}{2t}  \right) \, dx . \end{aligned}}  }$$ 
> 
> Note that 
> 
> $${ {\begin{aligned} &\, \partial _x ^2 g _t (x) \\ = &\, \partial _x  \frac{1}{\sqrt{2 \pi t}} \int \exp \left( - \frac{x ^2}{2t} \right) \left( - \frac{x}{t} \right)  \, dx \\ = &\, \frac{1}{\sqrt{2 \pi t}} \int \left[ \exp \left( - \frac{x ^2}{2t} \right) \left( - \frac{x}{t} \right) ^2 + \exp \left( - \frac{x ^2}{2t} \right)  \left( - \frac{1}{t} \right) \right] \, dx \\ = &\, 2 \frac{1}{\sqrt{2 \pi t }} \frac{1}{t} \int \exp \left( - \frac{x ^2}{2t} \right) \left( - \frac{1}{2} + \frac{x ^2}{2t}  \right) \, dx \\ = &\, 2 \partial _t g _t (x) \end{aligned}}  }$$ 
> 
> as needed. 
> 

Hence 

$${ {\begin{aligned} &\, \frac{d}{dt} H(X + Z _t) \\ = &\, - \int \left[ (p \ast \partial _t g _t) \ln (p \ast g _t)  + (p \ast \partial _t g _t) \right]  \\ = &\, - \frac{1}{2} \int \left[ (p \ast \partial _x ^2 g _t) \ln (p \ast g _t) +  (p \ast \partial _x ^2 g _t ) \right] . \end{aligned}} }$$ 

How do convolutions behave with derivatives? 

Note that 

$${ \partial _x (\phi _1 \ast \phi _2) (x) = (\phi _1 \ast \phi _2 ^{’}) (x) . }$$ 

> Note that 
> 
> $${ {\begin{aligned} &\, \partial _x (\phi _1 \ast \phi _2) (x) \\ = &\, \partial _x \int \phi _1 (y) \phi _2 (x - y) \, dt \\ = &\, \int \phi _1 (y) \phi _2 ^{’} (x - y) \, dy \\ = &\, (\phi _1 \ast \phi _2 ^{’})(x) \end{aligned}}  }$$ 
> 
> as needed. 
> 

Hence 

$${ {\begin{aligned} &\, \frac{d}{dt} H(X + Z _t) \\ = &\, - \frac{1}{2} \int \left[ (p \ast \partial _x ^2 g _t) \ln (p \ast g _t) +  (p \ast \partial _x ^2 g _t ) \right] \\ = &\, - \frac{1}{2} \int \left[ \partial _x ^2 (p \ast g _t) \ln (p \ast g _t) +  \partial _x ^2 (p \ast g _t) \right] .   \end{aligned}} }$$ 

Note that the second term 

$${ \int \partial _x ^2 (p \ast g _t) = \partial _x (p \ast g _t) \Big \vert _{-\infty} ^{\infty} = 0 . }$$ 

Note that the first term 

$${ {\begin{aligned} &\, \int \partial _x ^2 (p \ast g _t) \ln (p \ast g _t) \\ = &\, \partial _x (p \ast g _t) \ln (p \ast g _t) \Big \vert _{-\infty} ^{\infty} - \int \partial _x (p \ast g _t) \frac{\partial _x (p \ast g _t)}{p \ast g _t } \\ = &\, - \int \frac{(\partial _x (p \ast g _t)) ^2}{p \ast g _t} . \end{aligned}} }$$ 

Note that we have heuristically assumed ${ p(x) }$ decays rapidly enough as ${ x \to \pm \infty . }$ 

Hence 

$${ {\begin{aligned} &\, \frac{d}{dt} H(X + Z _t) \\ = &\,  \frac{1}{2} \int \frac{(\partial _x (p \ast g _t)) ^2}{p \ast g _t} \\ = &\, \frac{1}{2} J(X + Z _t)   \end{aligned}}  }$$ 

as needed. ${ \blacksquare }$ 

[**Information of Sum**] 

Let ${ X, Y }$ be independent random variables. Suppose we know ${ J(X), J(Y) . }$ 

Can we bound ${ J(X + Y) }$? 

Let ${ Z = X + Y . }$ 

Note that 

$${ p _Z (z) = (p _X \ast p _Y)(z) . }$$ 

Hence 

$${ p _Z ^{’} (z) = (p _X ^{’} \ast p _Y )(z). }$$ 

Hence 

$${ {\begin{aligned} &\, \frac{p _Z ^{’} (z)}{p _Z (z)} \\ = &\, \int  \frac{p _X ^{’} (x) p _Y (z - x)}{p _Z (z) } \, dx \\ = &\, \int \frac{p _X ^{’} (x)}{p _X (x)} \frac{p _X (x) p _Y (z - x)}{p _Z (z)} \, dx \\ = &\, \int \frac{p _X ^{’} (x)}{p _X (x)} \frac{p _{X, Z} (x, z) }{p _Z (z) } \, dx \\ = &\, \mathbb{E} \left[ \frac{p _X ^{’} (X)}{p _X (X)} \Bigg \vert Z = z \right] . \end{aligned}}  }$$ 

Note that similarly 

$${ {\begin{aligned} &\,  \frac{p _Z ^{’} (z)}{p _Z (z)} \\ = &\, \mathbb{E} \left[ \frac{p _Y ^{’} (Y)}{p _Y (Y)} \Bigg \vert Z = z \right] .   \end{aligned}} }$$ 

Note that taking linear combination 

$${ (a + b) \frac{p _Z ^{’} (z)}{p _Z (z) } = \mathbb{E} \left[ a \frac{p _X ^{’} (X)}{p _X (X)} + b \frac{p _Y ^{’} (Y)}{p _Y (Y)} \Bigg \vert Z = z \right] . }$$ 

Note that squaring 

$${ {\begin{aligned} &\, (a + b) ^2 \left(  \frac{p _Z ^{’} (z)}{p _Z (z) } \right) ^2 \\ = &\, \mathbb{E} \left[ a \frac{p _X ^{’} (X)}{p _X (X)} + b \frac{p _Y ^{’} (Y)}{p _Y (Y)} \Bigg \vert Z = z \right] ^2 \\ \leq  &\, \mathbb{E} \left[ \left( a \frac{p _X ^{’} (X)}{p _X (X)} + b \frac{p _Y ^{’} (Y)}{p _Y (Y)} \right) ^2 \Bigg \vert Z = z \right] . \end{aligned}} }$$ 

Note that averaging with respect to ${ p _Z (z) }$ 

$${ (a + b) ^2 \mathbb{E} \left[ \frac{(p _Z ^{’} (Z)) ^2}{p _Z (Z) ^2} \right] \leq \mathbb{E} \left[ \left( a \frac{p _X ^{’} (X)}{p _X (X)} + b \frac{p _Y ^{’} (Y)}{p _Y (Y)} \right) ^2 \right] .  }$$ 

Hence expanding the right hand side 

$${ (a + b) ^2 J(Z) \leq a ^2 J(X) + b ^2 J(Y). }$$ 

Hence 

$${ J(X + Y) \leq \lambda ^2 J(X) + (1 - \lambda ) ^2 J(Y) }$$ 

for all ${ \lambda \in (0, 1) . }$ 

Note that the right hand side, as a quadratic in ${ \lambda , }$ is minimized at 

$${ \lambda =  \frac{2 J(Y) }{2 (J(X) + J(Y))} . }$$

Hence setting this value for ${ \lambda }$ 

$${ \boxed{ J(X + Y) \leq \frac{J(X) J(Y)}{J(X) + J(Y)} }  . }$$ 

Equivalently, 

$${ \frac{1}{J(X+Y)} \geq \frac{1}{J(X)} + \frac{1}{J(Y)} . }$$ 

[**Entropy Power Inequality**] 

Let ${ X, Y }$ be independent random variables. Let ${ Z = X + Y . }$ 

Consider Gaussian perturbations ${ X _{f(t)} , Y _{g(t)} , Z _{h(t)} }$ where ${ h(t) = f(t) + g(t) . }$ Suppose ${ f(0) = g(0) = h(0) = 0 .  }$ 

Consider the function 

$${ \psi (t) =  \frac{\exp(2 H (X _{f(t)})) + \exp (2 H(Y _{g(t)}))}{\exp (2 H(Z _{h(t)})) }. }$$ 

We are interested in ${ \psi (0) . }$ 

Note that 

$${ {\begin{aligned} &\, \exp (2 H (Z _{h(t)})) J(Z _{h(t)}) h ^{’} (t) \psi (t) + \exp (2 H (Z _{h(t)})) \psi ^{’} (t) \\ = &\, \exp(2 H (X _{f(t)})) J(X _{f(t)}) f ^{’} (t) + \exp (2 H(Y _{g(t)})) J(Y _{g(t)}) g ^{’} (t) .  \end{aligned}}  }$$ 

Hence 

$${ {\begin{aligned} &\, J(Z _{h(t)}) \left[ f ^{’} (t) + g ^{’} (t) \right]  \left[ \exp(2 H (X _{f(t)})) + \exp (2 H(Y _{g(t)})) \right] \\ + &\, \exp (2 H (Z _{h(t)})) \psi ^{’} (t)  \\ = &\,  \exp(2 H (X _{f(t)})) J(X _{f(t)}) f ^{’} (t) + \exp (2 H(Y _{g(t)})) J(Y _{g(t)}) g ^{’} (t) . \end{aligned}}  }$$ 

Hence 

$${ {\begin{aligned} &\, \exp (2 H(Z _h)) \psi ^{’} (t) \\ \geq &\, \exp(2 H(X _f))  J(X _f) f ^{’} (t) +  \exp(2 H(Y _g )) J(Y _g) g ^{’} (t)  \\ - &\, \frac{J(X _f)J(Y _g)}{J(X _f) + J(Y _g)} \left[ f ^{’} (t) + g ^{’} (t) \right] \left[ \exp(2 H (X _{f(t)})) + \exp (2 H(Y _{g(t)})) \right] \\ = &\, \frac{1}{J(X _f) + J(Y _g)} \left\lbrace {\begin{aligned} &\, \exp (2 H (X _f)) J(X _f) ^2 f ^{’} (t) + \exp(2 H(Y _g )) J(Y _g) ^2 g ^{’} (t) \\ &\, - \exp(2 H(X _f)) g ^{’} (t)  J(X _f) J(Y _g) - \exp(2H(Y _g)) f ^{’} (t) J(X _f) J(Y _g) \end{aligned}}   \right\rbrace  \\ = &\, \frac{1}{J(X _f) + J(Y _g)} \left\lbrace \left[ f ^{’} (t) J(X _f) - g ^{’} (t) J(Y _g) \right] \left[ \exp(2H(X _f)) J(X _f) - \exp(2H(Y _g)) J(Y _g) \right] \right\rbrace . \end{aligned}}   }$$ 

Hence by putting 

$${ f ^{’} (t) = \exp(2 H(X _f)), \quad  g ^{’} (t) = \exp (2 H(Y _g)) }$$ 

we can ensure 

$${ \psi ^{’} (t) \geq 0 .  }$$ 

What is ${ \psi (+ \infty) }$? 

Note that 

$${ f(+ \infty) =  \int _0 ^{\infty} \exp(2H(X _{f(t)})) \, dt = + \infty . }$$ 

Similarly for ${ g(+ \infty) . }$ 

Hence 

$${ f(+ \infty) = g(+ \infty) = h(+ \infty) = + \infty .  }$$

How do the terms ${ H(X _f), }$ ${ H(Y _g), }$ ${ H(Z _h) }$ behave as ${ t \to + \infty }$? 

Consider 

$${ X _{F(t)} := X _{f(t)} / \sqrt{f(t)} .   }$$

Note that the density of ${ X _F }$ is 

$${ {\begin{aligned} &\, p _{X _F} (x) \\ = &\, \sqrt{f(t)} p _{X _f} \left(\sqrt{f(t)} x \right) \\ = &\, \sqrt{f(t)} \int p(y) \frac{1}{\sqrt{2 \pi f(t)}}  \exp \left( {- \frac{1}{2f(t)} \left(\sqrt{f(t)} x - y \right) ^2} \right) \, dy \\ = &\,  \int \sqrt{f}  p(\sqrt{f} u) \frac{1}{\sqrt{2 \pi f}} \exp \left( - \frac{1}{2} (x - u) ^2  \right) \, \sqrt{f} du  \end{aligned}}  }$$ 

Note that the term ${ \sqrt{f} p(\sqrt{f} u) }$ is the density of ${ X / \sqrt{f} }$ at ${ u .  }$ Hence ${ X _F }$ can be thought of as ${ X / \sqrt{f} }$ plus a standard Gaussian.  

Hence as ${ t \to \infty , }$ ${ X _F }$ behaves like the standard Gaussian. 

Note that the entropy of ${ X _F }$ is 

$${ H(X _F) = H(X _f) - \frac{1}{2} \ln(f) . }$$ 

Hence as ${ t \to \infty , }$ 

$${ H(X _f) - \frac{1}{2} (\ln(f) + \ln (2 \pi e))  \to 0 . }$$ 

Similarly as ${ t \to \infty , }$ 

$${ H(Y _g) - \frac{1}{2} \ln(2 \pi e g)  \to 0 }$$ 

and 

$${ H(Z _h) - \frac{1}{2} \ln(2 \pi e h) \to 0 .  }$$ 

Hence 

$${ \psi(+ \infty) =  \frac{2 \pi e f + 2 \pi e g}{2 \pi e h} = 1 . }$$ 

Hence 

$${ \psi(0) \leq \psi(+ \infty) = 1  . }$$

Hence 

$${ \exp(2H(X)) + \exp(2H(Y)) \leq \exp(2 H(Z))  }$$ 

as needed. ${ \blacksquare }$


