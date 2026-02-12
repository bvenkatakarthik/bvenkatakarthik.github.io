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
Updated: 11/2/26 

**Course-1: Introduction to Finance**

Instructor: Prof. Jessica Wachter. 

<a name="top"></a>

Sections: [Net Present Value](#1); [Fixed Income Valuation](#2); 

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

<a name="2"></a>

[**Fixed Income Valuation**] 

[Back to top](#top) 

We will consider bonds. 

A bond is a contract that specifies that a borrower owes a certain sum and the dates in which the interest and the principal will be paid. 

**Eg**: Consider a 5 year bond with a face value of ${ \$ 1000 }$ and a coupon rate of ${ 5 \% . }$ It means: 

* ${ 5 \% }$ of ${ \$ 1000 }$ is paid every year (coupon payment) 

* ${ \$ 1000 }$ is paid at the end. 

A bond is also called a fixed income security. 

Consider zero coupon bonds. A zero coupon bond is a fixed payment at a certain number of years in the furture (i.e.a bond with coupon rate ${ 0 \% }$). 

A zero coupon bond is just a fixed payment at maturity. 

A zero coupon bond is also called a discount bond. (Because the coupon payments are removed). 

We will now discuss valuation of pure discount bonds. 

**Eg**: Consider a bond that has  

$${ \text{Face value} = \$ 1000 }$$ 

$${ \text{Maturity} = 5 \text{ yrs} }$$ 

$${ \text{Bank:} \quad r = 7 \% }$$ 

Note that the price is 

$${ {\begin{aligned} &\, \text{Price} \\ = &\, \frac{1000}{(1.07) ^5} \\ = &\, \$ 712.99 . \end{aligned}}  }$$ 

If price ${ P > \$ 712.99 , }$ nobody would buy the bond. 

If price ${ P < \$ 712.99 , }$ everybody would be trying to buy the bond. 

In either case, market forces send the price back to ${ P = \$ 712.99  . }$ 

**Eg**: Consider a bond that has  

$${ \text{Face value} = \$ 1000 }$$ 

$${ \text{Maturity} = 3 \text{ yrs} }$$ 

$${ \text{Bank:} \quad r = 7 \% }$$ 

Note that the price is 

$${ {\begin{aligned} &\, P \\ = &\, \frac{1000}{(1.07) ^3} \\ = &\, \$ 816.30 . \end{aligned}} }$$ 

**Eg**: Consider a price 

$${ P = \$ 712.99 .  }$$ 

The bond has face value ${ \$ 1000 }$ and maturity ${ 5 }$ years. 

For what ${ r }$ is this price correct? 

We solve for 

$${ P = \frac{F}{(1 + r) ^5} .  }$$ 

Hence 

$${ 712.99 = \frac{1000}{(1 + r) ^5} .  }$$ 

Hence 

$${ r = 7 \%   }$$ 

is the right ${ r . }$ 

This is called the yield to maturity. 

We will now consider yield to maturity vs holding period return. 

What is a return? 

Suppose you have an investment with value ${ v . }$ One possible definition of your return is the percent change in your investment. In that case 

$${ R = \frac{V _t - V _0}{V _0} .  }$$ 

**Eg**: Consider a ${ 5 }$ year bond with a face value ${ F = \$ 1000 }$ and a price ${ P = \$ 712.99 . }$ 

Suppose we take this bond and hold it to maturity. 

Hence ${ V _t = \$ 1000 , }$ and ${ V _0 = \$ 712.99 . }$ Hence the return 

$${ R = \frac{1000}{712.99} - 1 = 40.25 \% .  }$$ 

Consider a ${ 3 }$ yr bond with same face value ${ F = \$ 1000 }$ but price ${ P = \$ 816.30 . }$ (See above bond examples). 

Note that return on the ${ 3 }$ year bond is 

$${ R = \frac{1000}{816.30} - 1 = 22.05 \% .  }$$

Why is the return on the ${ 5 }$ year bond bigger than the return on the ${ 3 }$ year bond? 

It took us ${ 5 }$ years to earn the ${ 40.25 \% }$ returns, versus only ${ 3 }$ years to earn the ${ 22.05 \% }$ returns. Considering time as well, the situation is balanced. 

Hence we need to adjust for the length of time we are holding the investment. 

For a new definition of return, we want to find ${ r }$ such that 

$${  (1 + r) ^t = \frac{V _t}{V _0} . }$$ 

Hence 

$${ r = \left( \frac{V _t}{V _0} \right) ^{1/t} - 1 .  }$$ 

We call this the holding period return (HPR). 

Note that the holding period return is same for both the above bonds, it is ${ r = 7 \% . }$ This is more reasonable. 

Now that we have a definition of return, we will compare it to yield to maturity. 

Note that this above HPR is equal to yield to maturity. 

Recall yield to maturity (YTM) is given by 

$${ \frac{F}{( 1 + YTM) ^t} = P  }$$ 

that is 

$${ YTM = \left(\frac{F}{P} \right) ^{1/t} - 1 .   }$$ 

Hence YTM = HPR if you hold the bond to maturity. 

**Result**: For a zero coupon bond, YTM = HPR if the bond is held to maturity. 

**Eg**: [An example where the bond is not held to maturity]    
Consider a ${ 10 }$ year bond, with face value ${ F = \$ 1000 }$ and price ${ P = \$ 450 . 11 . }$ 

Hence YTM on the bond is 

$${ YTM = \left(\frac{1000}{450.11} \right) ^{1/10} - 1 = 8.31 \% . }$$ 

What happens if you purchase this 10 year bond and sell it after 1 year? 

After 1 year, the bond is a 9 year bond. 

Suppose market conditions have changed and YTMs are higher. Suppose YTM = ${ 8.6 \% . }$ 

Hence the bond sells for a price 

$${ P = \frac{1000}{(1.086) ^9} = \$ 475.92 . }$$ 

Between when you bought the bond and when you sold it, the YTM rose. What happens to holding period return HPR? 

The HPR is 

$${ {\begin{aligned} &\, HPR \\ = &\, \left( \frac{V _t}{V _0} \right) ^{1/t} - 1 \\ = &\, \frac{475.92}{450.11} - 1 \\ = &\, 5.7 \% .  \end{aligned}}  }$$ 

Hence here 

$${ \underbrace{HPR} _{5.7 \%} < \underbrace{YTM} _{8.31 \% } .  }$$ 

If YTMs rise, we get a loss on the bond and ${ HPR < YTM . }$ 

If YTMs fall, ${ HPR > YTM . }$ 

If YTMs stay the same, ${ HPR = YTM . }$ 

Hence Bonds are fixed income not fixed return (Bonds are not risk free investments). A bond is risk free only when you hold the bond till maturity. 

Link to official notes: [Link](https://drive.google.com/file/d/1kF8yIMKV3ssBXGv5bApAH3XM29BKIxbq/view?usp=sharing). 

We will now consider prices and returns on coupon bonds. 

Consider a bond with coupon payment ${ C }$ and face value ${ F . }$ 

Note that the cash flows are 

<div align="center">
    <img src="https://d.l3n.co/UWhFVF.png" width="400" height="200"/> 
</div>

Hence the price on the coupon bond is 

$${ {\begin{aligned} &\, P \\ = &\, \frac{C}{(1+r)} + \frac{C}{(1 + r) ^2} + \ldots + \frac{C+F}{(1 + r) ^t} . \end{aligned}}  }$$ 

The coupon rate is ${ C / F . }$ 

The YTM is the rate (for bank) such that the PV of the bond's payments equals the price. Hence the ${ r }$ in the above formula is the YTM. 

Result: Consider a coupon bond. The bond sells for its face value if and only if YTM = ${ C / F . }$ 

Proof: Note that the bond sells for its face value if and only if 

$${ F = \frac{C}{(1+r)} + \frac{C}{(1 + r) ^2} + \ldots + \frac{C+F}{(1 + r) ^t}  }$$ 

if and only if 

$${ F \left( 1 - \frac{1}{(1 + r) ^t} \right) = C \frac{1}{r} \left( 1 - \frac{1}{(1 + r) ^t} \right)  }$$ 

if and only if 

$${ r = \frac{C}{F}  }$$ 

as needed. 

Note that the ${ P }$ vs ${ r }$ (${ = YTM }$) graph falls with ${ r . }$ 

Note that if ${ YTM > C / F , }$ we have ${ P < F }$ i.e. Bond sells at a discount. 

Note that if ${ YTM < C / F , }$ we have ${ P > F }$ i.e. Bond sells at a premium. 

Note that if ${ YTM = C / F , }$ we have ${ P = F }$ i.e. Bond sells at par. 

Bonds are typically issued at par. The firm will choose the coupon rate equal to pervailing YTM. Over the course, YTM fluctuates, and sometimes bonds sell for a premium and sometimes bonds sell at a discount. 

Consider the HPR for a coupon bond. 

**Eg**: Consider a bond with maturity ${ t = 4 , }$ yield to maturity ${ YTM = 8 \% }$ and face value ${ \$ 1000 . }$ Say the coupon payment ${ C = \$ 80 . }$ Hence the bond sells at par. 

Suppose we hold the bond till maturity. What is HPR? 

Note that 

$${ {\begin{aligned} &\, HPR \\ = &\, \left( \frac{V _4}{V _0} \right) ^{1/4} - 1 \\ = &\, \left( \frac{V _4}{1000} \right) ^{1/4} - 1 \\ = &\, \left( \frac{1360.49}{1000} \right) ^{1/4} - 1 \\ = &\, 8 \% \end{aligned}}  }$$  

Assume we reinvested the coupons at YTM. 

Note that ${ V _4 }$ is 

$${ {\begin{aligned}  &\, V _4 \\ = &\, 1080 + 80(1.08) + 80 (1.08) ^2 + 80(1.08) ^3 \\ = &\, 1360.49 . \end{aligned}} }$$ 

Here is a picture for calculating ${ V _4 }$:


<div align="center">
    <img src="https://b.l3n.co/Ui2Avx.png" width="400" height="250"/> 
</div>

Result: For a coupon bond, YTM = HPR if the bond is held to maturity and the coupons are reinvested at the YTM. 

If you reinvest at ${ < YTM , }$ then ${ HPR < YTM. }$ 

If you reinvest at ${ > YTM, }$ then ${ HPR > YTM. }$ 

Link to official notes: [Link](https://drive.google.com/file/d/1zGRZJ--aPF8I44W48gxXOJbOqO2cqD_i/view?usp=sharing). 

We will now consider semi-annual bonds.

Corporations usually issue semi-annual bonds. 

A semi-annual bond has cash flows that look like: 

<div align="center">
    <img src="https://d.l3n.co/Uiexxq.jpeg" width="400" height="100"/> 
</div>

Hence price 

$${ {\begin{aligned} &\, P \\ = &\, \frac{C/2}{1 + \frac{r _a}{2}} + \frac{C/2}{(1 + \frac{r _a}{2}) ^2} + \frac{C/2}{(1 + \frac{r _a}{2}) ^3} + \ldots + \frac{F + C/2}{(1 + \frac{r _a}{2}) ^{2t}}. \end{aligned}}  }$$ 

We will now consider the yield curve. 

The yield curve depicts the relation between YTM and bond maturity. 

In USA, very short term bonds have YTMs about ${ 2 \% , }$ and the longest term bonds have YTMs about ${ 3 \% . }$ 

<div align="center">
    <img src="https://a.l3n.co/UinjJH.png" width="400" height="200"/> 
</div>

For constructing the yield curve, typically the following bond maturities are considered:

* ${ 1 }$ month, ${ 3 }$ month, ${ 6 }$ month Treasury Bills (Treasury Bills are short term zero coupon bonds). 

* ${ 2 , 3, 5, 10, }$ and ${ 30 }$ year bonds. 

Most of the time, the yield curve is upward sloping. 

Sometimes, it "flattens", i.e. the slopes become smaller. 

Our assumption with above PV calculations is that the yield curve is completely flat / constant. 

Sometimes yield curve takes other shapes. 

<div align="center">
    <img src="https://a.l3n.co/UinIxc.png" width="400" height="250"/> 
</div>

Most of the time, the yield curve is upward sloping. We see higher yields for longer maturity times. 

An inverted yield curve often predicts recessions.

Why is the yield curve upward sloping most of the time? 

Why does an inverted yield curve predicts recessions?

We dont know yet. 

**Eg**: An investment costs ${ 1M . }$ It will pay ${ 0.1 M }$ in 1 yr, ${ 0.35 M }$ in 2 yrs, and ${ 0.6 M }$ in 3 yrs. 

For zero coupon bonds, YTM on 1 yr is ${ 1 \% , }$ the YTM on ${ 2 yr }$ is ${ 1.5 \% }$ and YTM on 3 yr is ${ 4 \% . .}$

Hence 

$${ {\begin{aligned} &\, NPV \\ = &\, -1 + \frac{1}{1.01} + \frac{0.35}{1.015 ^2} + \frac{0.6}{1.04 ^3} \\ < &\, 0 . \end{aligned}}  }$$ 

Hence by the NPV rule we should reject the investment. (The zero coupon bond investments return better).

**Eg**: Suppose you have the following data on zero coupon bond prices (per ${ \$ 100 }$ of face value). 

1 yr bond ${ P _1 = \$ 93.46 }$ 

2 yr bond ${ P _2 = \$ 89 }$ 

3 yr bond ${ P _3 = \$ 83.96 . }$ 

Given this setup, what is the price of a ${ 3 }$ yr coupon bond with ${ C / F = 5 \% }$ per ${ \$ 100 }$ of face value?

**Ans**: The coupon bond has cash flows as expected. 

Note that 

$${ 93.46 = \frac{100}{(1 + r _1)} }$$ 

and 

$${ 89 = \frac{100}{(1 + r _2) ^2} }$$ 

and 

$${ 83.96 = \frac{100}{(1 + r_3) ^3} .  }$$ 

We can use YTMs ${ r _1, r _2, r _3 }$ to find out the price of the ${ 3 }$ yr coupon bond. 

It turns out the answer is ${ \$ 97.28 . }$ 

Link to official notes: [Link](https://drive.google.com/file/d/1O-IfB3XcgMR2KDI_9DXJBwVMwKjH50bi/view?usp=sharing). 



















