---
layout: post
title: "Open Mapping Theorem"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

[Link to previous post: [Link](https://bvenkatakarthik.github.io/Open_Mapping_2026_02_19)] 

**Ref**: “Principles of Analysis” by Junghenn. 

Let ${ \mathscr{X} }$ and ${ \mathscr{Y} }$ be Banach spaces. Let ${ T : \mathscr{X} \to \mathscr{Y} }$ be a continuous linear bijection. Is the inverse ${ T ^{-1} : \mathscr{Y} \to \mathscr{X} }$ also continuous? Note that continuity of ${ T ^{-1} }$ is equivalent to openness of ${ T . }$ 

This motivates the general study of open linear maps. 

Let ${ \mathscr{X} }$ and ${ \mathscr{Y} }$ be Banach spaces. 

[Open Map]    
Let ${ \mathscr{X} }$ and ${ \mathscr{Y} }$ be Banach spaces. Let ${ T : \mathscr{X} \to \mathscr{Y} . }$ We say ${ T }$ is an open map if it takes open sets to open sets. 

**Obs** [Open Map]    
Let ${ \mathscr{X} }$ and ${ \mathscr{Y} }$ be Banach spaces. Let ${ T : \mathscr{X} \to \mathscr{Y} . }$    
Then ${ T }$ is an open map if and only if for each ${ x \in \mathscr{X} }$ and ${ r > 0, }$ the image ${ T(B(x, r)) }$ contains an open ball ${ B(T(x), s) . }$    
**Pf**: ${ \underline{\implies} }$ Clear.    
${ \underline{\impliedby} }$ It suffices to show for every ${ x \in \mathscr{X} }$ and ${ r > 0 , }$ ${ T(B(x, r)) }$ is a union of open balls.    
Let ${ x \in \mathscr{X} }$ and ${ r > 0 . }$ Let ${ y ^{’} \in T(B(x, r)) . }$ We are to show there is an ${ s ^{’} > 0 }$ such that ${ B(y ^{’}, s ^{’}) \subseteq T(B(x, r)) . }$ We will show this.    
Note that there is an ${ x ^{’} \in B(x, r) }$ such that ${ T(x ^{’}) = y ^{’} . }$ Note that there is an ${ r ^{’} > 0 }$ such that ${ B(x ^{’}, r ^{’}) \subseteq B(x, r) . }$ Note that there is an ${ s ^{’} > 0 }$ such that ${ B(T(x ^{’}), s ^{’}) \subseteq T(B(x ^{’}, r ^{’})) .  }$ Now 

$${ B(T(x ^{’}), s ^{’}) \subseteq T(B(x ^{’}, r ^{’})) \subseteq T(B(x, r))  }$$ 

as needed. ${ \blacksquare }$ 

**Obs** [Open Linear Map]    
Let ${ \mathscr{X} }$ and ${ \mathscr{Y} }$ be Banach spaces. Let ${ T : \mathscr{X} \to \mathscr{Y} }$ be a linear map.    
Then ${ T }$ is an open map if and only if ${ T(B(0,1)) \supseteq B(0,t) }$ for some ${ t > 0 . }$ In this case ${ T }$ is surjective.    
**Pf**: ${ \underline{\implies} }$ Clear.    
${ \underline{\impliedby} }$ Let ${ x \in \mathscr{X} }$ and ${ r > 0 . }$ We are to show ${ T(B(x,r)) }$ contains an open ball ${ B(T(x), s) . }$ We will show this.    
Note that 

$${ {\begin{aligned} &\, T(B(x,r)) \\ = &\, T(x + rB(0,1)) \\ = &\, T(x) + r T(B(0,1)) \\ \supseteq &\, T(x) + r B(0,t) \\ = &\, B(T(x), rt)   \end{aligned}}  }$$ 

for some ${ t > 0 , }$ as needed.    

Let ${ T }$ be an open map. We are to show ${ T }$ is surjective.    
Let ${ y \in \mathscr{Y} , y \neq 0. }$ Note that ${ T(B(0,1)) \supseteq B(0,t) }$ for some ${ t > 0 . }$ Note that ${ t \left(y / 2 \lVert y \rVert  \right) }$ lies in ${ B(0,t) . }$ Hence ${ t \left(y / 2 \lVert y \rVert  \right) }$ lies in ${ T(B(0,1)) . }$ Hence ${ y }$ lies in ${ T(\mathscr{X}) , }$ as needed. ${ \blacksquare }$ 

**Thm** [Open Mapping Theorem]    
Let ${ \mathscr{X} }$ and ${ \mathscr{Y} }$ be Banach spaces. Let ${ T \in \mathscr{B}(\mathscr{X}, \mathscr{Y})  }$ be surjective. Then ${ T }$ is an open map.    
**Pf**: Note that by surjectivity 

$${ \mathscr{Y} = \bigcup _{n=1} ^{\infty} T(B(0,n)) .  }$$ 

Hence by Baire Category Theorem, there is a ${ T(B(0,n)) }$ such that ${ \text{cl} \,  T(B(0,n)) }$ ${ = n \text{cl} \, T(B(0,1)) }$ contains an open ball. Note that ${ \text{cl} \,  T(B(0,1)) }$ is a symmetric set around ${ 0 . }$ Hence there is a ${ y _0 \in \mathscr{Y} }$ and ${ \varepsilon > 0 }$ such that 

$${ B(y _0, \varepsilon), -B(y _0, \varepsilon) \subseteq \text{cl} \, T(B(0,1)) . }$$ 

Hence for ${ y \in B(0, \varepsilon) }$ we have ${ y \pm y _0 \in \text{cl} \, T(B(0,1)) . }$ Note that by convexity of ${ \text{cl} \, T(B(0,1)) , }$ the average ${ y \in \text{cl} \, T(B(0,1)) . }$ 

Hence 

$${ B(0, \varepsilon) \subseteq \text{cl} \, T(B(0,1)) . }$$ 

Close enough to our original goal. By the lemma below, we have 

$${ B(0, \varepsilon / 2) \subseteq T(B(0,1))  }$$ 

as needed. ${ \blacksquare }$ 

**Lem** [Ball in ${ \text{cl} \, T(B(0,1)) }$ to Ball in ${ T(B(0,1)) }$]    
Let ${ \mathscr{X} }$ and ${ \mathscr{Y} }$ be Banach spaces. Let ${ T \in \mathscr{B}(\mathscr{X}, \mathscr{Y}) . }$    
Let ${ \varepsilon > 0 }$ be such that ${ B(0, \varepsilon) \subseteq \text{cl} \, T(B(0,1)) . }$    
Then ${ B(0, \varepsilon / 2) \subseteq T(B(0,1)) . }$    
**Pf**: Let ${ y \in B(0, \varepsilon) . }$ By hypothesis, we have ${ y _1 \in B(y, \varepsilon / 2) }$ such that ${ y _1 \in T(B(0,1)) . }$ Note that 

$${ y - y _1 \in B(0, \varepsilon / 2) \subseteq \frac{1}{2} \text{cl} \, T(B(0,1)) . }$$ 

Hence there is a ${ y _2 \in B(y - y _1, \varepsilon / 4) }$ such that ${ y _2 \in T(B(0, 1/2)) . }$ Continuing so, we get a sequence ${ (x _n) }$ such that 

* ${ x _n \in B(0,1 / 2 ^{n-1}) }$ 
* ${ y - \sum _{k=1} ^{n} T(x _k) \in B(0, \varepsilon / 2 ^{n}) . }$ 

Note that ${ x _1 + \ldots + x _n }$ is a Cauchy sequence. Hence it has a limit 

$${  \sum _{k=1} ^{n} x _k \to x,  \, \, \text{ as } n \to \infty . }$$ 

Note that ${ \sum _{k=1} ^{n} T(x _k) }$ converges to ${ y }$ as ${ n \to \infty . }$ By continuity, the limits ${ y = T(x) . }$ Further, ${ \lVert x \rVert }$ ${ \leq \sum _{k=1} ^{\infty} 1/2 ^{k-1} }$ ${ = 2 . }$    
Hence 

$${ B(0, \varepsilon) \subseteq T(B(0, 2)) . }$$ 

Hence 

$${ B(0, \varepsilon / 2) \subseteq T(B(0,1))  }$$ 

as needed. ${ \blacksquare }$ 
