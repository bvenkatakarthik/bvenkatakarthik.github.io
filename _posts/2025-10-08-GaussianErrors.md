---
layout: post
title: "Gaussian Errors"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

Consider the plane ${ \mathbb{R} ^2 . }$ Consider the origin ${ (0, 0) . }$ 

Consider the natural error generating process:
* The random error vector is ${ \mathcal{E} = (\varepsilon _1, \varepsilon _2) . }$ 
* The components ${ \varepsilon _1, \varepsilon _2 }$ are independent and identically distributed. 
* The distribution of ${ \mathcal{E} }$ is rotationally symmetric. 

**Q**) What is the distribution of the random error vector ${ \mathcal{E} }$? 

Let ${ f(x, y) }$ be the density of ${ \mathcal{E} . }$ 

Let ${ f(x) }$ be the density of the components ${ \varepsilon _1 , \varepsilon _2 . }$ 

Note that by independence of components 

$${ f(x, y) = f(x) f(y) .  }$$ 

Note that by rotational symmetry of ${ f(x, y) }$ 

$${ f(x, y) = g(x ^2 + y ^2) .  }$$ 

Hence 

$${  \boxed{f(x, y) = f(x) f(y) = g(x ^2 + y ^2) }.  }$$ 

Note that it suffices to find the expression of ${ g . }$ 

Note that 

$${ f(x) f(0) = g(x ^2) .  }$$ 

Note that 

$${ f(0) ^2 = g(0) .  }$$ 

Hence 

$${ f(x) = \frac{1}{\sqrt{g(0)}} g (x ^2) .  }$$ 

Hence 

$${ \frac{1}{\sqrt{g(0)}} g (x ^2) \frac{1}{\sqrt{g(0)}} g (y ^2) = g(x ^2 + y ^2) .  }$$ 

Hence 

$${  g(x ^2) g(y ^2) = g(0) g(x ^2 + y ^2) . }$$ 

Hence 

$${ g(t _1) g(t _2) = g(0) g(t _1 + t _2)  }$$ 

for ${ t _1, t _2 > 0 . }$ 

Hence 

$${ g(t) = A e ^{kt} .  }$$ 

Hence ${ f(x, y) }$ is of the form 

$${ \boxed{ f(x, y) = A e ^{k(x ^2 + y ^2)} } .   }$$ 

Note that ${ k < 0 . }$ 

Hence ${ f(x, y) }$ is of the form 

$${ \boxed{f(x, y) = \frac{1}{2 \pi \sigma ^2} e ^{- \frac{x ^2 + y ^2}{2 \sigma ^2}} }  .  }$$ 

We call this a Gaussian distribution. 








