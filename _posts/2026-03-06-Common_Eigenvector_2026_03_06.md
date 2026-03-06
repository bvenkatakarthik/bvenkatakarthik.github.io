---
layout: post
title: "Simultaneous Triangularization"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

[This is a repetition of the answer [here](https://math.stackexchange.com/a/593291/303300)]

**Thm** [Commuting matrices share an eigenvector]    
Let ${ A, B \in \mathbb{C} ^{n \times n} . }$ Suppose ${ AB = BA . }$    
Then ${ A, B }$ share an eigenvector.

**Pf**: Let ${ \lambda }$ be an eigenvalue of ${ A . }$ 

Consider any eigenvector 

$${ v \in \ker(A - \lambda I) .  }$$ 

Note that 

$${ AB v = B A v .  }$$ 

Hence 

$${ A (Bv) = \lambda (Bv) .  }$$ 

Hence 

$${ Bv \in \ker(A - \lambda I)  }$$ 

as well. 

Hence 

$${ \ker(A - \lambda I) \, \text{ is a (nontrivial) B-invariant subspace.} }$$ 

Hence ${ B \vert _{\ker(A - \lambda I)} }$ admits an eigenvector ${ w . }$ 

Note that ${ w }$ is a common eigenvector of ${ A, B , }$ as needed. ${ \blacksquare }$ 
