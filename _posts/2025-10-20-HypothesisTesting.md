---
layout: post
title: "Hypothesis Testing"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Updated**: 21/10/25

**Ref**: 
* "Introduction to Mathematical Statistics" by Hogg, McKean, Craig. 
 * "Statistics for Mathematicians" by Panaretos. 

[**Hypothesis Testing**] 

Consider a random variable ${ X }$ with density ${ f(x; \theta) , }$ ${ \theta \in \Omega . }$ 

Suppose we think ${ \theta \in \Omega _0 }$ or ${ \theta \in \Omega _1 , }$ where ${ \Omega = \Omega _0 \sqcup \Omega _1 . }$ 

We label these hypotheses as 

$${ H _0 : \theta \in \Omega _0 \, \, \text{ versus } \, \, H _1 : \theta \in \Omega _1 .  }$$

We call ${ H _0 }$ the null hypothesis, and ${ H _1 }$ the alternative hypothesis. Often the null hypothesis represents no change from the past belief, while the alternative represents change from past belief. 

Consider a sample ${ X _1, \ldots, X _n }$ from ${ X . }$ 

**Q**) Can we have a reasonable decision rule / test to take ${ H _0 }$ or ${ H _1 }$ based on the sample? 

**Q**) What is a decision rule / test? 

Consider the space of the sample 

$${ \mathcal{D} = \text{space} \lbrace (X _1, \ldots, X _n) \rbrace . }$$ 

A test of ${ H _0 }$ versus ${ H _1 }$ is based on a subset ${ \mathcal{C} \subseteq \mathcal{D} , }$ such that 

$${ {\begin{aligned} &\, \text{Reject } H _0 \, \, \text{ if } (X _1, \ldots, X _n) \in \mathcal{C}, \\ &\, \text{Retain } H _0 \, \, \text{ if } (X _1, \ldots, X _n) \not\in \mathcal{C}.   \end{aligned}}  }$$ 

We call ${ \mathcal{C} }$ the critical region of the test.

**Q**) Can we have a measure of effectiveness of a given test? 

Note that given a test, two types of errors can occur. 

