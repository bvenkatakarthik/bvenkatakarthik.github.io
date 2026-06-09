---
layout: post
title: "Entropy as Average Doubt"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

[**Doubt of an event**] 

Consider a setup where various events are assigned various probabilities. 

For an event ${ E , }$ let ${ \mathbb{P}(E) }$ denote the probability of occurence of ${ E , }$ a **measure of certainity of ${ E }$ occuring**. 

Suppose we want to assign to each event ${ E, }$ a **measure of doubt of ${ E }$ occuring**, ${ \text{Doubt}(E) \in \mathbb{R} _{\geq 0}. }$ 


One immediate option is 

$${ \text{Doubt} _{1} (E) := 1 - \mathbb{P}(E).  }$$ 

It seems reasonable, because for example ${ \text{Doubt} _{1} (E)  }$ decreases as ${ \mathbb{P}(E) }$ increases. 

So far, any non-negative, decreasing function of ${ \mathbb{P}(E) }$ seems to be reasonable as a measure of doubt.

But suppose we further want "additivity"

$${ {\begin{aligned} &\, \text{Want:} \\ &\, \text{For independent events } A, B, \\ &\, \text{the doubt that both } A \text{ and } B \text{ occur} \\ &\, \text{is the sum of doubts of } A \text{ and } B. \end{aligned}}   }$$ 

That is we want 

$${ {\begin{aligned} &\, \text{Want:} \\ &\, \text{For independent events } A, B, \\ &\, \text{Doubt}(A \cap B) = \text{Doubt}(A) + \text{Doubt}(B).  \end{aligned}} }$$ 

Looking for doubts of the form  

$${ \text{Doubt}(E) = f(\mathbb{P}(E)) ,  }$$ 

we see we want 

$${ \text{Want:} \quad f(\mathbb{P}(A) \mathbb{P}(B)) = f(\mathbb{P}(A)) + f(\mathbb{P}(B))  }$$ 

and we see 

$${ f(x) = - k \log(x), \quad k > 0   }$$ 

are more or less the only candidates. 

Hence 

$${ \boxed{ \text{Doubt}(E) := - \log( \mathbb{P}(E) ) = \log \left( \frac{1}{\mathbb{P}(E)} \right) .   }  }$$ 

is a "good" measure of doubt of an event occuring. 


[**Average doubtfulness of the realisations of a random variable: Entropy of the random variable**] 

Consider a discrete random variable ${ X }$ taking values ${ x _1, \ldots, x _n }$ with probabilities ${ p _1, \ldots, p _n . }$ 

Suppose we are observing a realisation of ${ X . }$ 

With probability ${ p _1 ,}$ we observe a realisation ${ X = x _1 }$ with doubt ${ \text{Doubt}(X = x _1) , }$ and so on. 

Hence the average doubt of a realisation of ${ X }$ is 

$${ - \sum _{i = 1} ^{n} p _i \log (p _i) .  }$$ 

We call this the entropy ${ \text{Ent}(X) }$ of ${ X . }$ 

**The entropy of a random variable is the average doubtfulness of the realisations of the random variable.**

Note that in this context, the [Principle of Maximum Entropy](https://en.wikipedia.org/wiki/Principle_of_maximum_entropy) feels intuitive: Within given constraints, to model a situation, we should prefer picking those random variables of highest entropy  (this way, we **MAXIMIZE OUR IGNORANCE ${ \approx }$ DOUBTFULNESS about realisations of the random variable**). 


