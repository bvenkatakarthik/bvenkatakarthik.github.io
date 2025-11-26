---
layout: post
title: "QR Algorithm"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Ref**: 

* "Linear Algebra" by Lax. 

* "Matrix Methods" by Strang. Lecture-12. Link to the lecture: [Link](https://youtu.be/d32WV1rKoVk?si=CEHgx2TUDJsy_bNZ).

* "Advanced Scientific Computing" by Rycroft. Lecture-5.6. Link to the lecture: [Link](https://youtu.be/TtPU4KOaQ9A?si=FGiZsiEw37jrkpKN). 

* "Scientific Computing" by Heath. 

**ROUGH NOTES (!)**    
Updated: 25/11/25

Let ${ A \in \mathbb{R} ^{n \times n} }$ be a symmetric matrix. 

**Q**) Can we efficiently compute the eigenvalues of ${ A }$?

It turns out yes. 

It turns out there is the QR algorithm. 

Link to the Wikipedia page: [Link](https://en.wikipedia.org/wiki/QR_algorithm). 

Note that arguably the QR algorithm is one of the top ${ 10 }$ algorithms in the ${ 20 }$th century. 

Link to the journal article by Dongarra, Sullivan: [Link](https://www.computer.org/csdl/magazine/cs/2000/01/c1022/13rRUxBJhBm). 

Link to Higham's top ${ 10 }$ list: [Link](https://press.princeton.edu/ideas/nicholas-higham-on-the-top-10-algorithms-in-applied-mathematics?srsltid=AfmBOoptO29G_k8l-a46W9nuhRMhkj8_mZbG1AS-iO4T1VfE2oEW9wkG). 

[**Power iteration**] 

Let ${ A \in \mathbb{R} ^{n \times n} . }$ 

**Q**) Can we compute the maximum eigenvalue ${ \lambda _1 ,}$ and a corresponding eigenvector ${ v _1 }$?

Suppose ${ A }$ has a unique maximum eigenvalue ${ \lambda _1 , }$ and has a corresponding eigenvector ${ v _1 . }$ 

Suppose there is a basis of eigenvectors ${ (v _1, \ldots, v _n) . }$ 

Pick any ${ x _0 \neq 0  }$ in ${ \mathbb{R} ^n . }$

What is the behaviour of the power iteration 

$${ x _0, x _1 = A x _0, x _2 = A ^2 x _0, \ldots , x _k = A ^k x _0, \ldots  }$$ 

Note that 

$${ {\begin{aligned} &\, x _k \\ = &\,A ^k \left( \sum _{j = 1} ^{n} \alpha _j v _j \right)  \\ = &\, \sum _{j = 1} ^{n} \alpha _j \lambda _j ^k v _j \\ = &\, \lambda _1 ^k \left(\alpha _1 v _1 + \sum _{j \neq 1} \left( \frac{\lambda _j}{\lambda _1} \right) ^k \alpha _j v _j \right) \\ \approx &\, \lambda _1 ^k \alpha _1 v _1 \quad \text{ for large } k . \end{aligned}}  }$$ 

Hence the power iteration in the limit approximates an eigenvector corresponding to the maximum eigenvalue of ${ A . }$ 

[**Subspace iteration**] 

**Q**) Can we use the above power iteration to compute multiple eigenvalue/eigenvector pairs? 

Consider simultaneous iteration 

 * ${ X _0 }$ = arbitrary ${ n \times p }$ matrix of rank ${ p . }$

 * for ${ k = 1, 2, \ldots }$ 

 $${ X _k = A X _{k-1}  }$$

 * end. 

 Note that 

$${ X _k = A ^k X _0 .  }$$ 

 Suppose ${ A }$ has eigenvalues with 

 $${ \vert \lambda _1 \vert >  \ldots >  \vert \lambda _n \vert }$$ 

 and corresponding eigenvectors 

 $${ (v _1, \ldots, v _n) .  }$$ 

  Note that 

$${ X _k = A ^k X _0 .  }$$ 

 Let 

 $${ \mathcal{S} _k = \text{span}(A ^k X _0) }$$ 

 and 

 $${  \mathcal{S} = \text{span}(v _1, \ldots, v _p) . }$$ 

Note that the column ${ (X _k ) _i }$ of ${ X _k }$ is 

$${ {\begin{aligned} &\, (X _k) _i \\ = &\, A ^k (X _0) _i \\ = &\, A ^k \left( \sum _{j = 1} ^{n} \alpha _{i, j} v _j \right) \\ = &\, \sum _{j = 1} ^{n} \alpha _{i, j} \lambda _j ^k v _j \\ = &\, \lambda _p ^{k} \left(\sum _{j = 1} ^{p} \left( \frac{\lambda _j}{\lambda _p}  \right) ^k \alpha _{i, j} v _j + \sum _{j = p + 1} ^{n} \left( \frac{\lambda _j}{\lambda _p}  \right) ^k \alpha _{i, j} v _j \right) \\ \approx &\, \lambda _p ^k \left(\sum _{j = 1} ^{p} \left( \frac{\lambda _j}{\lambda _p}  \right) ^k \alpha _{i, j} v _j \right) \quad \text{ for large } k . \end{aligned}}  }$$ 

Hence ${ X _k }$ converges to a basis of ${ \mathcal{S} = \text{span}(v _1, \ldots, v _p) . }$ 

Note that each basis vector of ${ X _k }$ is very close to ${ v _1 }$ in direction. 

Hence the basis vectors of ${ X _k }$ are very close to being linearly dependent. 

We can resolve this by enforcing linear independence at each step. 

Consider orthogonal iteration 

* ${ X _0 }$ = arbitrary ${ n \times p }$ matrix of rank ${ p . }$
* for ${ k = 0, 1, 2, \ldots }$ 

    * Compute reduced QR factorization   
 
    $${ \boxed{ X _{k} = \hat{Q} _k R _k } .  }$$ 

    * Set    

    $${ \boxed{ X _{k+1}  = A \hat{Q} _k }.  }$$

* end. 

Note that ${ X _k }$ converges to a basis of ${ \mathcal{S} = \text{span}(v _1, \ldots, v _p) . }$  

Note that ${ \hat{Q} _k }$ converges to an orthonormal basis ${ \hat{Q} }$ of ${ \mathcal{S} = \text{span}(v _1, \ldots, v _p) . }$  

Note that for each ${ 1 \leq j \leq p , }$ the first ${ j }$ columns of ${ \hat{Q} }$ is an orthonormal basis of ${ \text{span}(v _1, \ldots, v _j) . }$ 

Hence 

$${ A \hat{Q} = \hat{Q} B }$$ 

with ${ B }$ a ${ p \times p }$ upper triangular matrix.

Hence we can obtain the ${ p }$ largest eigenvalues of ${ A  }$ and the corresponding orthonormal eigenvectors, as needed. 

[**QR iteration**] 

Consider above orthogonal iteration with 

$${ p = n, \quad X _0 = I  . }$$ 

Note that 

$${ \hat{Q} ^T A \hat{Q} \, \,  \text{ is upper triangular.}  }$$ 

Hence we expect 

$${ A _k = \hat{Q} _k ^T A \hat{Q} _k }$$ 

to converge to an upper triangular matrix with eigenvalues on the diagonal.

Hence consider the orthogonal iteration with ${ A _k }$ steps 

* ${ X _0 = I . }$
* for ${ k = 0, 1, 2, \ldots }$ 

    * Compute reduced QR factorization 
   
    $${ \boxed{ X _{k} = \hat{Q} _k R _k }   }$$ 

      and
 
    $${ \boxed{A _k = \hat{Q} _k ^T A \hat{Q} _k}. }$$ 

    * Set  
  
    $${ \boxed{ X _{k+1}  = A \hat{Q} _k }.  }$$

* end. 


Note that 

$${ X _0 = I  . }$$ 

Note that 

$${ X _0 = (\hat{Q} _0 = I) (R _0 = I),   }$$ 

and 

$${ A _0 = A }$$

and 

$${ X _1 = (A \hat{Q} _0 = A) .  }$$ 

Note that 

$${ (X _1 = A) = \hat{Q} _1 R _1  }$$ 

and 

$${ A _1 = (\hat{Q} _1 ^T A) \hat{Q} _1 = R _1 \hat{Q} _1 }$$

and

$${ X _2 = A \hat{Q} _1 .  }$$ 

Can we simplify the next step, involving QR factorization of ${ X _2 ,}$ in terms of ${ A _1 }$? 

Note that 

$${ {\begin{aligned} &\, X _2 \\ = &\, A \hat{Q} _1 \\ = &\, \hat{Q} _1 A _1 \\ = &\, \hat{Q} _1 (Q _2 R ^{'} _2) \quad (\text{QR factorization } A _1 = Q _2 R ^{'} _2)  \end{aligned}}  }$$

Hence 

$${ \hat{Q} _2 = \hat{Q} _1 Q _2, \quad R _2 = R _2 ^{'} .   }$$ 

Hence 

$${ {\begin{aligned} &\, A _2 \\ = &\, \hat{Q} _2 ^T A \hat{Q} _2 \\ = &\, Q _2 ^T \hat{Q} _1 ^T A \hat{Q} _1 Q _2 \\ = &\, Q _2 ^T A _1 Q _2 \\ = &\, Q _2 ^T (Q _2 R _2 ^{'}) Q _2 \\ = &\, R _2 ^{'} Q _2 .  \end{aligned}} }$$ 


And so on. 

Hence consider the QR iteration 

* ${ A _0 = A }$ 
* for ${ k = 1, 2, \ldots }$ 

    * Compute QR factorization 

    $${ A _{k - 1} = Q _k R _k }$$
 
    * Set  

    $${ A _k = R _k Q _k  }$$ 

* end. 

Note that ${ A _k }$s here are ${ A _k = \hat{Q} _k ^T A \hat{Q} _k }$ in the original algorithm. 

Hence ${ A _k }$ converges to an upper triangular matrix with eigenvalues on the diagonal, as needed. 







