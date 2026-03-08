---
layout: post
title: "Post"
author: "Rational Approximations to Pi"
categories: journal
tags: [documentation,sample]
---

Note that 

$${ \int _0 ^{1} \frac{1}{1+x ^2} \, dx = \frac{\pi}{4} .  }$$ 

This suggests studying inequalities of form 

$${ \boxed{  \int _0 ^{1} \frac{P(x) ^2}{1 + x ^2} \, dx > 0 } }$$ 

where ${ P(x) }$ is a polynomial, to get bounds on ${ \pi . }$ 

Ideally, we want ${ P(x) ^2 }$ to leave a constant remainder on dividing by ${ (1 + x ^2) . }$ 

Let’s write 

$${ P(x) ^2 = (1 + x ^2) Q(x) + R(x) .  }$$ 

Putting ${ x = i }$ we have 

$${ P(x) ^2 = (1 + x ^2) Q(x) + P(i) ^2 . }$$ 

We want ${ P(i) ^2 }$ to be real. 

Suppose for now we want an upper bound on ${ \pi . }$ Hence we can set ${ P(i) }$ to be purely imaginary, to get an upper bound on ${ \pi . }$ (Note that if ${ P(i) }$ is purely imaginary, we have the remainder ${ P(i) ^2 < 0 }$).

We can try 

$${ P(x) = a _4 x ^4 + \ldots + a _1 x + a _0 .  }$$ 

By the ${ P(i) }$ purely imaginary condition we have 

$${ a _4 + a _0 = a _2 .  }$$ 

For simplicity we can look at ${ a _0 = 0 . }$ Hence ${ a _4 = a _2 . }$

By scaling WLOG ${ a _4 = a _2 = 1 . }$ 

Hence consider 

$${ P(x) = x ^4 + a _3 x ^3 +  x ^2 .  }$$ 

Note that 

$${ {\begin{aligned} &\, ( x ^4 + a _3 x ^3 + x ^2 ) ^2 \\ = &\,   (1 + x ^2) (\text{Quotient}) + P(i) ^2 \\ = &\, (1+x ^2) (\text{Quotient}) - a _3 ^2 .  \end{aligned}}  }$$ 

For elegance ${ a _3 = (-2) }$ ensures 

$${ \boxed{ P(x) = x ^2 (1-x) ^2 }  }$$ 

and 

$${ P(x) ^2 = (1+x ^2) (\text{Quotient}) - 4  . }$$ 

It turns out by using this ${ P(x) }$ in 

$${ \int _0 ^{1} \frac{P(x) ^2}{1 + x ^2} \, dx > 0  }$$ 

we get 

$${ \frac{22}{7} - \pi > 0 . }$$ 

Plotting this ${ P(x) ^2 / (1 + x ^2) }$ on ${ [0,1] }$ shows how small the LHS practically is. 

**P.S.** This argument also explains why using 

$${ P(x) = x ^{4k+2} (1-x) ^{4k+2}  }$$

give better and better upper bounds for ${ \pi . }$ (Note that ${ P(i) }$ is purely imaginary, hence the remainder ${ P(i) ^2 < 0}$). 

Link to MathOverflow answer by Geoff Robinson: [Link](https://mathoverflow.net/a/67410/124146).  

The cases 

$${ P(x) = x ^{4k} (1 - x) ^{4k}  }$$

give better and better lower bounds for ${ \pi . }$ (Note that ${ P(i) }$ is purely real, hence the remainder ${ P(i) ^2 \geq 0 }$).

For eg, the ${ k = 1 }$ case, as mentioned in Noam Elkies' MathOverflow post [here](https://mathoverflow.net/q/67384/124146), gives a lower bound on ${ \pi }$:

$${ \int_0^1 (x-x^2)^8 \frac{dx}{1+x^2} = 4\pi - \frac{188684}{15015} > 0 .  }$$ 

