---
layout: post
title: "Dual Cones"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Ref**: 
* "Convex Optimization" by Boyd, Vandenberghe. 
* "Convex Optimization" by Boyd. Lecture-2. Link to lecture: [Lecture](https://youtu.be/1menqhfNzzo?si=CWPtv4j8ZTl1SBxI&t=856).

[**Dual cones**]

Note that cones can be used to induce inequalities. Link to Stackexchange post: [Link](https://math.stackexchange.com/a/5103418/303300). 

Consider ${ \mathbb{R} ^n . }$ Let ${ K \subseteq \mathbb{R} ^n }$ be a cone. 

Consider the dual space 

$${ (\mathbb{R} ^n)^{\ast} := \lbrace x ^T (\cdot) : x \in \mathbb{R} ^n \rbrace .  }$$ 

Note that ${ (\mathbb{R} ^n) ^{\ast} }$ has the norm 

$${ \lVert x ^T (\cdot) \rVert := \sup \lbrace x ^T (y) : \lVert y \rVert = 1 \rbrace  .  }$$ 

Note that 

$${ \lVert x ^T (\cdot) \rVert = \lVert x \rVert .  }$$ 

**Q**) What are all the elements of ${ (\mathbb{R} ^n) ^{\ast} }$ which respect ${ \preceq _K }$? 

Equivalently

**Q**) What is 

$${   \lbrace \lambda ^T (\cdot) : x {\preceq _K} y \implies \lambda ^T (x) \leq \lambda ^T (y) \rbrace  .  }$$ 

Note that the set is 

$${ {\begin{aligned} &\, \lbrace \lambda ^T (\cdot) : x {\preceq _K} y \implies \lambda ^T (x) \leq \lambda ^T (y) \rbrace \\ = &\, \lbrace \lambda ^T (\cdot) : \lambda ^T (y - x) \geq 0 \text{ for all } y - x \in K \rbrace \\ = &\, \lbrace \lambda ^T (\cdot) : \lambda ^T z \geq 0 \text{ for all } z \in K \rbrace .  \end{aligned}}  }$$ 

We call 

$${ \boxed{ K ^{\ast} = \lbrace \lambda : \lambda ^T z \geq 0 \text{ for all } z \in K \rbrace }   }$$ 

as the dual cone of ${ K . }$ 

Note that geometrically, ${ \lambda \in K ^{\ast} }$ means ${ (-\lambda) }$ is a normal vector of a supporting hyperplane of ${ K  }$ at ${ 0 . }$ 

**Thm**: Consider ${ \mathbb{R} ^n . }$ Let ${ K \subseteq \mathbb{R} ^n }$ be a proper cone. Then 

$${ x {\preceq _K} y \iff \lambda ^T (x) \leq \lambda ^T (y) \, \, \text{ for all } \lambda \in K ^{\ast}  .  }$$ 

**Pf**: ${ \underline{\implies} }$ Note that it is true by definition of ${ K ^{\ast} . }$ 

${ \underline{\impliedby} }$ Suppose 

$${ \lambda ^T (y - x) \geq 0 \quad \text{ for all } \lambda \in K ^{\ast} .  }$$ 

Hence 

$${ (y - x) \in K ^{\ast \ast} .  }$$

Note that by the below theorem 

$${ K ^{\ast \ast} = K .  }$$ 

Hence 

$${ (y - x) \in K  }$$ 

as needed. ${ \blacksquare }$ 

[**${ K ^{\ast \ast} = K }$**] 

**Thm**: Let ${ K \subseteq \mathbb{R} ^n }$ be a proper cone. Then 

$${ K ^{\ast \ast} = K  . }$$ 

**Pf**: Note that ${ K }$ is the intersection of all homogeneous half spaces containing ${ K . }$ 

Hence 

$${ {\begin{aligned} &\, K \\ = &\, \bigcap _{\lambda \in K ^{\ast}} \lbrace x : (- \lambda) ^T x \leq 0 \rbrace \\ = &\, \bigcap _{\lambda \in K ^{\ast}} \lbrace x : \lambda ^T x \geq 0 \rbrace \\ = &\, \lbrace x : \lambda ^T x \geq 0 \text{ for all } \lambda \in K ^{\ast} \rbrace \\ = &\, K ^{\ast \ast} .  \end{aligned}}  }$$ 

Hence 

$${  K ^{\ast \ast} = K }$$ 

as needed. ${ \blacksquare }$ 






