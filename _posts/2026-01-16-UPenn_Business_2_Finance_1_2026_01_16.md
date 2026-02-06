---
layout: post
title: "Business-2 Finance-1"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Ref**: UPenn Coursera courses on Business.

Link to UPenn Coursera page: [Link](https://www.coursera.org/partners/penn). 

Link to UPenn MBA curriculum: [Link](https://mba.wharton.upenn.edu/mba-curriculum/). 

Link to UPenn Finance courses: [Link](https://www.coursera.org/specializations/finance-accounting). 

**ROUGH NOTES (!)**    
Updated: 16/1/26 

**Course-1: Introduction to Finance**

Instructor: Prof. Jessica Wachter. 

Sections:  

The goal is to understand how best to make capital budgeting decisions / investment decisions. (i.e. which projects to undertake, whether they increase or decrease value, etc.) 

The goal is to increase economic value. 

[**Net Present Value**] 

[Back to top] 

Imagine you are running a corporation. How are you going to decide which projects are worth investing in? 

It turns out we use the net present value rule. 

We first consider future value.    
Suppose we deposit ${ \$100 }$ in a bank account that pays ${ 10 \% }$ interest. Then the future value is 

$${ {\begin{aligned} &\, FV \\ = &\, 100 + 100(0.10) \\ = &\, 110. \end{aligned}}  }$$ 

In general, for interest rate ${ r }$ 

$${ FV = 100 (1 + r) . }$$ 

We now consider present value.    
Suppose you need ${ \$ 100 }$ in one year. What do you put aside today? We have 

$${ 100 = PV ( 1 + r) .  }$$ 

Hence 

$${ PV = \frac{100}{1 + r} . }$$ 

In general: Suppose we have a cash flow (CF) equal to ${ c }$ in one year. 

$${ c = CF \text{ in 1 year}.  }$$ 

Then present value 

$${ PV = \frac{c}{1 + r} .  }$$ 

Net present value is 

$${ NPV = C _0 + \frac{C _1}{1 + r}  }$$ 

where ${ C _0 }$ is negative of the cost of investment, and ${ C _1 }$ is the payoff in one year. 

**Eg**: Suppose you are a software developer, and there is a cost / required investment 

$${ \text{Cost} = 0.5M }$$ 

to develop the software, and next year we get a payoff 

$${ \text{Next yr payoff} = 0.54M .  }$$

Then 

$${ NPV = -0.5 + \underbrace{\frac{0.54}{1+r}} _{\text{discount future payoff back to present}}. }$$

We now consider the NPV rule. 

The NPV rule: 

Accept projects if ${ NPV \geq 0 .}$ Reject projects if ${ NPV < 0 . }$ 

The NPV rule maximises the value of the corporation. 

Why does the NPV rule work? 

**Eg**: Consider a corporation of one person, Suzy. Suzy has access to a bank account with ${ r = 20 \% . }$ 

$${ \text{Suzy:} \quad 1 M }$$ 

$${ \text{Bank account} \quad r = 20 \% . }$$ 

She can 

$${ \text{Consume } 1M \text{ now}  }$$

$${ \text{or} }$$

$${ 1.2M \text{ in old age} .  }$$

We have a graph of possibilities (describing the ${ \$ 1 }$ now vs ${ \$ 1.2 }$ later tradeoff). 

<div align="center">
    <img src="https://a.l3n.co/FyCjFq.jpeg" width="400" height="300"/> 
</div>

Suppose she is considering opening a restaurant. 

Suppose 

$${ {\begin{aligned} &\, \text{Restaurant}: \\ &\, \text{Cost}: 0.7 \, \, (\text{in M})  \\ &\, \text{Payoff}: 0.8 . \end{aligned}}  }$$ 

Should she open the restaurant? 

No. Note that ${ 0.7 }$ deposited in the bank becomes ${ 0.84 , }$ which is better than the payoff ${ 0.8 . }$ 

Suppose she is considering buying a vineyard. 

Suppose 

$${ {\begin{aligned} &\, \text{Vineyard}: \\ &\, \text{Cost}: 0.7 \, \, (\text{in M})  \\ &\, \text{Payoff}: 0.91 . \end{aligned}}  }$$ 

Should she invest in the vineyard?

Maybe she is interested in spending the money now, instead of on the vineyard. 

The NPV rule says no matter what her preferences are, she should go for the vineyard. If she wants to spend more now, she could borrow money. We will see this on the graph. 

<div align="center">
    <img src="https://c.l3n.co/FyC4T2.jpeg" width="400" height="500"/> 
</div>

So for example even if she wants to spend more right now, she should buy the vineyard. 

Indeed, as per the NPV rule, 

$${ NPV = C _0 + \frac{C _1}{1 + r} = -0.7 + \frac{0.91}{1.2} > 0  }$$ 

hence she should buy the vineyard. 

We will now consider the separation theorem. 

The separation theorem says we can separate two decisions: 

* When to consume. 

* What projects to choose. 

The second decision is going to be made according to the NPV rule. 

Link to the official notes: [Link](https://drive.google.com/file/d/1usMkDP-J5zqlnF-dMfwpnKcUx_eWaYPU/view?usp=sharing).








