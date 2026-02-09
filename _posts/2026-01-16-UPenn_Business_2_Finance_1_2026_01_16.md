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

<a name="top"></a>

Sections: [Net Present Value](#1); 

The goal is to understand how best to make capital budgeting decisions / investment decisions. (i.e. which projects to undertake, whether they increase or decrease value, etc.) 

The goal is to increase economic value. 

<a name="1"></a>

[**Net Present Value**] 

[Back to top](#top)

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

We will now consider simple vs compound interest. 

Suppose we have ${ \$ 100 . }$ Suppose we invest this in a bank with interest rate ${ r = 7 \% }$ for two years. 

If the bank offers simple interest, 

$${ FV = 100 + 7 + 7 .  }$$ 

If the bank offers compound interest, 

$${ {\begin{aligned} &\, FV \\ = &\, 100 + 7 + (0.07)(100 + 7) \\ = &\, 100 ( 1 + 0.07) (1 + 0.07) . \end{aligned}}  }$$ 

In general if we have compound interest for ${ t }$ years, 

$${  FV = 100 (1 + r) ^t .  }$$

Unless stated otherwise, we consider compound interest. 

Suppose we invest in a bank with interest rate ${ r  }$ for ${ t }$ years. 

What is the present value to be invested such that we get ${ \$ 100 }$ after the ${ t }$ years? 

The present value to get ${ \$100 }$ in ${ t }$ years is given by 

$${ 100 = PV (1 + r) ^t  }$$ 

that is 

$${ PV = \frac{100}{(1 + r) ^t} . }$$ 

We will now consider Annuities and Perpetuities. 

An annuity is defined by equal payments. 

**Eg**: How much would you pay to get ${ \$ 100 }$ a year for ${ 3 }$ years?

Note that

$${ PV = \frac{100}{1+r} + \frac{100}{(1+r) ^2} + \frac{100}{(1 + r) ^3} .  }$$ 

For an annuity lasting ${ t }$ years

$${ {\begin{aligned} &\, PV \\ = &\, \frac{C}{1+r} + \frac{C}{(1+r) ^2} + \ldots + \frac{C}{(1 + r) ^t} \\ = &\, C \frac{1}{1+r} \left( \frac{1 - \frac{1}{(1+r) ^t}}{1 - \frac{1}{1+r}} \right) \\ = &\, C \underbrace{\frac{1}{r} \left( 1 - \frac{1}{(1 + r) ^t} \right)} _{\text{Annuity factor, AF}}  .  \end{aligned}} }$$ 

**Eg**: Consider a ${ 15 }$ year mortgage. The loan amount is ${ 0.5 M . }$ The interest rate is ${ r = 4 \% . }$ 

Each year the cash flow to the bank is ${ C . }$ What is ${ C }$ so that the value to the bank is correct?

We have 

$${ 0.5M = \frac{C}{1+r} + \ldots + \frac{C}{(1+r) ^t} .  }$$ 

We solve for ${ C . }$

Note that the future value of an annuity is 

$${ FV = \underbrace{C \frac{1}{r} \left( 1 - \frac{1}{(1 + r) ^t} \right)} _{PV} (1+r) ^t .   }$$ 

Note that the present value of an annuity is 

$${ PV = C \frac{1}{r} \left( 1 - \frac{1}{(1 + r) ^t} \right) .   }$$ 

Note that as ${ t \to \infty }$, the present value ${ PV \to \frac{C}{r} . }$ 

Hence the PV of a consol (i.e. an annuity as ${ t \to \infty }$) is 

$${ PV = \frac{C}{r} .  }$$ 

**Eg**: Suppose ${ r = 10 \% }$ and ${ C = \$ 100 . }$ How much money would you be willing to pay to get ${ \$ 100 }$ every year forever? 

We have 

$${ PV = \frac{C}{r} = \frac{100}{0.1} = \$ 1000 . }$$ 

We will now consider growing delayed annuities and perpetuities. 

For a growing perpetuity, we have a payment that grows at a fixed rate forever. 

The cash flows are 

<div align="center">
    <img src="https://d.l3n.co/UAZdDZ.png" width="400" height="200"/> 
</div>

Hence 

$${ {\begin{aligned} &\, PV \\ = &\, \frac{C}{1 + r} + \frac{C(1 + g)}{(1 + r) ^2} + \frac{C(1 + g) ^2}{(1 + r) ^3} + \ldots \\ = &\, \frac{\frac{C}{1 + r}}{1 - \frac{1 + g}{1 + r}} \\ = &\, \frac{C}{r - g}  \end{aligned}}  }$$ 

if ${ r > g . }$ 

Consider a delayed perpetuity. 

For a delayed perpetuity, suppose we have a cash flow ${ C }$ every year starting ${ 3 }$ years from now. 

The cash flows are 

<div align="center">
    <img src="https://b.l3n.co/UAZHgC.png" width="400" height="150"/> 
</div>

Hence 

$${ {\begin{aligned} &\, PV \\ = &\, \frac{C}{(1 + r) ^3} + \frac{C}{(1 + r) ^4} + \ldots \\ = &\, \frac{\frac{C}{(1 + r) ^3}}{1 - \frac{1}{1 + r}} \\ = &\, \frac{1}{(1 + r) ^2} \frac{C}{r} .  \end{aligned}}  }$$ 

In general for a perpetuity where CFs (cash flows) begin in ${ t }$ years 

$${ PV = \frac{1}{(1 + r) ^{t - 1}} \frac{C}{r} .  }$$ 

We will now consider compounding within the year and effective annual interest rate. 

**Eg**: A bank offers a stated annual interest rate of ${ 8 \% }$ compounded semiannually. 

If we invested ${ \$ 100 }$ what do we have after ${ 1 }$ year?

The stated annual interest rate 

$${ SAIR = 8 \% \text{ compounded semiannually} .  }$$ 

It means that 

$${ FV = \$ 100 (1 + 0.04) ^2 .  }$$ 

The general formula, if we start from ${ \$ 100 , }$ and divide the year into ${ m }$ parts for compounding, is 

$${ FV = 100 \left(1 + \frac{SAIR}{m} \right) ^m .   }$$ 

Similarly for present value 

$${ PV = 100 \left( 1 + \frac{SAIR}{m} \right) ^{-m} . }$$ 

If we want the above process to go on for ${ t }$ years we have 

$${ FV = 100 \left(1 + \frac{SAIR}{m} \right) ^{mt} }$$ 

and 

$${ PV = 100 \left( 1 + \frac{SAIR}{m} \right) ^{-mt} . }$$ 

Note that as ${ m \to \infty , }$ we have continuous compounding in which  

$${ FV = 100 e^{(SAIR)t}  }$$ 

and 

$${ PV = 100 e ^{- (SAIR) t} . }$$ 

The effective annual interest rate EAR is the rate that when compounded annually produces the same return as SAIR compounded ${ m }$ times a year. 

Hence 

$${ 1 + EAR = \left( 1 + \frac{SAIR}{m} \right) ^m .  }$$ 

Link to the official notes: [Link](https://drive.google.com/file/d/1PTHf_ne1NhT2dWuiX0LNolOiZsAm6MeR/view?usp=sharing). 