![HypothesisTesting](https://a.l3n.co/Pna9YD.jpg)

Note that a Type ${ \text{I} }$ error is considered more significant than a Type ${ \text{II} }$ error. 

Hence in looking for the potential critical regions, we would want to bound the probability of Type ${ \text{I} }$ error. 

Pick an ${ \alpha > 0 . }$ 

We say a critical region ${ \mathcal{C} }$ is of size ${ \alpha }$ if 

$${ \sup _{\theta \in \Omega _0} \mathbb{P} _{\theta} ((X _1, \ldots, X _n) \in \mathcal{C}) = \alpha  . }$$ 

Over all critical regions of size atmost ${ \alpha , }$ we want to look for critical regions with lower probabilities of Type ${ \text{II} }$ error. 

Over all critical regions of size atmost ${ \alpha , }$ we want to look for critical regions which minimize the function 

$${ \mathbb{P} _{\theta} ((X _1, \ldots, X _n) \not \in \mathcal{C}) ; \quad \theta \in \Omega _1 .  }$$ 

Over all critical regions of size atmost ${ \alpha , }$ we want to look for critical regions which maximize the power function 

$${ \gamma _{\mathcal{C}} (\theta) = \mathbb{P} _{\theta} ((X _1, \ldots, X _n) \in \mathcal{C}) ; \quad \theta \in \Omega _1 .  }$$

**Eg**: Let ${ X }$ be a random variable with mean ${ \mu }$ and variance ${ \sigma ^2 . }$ Consider a sample ${ X _1, \ldots, X _n }$ from ${ X . }$ 

Suppose we want to test 

$${ H _0 : \mu = \mu _0 \, \, \text{ versus } \, \, H _1 : \mu \neq \mu _0   }$$ 

where ${ \mu _0 }$ is specified. 

Consider tests of the form 

$${ T _k : \quad \text{Reject } \, H _0 \, \text{ if } \, \, \left \vert \frac{\overline{X _n} - \mu _0}{S/ \sqrt{n}}  \right \vert \geq k .  }$$ 

Let ${ \alpha > 0 . }$

Let us impose the constraint that the size of the test is atmost ${ \alpha . }$ 

Hence 

$${ \mathbb{P} _{\mu _0} \left( \left \vert \frac{\overline{X _n} - \mu _0}{S/ \sqrt{n}}  \right \vert \geq k \right) \leq  \alpha .   }$$ 

Hence 

$${ k \geq z _{\alpha / 2} . }$$ 

Over all tests with ${ k \geq z _{\alpha / 2 } , }$ we are to pick a ${ k }$ which maximises the power function 

$${ \gamma _k (\mu) = \mathbb{P} _{\mu} \left( \left \vert \frac{\overline{X _n} - \mu _0}{S/ \sqrt{n}}  \right \vert \geq k \right); \quad \mu \neq \mu _0 .   }$$ 

Note that 

$${ {\begin{aligned} &\, \gamma _k (\mu) \\ = &\, \mathbb{P} _{\mu} \left( \left \vert \frac{\overline{X _n} - \mu}{S/ \sqrt{n}} - \frac{\mu _0 - \mu}{S / \sqrt{n}}  \right \vert \geq k \right) \\ = &\, \mathbb{P}\left( N(0, 1) > \frac{\mu _0 - \mu}{S / \sqrt{n}} + k \right) + \mathbb{P} \left( N(0, 1) < \frac{\mu _0 - \mu}{S / \sqrt{n}} - k \right) .    \end{aligned}}  }$$ 

Note that 

$${ \gamma _k (\mu) \,  \text{ decreases as } \, k \, \text{ increases}.   }$$ 

Hence we pick the test with 

$${ k = z _{\alpha / 2} .  }$$ 

Hence the required test is 

$${ T _{\alpha / 2} : \quad \text{Reject } \, H _0 \, \text{ if } \, \, \left \vert \frac{\overline{X _n} - \mu _0}{S/ \sqrt{n}}  \right \vert \geq z _{\alpha / 2}  }$$   

as needed. ${ \blacksquare }$ 

[**${ p }$-value**]

Consider the above example. 

$${ T _{\alpha / 2} : \quad \text{Reject } \, H _0 \, \text{ if } \, \, \left \vert \frac{\overline{X _n} - \mu _0}{S/ \sqrt{n}}  \right \vert \geq z _{\alpha / 2}  }$$   

Suppose we get a realisation ${ \overline{x}  }$ of ${ \overline{X _n} , }$ and are allowed to vary ${ \alpha . }$ 

**Q**) What are the values of ${ \alpha }$ for which the test rejects ${ H _0 }$? What are the values of ${ \alpha }$ for which the test retains ${ H _0 }$? 

Note that 

$${ {\begin{aligned} &\, \lbrace \alpha : \text{Test rejects } H _0 \rbrace \\ = &\, \left \lbrace \alpha : \left \vert \frac{\overline{x} - \mu _0}{S/ \sqrt{n}}  \right \vert \geq z _{\alpha / 2} \right \rbrace \\ = &\, \left \lbrace \alpha : \frac{\alpha}{2} \geq  \mathbb{P} \left(N(0, 1) \geq  \left \vert \frac{\overline{x} - \mu _0}{S/ \sqrt{n}}  \right \vert \right) \right \rbrace \\ = &\, \left \lbrace \alpha : \alpha \geq \mathbb{P}\left( \vert N(0,1) \vert \geq  \left \vert \frac{\overline{x} - \mu _0}{S/ \sqrt{n}}  \right \vert  \right) \right \rbrace  .  \end{aligned}}  }$$ 

Note that the critical ${ \alpha }$ at which the Test goes from rejecting to retaining is 

$${ \alpha _{\text{crit}} = \mathbb{P}\left( \vert N(0,1) \vert \geq  \left \vert \frac{\overline{x} - \mu _0}{S/ \sqrt{n}}  \right \vert  \right)  .  }$$ 

We call this the observed significance level or the ${ p - }$value of the test. 

Note that generally if ${ \alpha _{\text{crit}} < 0.05 }$ we consider it strong evidence to reject ${ H _0 , }$ and fail to reject otherwise. 






















