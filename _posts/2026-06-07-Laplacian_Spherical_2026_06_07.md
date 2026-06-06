---
layout: post
title: "Laplacian in Spherical Coordinates"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

[This is a brute-force way to compute the Laplacian in spherical coordinates.] 

**Refs**: 

* "Advanced Engineering Mathematics" by Kreyszig. 

* Youtube video: "Converting the Laplacian to Spherical Coords" by Todd Yilk. Link to the video: [Link](https://youtu.be/-odVYy5PO1Q?si=4ffhwX3BIoqmQVZi).

[**Spherical Coordinates**] 

Recall Spherical Coordinates 

<div align="center">
    <img src="https://b.l3n.co/cPIOwF.png" width="400"/> 
</div>

Note that spherical to cartesian conversion is 

$${ x = r \cos(\theta) \sin(\phi), \quad y = r \sin(\theta) \sin(\phi), \quad z = r \cos(\phi) .  }$$ 

Note that cartesian to spherical "conversion" is 

$${ r = \sqrt{x ^2 + y ^2 + z ^2}, \quad \cos(\theta) = \frac{x}{\sqrt{x ^2 + y ^2}} , \quad \cos(\phi) = \frac{z}{\sqrt{x ^2 + y ^2 + z ^2}} .  }$$ 

[**Laplacian in spherical coordinates**] 

Consider a scalar function ${ u . }$ 

**Q**) **Can we express the Laplacian** 

$${ \nabla ^2 u = u _{xx} + u _{yy} + u _{zz} }$$ 

**in terms of the derivatives of ${ u }$ wrt ${ r, \theta, \phi }$?** 

Note that 

$${ {\begin{aligned} &\, u _x \\ = & u _r r _x + u _{\theta} \theta _{x} + u _{\phi} \phi _{x} . \end{aligned}} }$$ 

Hence 

$${ {\begin{aligned} &\,  u _{xx} \\ = &\, (u _r r _x) _x + (u _{\theta} \theta _{x}) _{x} + (u _{\phi} \phi _x) _{x} \\ = &\, u _{rx} r _{x} + u _r r _{xx} + u _{\theta x} \theta _{x} + u _{\theta} \theta _{xx} + u _{\phi x} \phi _{x} + u _{\phi} \phi _{xx} \\ = &\, (u _{rr} r _x + u _{r\theta} \theta _{x}  + u _{r \phi} \phi _{x}) r _x \\ + &\, u _{r} r _{xx} \\ + &\, (u _{\theta r} r _x + u _{\theta \theta} \theta _x + u _{\theta \phi} \phi _{x} ) \theta _x \\ + &\, u _{\theta} \theta _{xx} \\ + &\, (u _{\phi r} r _x + u _{\phi \theta} \theta _x + u _{\phi \phi} \phi _x) \phi _x \\ + &\, u _{\phi} \phi _{xx} \\ = &\, { \begin{pmatrix} r _{xx} &\theta _{xx} &\phi _{xx} \end{pmatrix} }  {\begin{pmatrix} u _{r} \\ u _{\theta} \\ u _{\phi} \end{pmatrix}} + {\begin{pmatrix} r _{x} &\theta _{x} &\phi _{x} \end{pmatrix}} {\begin{pmatrix} u _{rr} &u _{r \theta} &u _{r \phi} \\ u _{\theta r} &u _{\theta \theta} &u _{\theta \phi} \\ u _{\phi r} &u _{\phi \theta} &u _{\phi \phi}  \end{pmatrix}} {\begin{pmatrix} r _{x} \\ \theta _{x} \\ \phi _{x} \end{pmatrix}} .    \end{aligned}}  }$$ 

Likewise for ${ u _{yy}, u _{zz}. }$ 

Hence the Laplacian 

$${ {\begin{aligned} &\, \nabla ^2 u \\ = &\, \sum _{\nu = x, y, z} u _{\nu \nu}  \\ = &\,  \sum _{\nu = x, y, z} { \begin{pmatrix} r _{\nu \nu} &\theta _{\nu \nu} &\phi _{\nu \nu} \end{pmatrix} }  {\begin{pmatrix} u _{r} \\ u _{\theta} \\ u _{\phi} \end{pmatrix}} + \sum _{\nu = x, y, z} {\begin{pmatrix} r _{\nu} &\theta _{\nu} &\phi _{\nu} \end{pmatrix}} {\begin{pmatrix} u _{rr} &u _{r \theta} &u _{r \phi} \\ u _{\theta r} &u _{\theta \theta} &u _{\theta \phi} \\ u _{\phi r} &u _{\phi \theta} &u _{\phi \phi}  \end{pmatrix}} {\begin{pmatrix} r _{\nu} \\ \theta _{\nu} \\ \phi _{\nu} \end{pmatrix}}.  \end{aligned}}  }$$ 

Note that **atleast in the positive octant** 

$${ {\begin{aligned} &\, r _x = \frac{x}{\sqrt{x ^2 + y ^2 + z ^2}}, \\ &\, \left( \frac{-y}{\sqrt{x ^2 + y ^2}} \right) \theta _x = \frac{\sqrt{x ^2 + y ^2} - x \left( \frac{x}{\sqrt{x ^2 + y ^2}} \right)}{x ^2 + y ^2}, \\ &\, \left( \frac{- \sqrt{x ^2 + y ^2}}{\sqrt{x ^2 + y ^2 + z ^2}} \right) \phi _x  = \frac{-z \frac{x}{\sqrt{x ^2 + y ^2 + z ^2}}}{x ^2 + y ^2 + z ^2} \end{aligned}}  }$$ 

Hence 

$${ {\begin{aligned} &\, r _x = \frac{x}{\sqrt{x ^2 + y ^2 + z ^2}}, \\ &\,  \theta _x = \frac{-y}{x ^2 + y ^2} , \\ &\, \phi _{x} = \frac{zx}{(x ^2 + y ^2 + z ^2) \sqrt{x ^2 + y ^2}} . \end{aligned}} }$$ 

That is 

$${ {\begin{aligned} &\, r _x =  \frac{r \cos(\theta) \sin(\phi)}{r} , \\ &\, \theta _{x} = \frac{- r \sin(\theta) \sin(\phi) }{r ^2  \sin(\phi) ^2}, \\ &\, \phi _{x} = \frac{(r \cos(\phi)) (r \cos(\theta) \sin(\phi))}{r ^2 (r \sin(\phi)) }.   \end{aligned}} }$$ 

That is 

$${ \boxed{ {\begin{aligned} &\, r _x =  \cos(\theta) \sin(\phi) , \\ &\, \theta _{x} = \frac{- \sin(\theta)}{r \sin(\phi)} , \\ &\, \phi _{x} = \frac{\cos(\phi) \cos(\theta)}{r } .   \end{aligned}} } }$$ 

Hence 

$${ {\begin{aligned} &\, r _{xx} =  - \sin(\theta) \sin(\phi) \theta _{x} + \cos(\theta) \cos(\phi) \phi _{x},  \\ &\, \theta _{xx} = \frac{- \cos(\theta) \theta _{x} r \sin(\phi) + \sin(\theta) (r _{x} \sin(\phi) + r \cos(\phi) \phi _{x} ) }{r ^2 \sin(\phi) ^2} , \\ &\, \phi _{xx} = \frac{(- \sin(\phi) \phi _{x} \cos(\theta) - \cos(\phi) \sin(\theta) \theta _{x} )r - \cos(\phi) \cos(\theta) r _{x}}{r ^2} .  \end{aligned}}  }$$ 

That is 

$${ {\begin{aligned} &\, r _{xx} = \frac{(\sin(\theta)) ^2}{r} + \frac{(\cos(\theta)) ^2 (\cos(\phi)) ^2}{r} , \\ &\, \theta _{xx} = \frac{\sin(\theta) \cos(\theta)}{r ^2 \sin ^2 (\phi) } + \frac{\sin(\theta) \cos(\theta)}{r ^2} + \frac{1}{r ^2} \cot ^{2} (\phi) \sin(\theta) \cos(\theta), \\ &\, \phi _{xx} = \frac{- \sin(\phi) \cos(\phi) \cos ^2 (\theta)}{r ^2} + \frac{\cot (\phi) \sin ^2 (\theta)}{r ^2} - \frac{ \sin(\phi) \cos(\phi) \cos ^2 (\theta)}{r ^2} .   \end{aligned}}  }$$ 

That is 

$${ \boxed{ {\begin{aligned} &\, r _{xx} = \frac{(\sin(\theta)) ^2}{r} + \frac{(\cos(\theta)) ^2 (\cos(\phi)) ^2}{r} , \\ &\, \theta _{xx} = \frac{\sin(\theta) \cos(\theta)}{r ^2 \sin ^2 (\phi) } + \frac{\sin(\theta) \cos(\theta)}{r ^2} + \frac{1}{r ^2} \cot ^{2} (\phi) \sin(\theta) \cos(\theta), \\ &\, \phi _{xx} = \frac{- 2 \sin(\phi) \cos(\phi) \cos ^2 (\theta)}{r ^2} + \frac{\cot (\phi) \sin ^2 (\theta)}{r ^2} .   \end{aligned}} }  }$$ 

Note that **atleast in the positive octant** 

$${ {\begin{aligned} &\, r _y = \frac{y}{\sqrt{x ^2 + y ^2 + z ^2}}, \\ &\, \left( \frac{-y}{\sqrt{x ^2 + y ^2}} \right) \theta _{y} = \frac{-xy}{(x ^2 + y ^2) ^{3/2}}, \\ &\, \left( \frac{- \sqrt{x ^2 + y ^2}}{\sqrt{x ^2 + y ^2 + z ^2}} \right) \phi _{y}  = \frac{-yz}{(x ^2 + y ^2 + z ^2) ^{3/2}} .  \end{aligned}}  }$$ 

Hence 

$${  {\begin{aligned} &\, r _y = \frac{y}{\sqrt{x ^2 + y ^2 + z ^2}}, \\ &\,  \theta _{y} = \frac{x}{x ^2 + y ^2}, \\ &\,  \phi _{y}  = \frac{yz}{(x ^2 + y ^2 + z ^2) \sqrt{x ^2 + y ^2}} .  \end{aligned}}   }$$ 

That is 

$${ {\begin{aligned} &\, r _y = \frac{r \sin(\theta) \sin(\phi)}{r}, \\ &\,  \theta _{y} = \frac{r \cos(\theta) \sin(\phi)}{r ^2 \sin ^2 (\phi)}, \\ &\,  \phi _{y}  = \frac{(r \sin(\theta) \sin(\phi)) (r \cos(\phi))}{r ^2 (r \sin(\phi)) } .  \end{aligned}} }$$ 

That is 

$${ \boxed{ {\begin{aligned} &\, r _y = \sin(\theta) \sin(\phi), \\ &\,  \theta _{y} = \frac{\cos(\theta)}{r  \sin (\phi)}, \\ &\,  \phi _{y}  = \frac{\sin(\theta) \cos(\phi)}{r } .  \end{aligned}} } }$$ 

Hence 

$${ {\begin{aligned} &\, r _{yy} = \cos(\theta) \theta _{y} \sin(\phi) + \sin(\theta) \cos(\phi) \phi _{y} , \\ &\, \theta _{yy} = \frac{- \sin(\theta) \theta _{y} r \sin(\phi) - \cos(\theta) (r _{y} \sin(\phi) + r \cos(\phi) \phi _{y}) }{r ^2 \sin ^2 (\phi) }, \\ &\, \phi _{yy} = \frac{(\cos(\theta) \theta _{y} \cos(\phi) - \sin(\theta) \sin(\phi) \phi _{y} ) r - (\sin(\theta) \cos(\phi)) r _{y} }{r ^2} . \end{aligned}}  }$$ 

That is 

$${ {\begin{aligned} &\, r _{yy} = \frac{\cos ^2 (\theta)}{r} + \frac{1}{r} \sin ^2 (\theta) \cos ^2 (\phi)  , \\ &\, \theta _{yy} = \frac{- \sin(\theta) \cos(\theta)}{r ^2 \sin ^2 (\phi)} + \frac{- \sin(\theta) \cos(\theta)}{r ^2} + \frac{- \sin(\theta) \cos(\theta) \cot ^2 (\phi)}{r ^2} , \\ &\, \phi _{yy} = \frac{\cos ^2 (\theta) \cot (\phi)}{r ^2} + \frac{- \sin ^2 (\theta) \sin(\phi) \cos(\phi)}{r ^2} + \frac{- \sin ^2 (\theta) \sin(\phi) \cos(\phi)}{r ^2} . \end{aligned}}  }$$ 

That is 

$${ \boxed{  {\begin{aligned} &\, r _{yy} = \frac{\cos ^2 (\theta)}{r} + \frac{1}{r} \sin ^2 (\theta) \cos ^2 (\phi)  , \\ &\, \theta _{yy} = \frac{- \sin(\theta) \cos(\theta)}{r ^2 \sin ^2 (\phi)} + \frac{- \sin(\theta) \cos(\theta)}{r ^2} + \frac{- \sin(\theta) \cos(\theta) \cot ^2 (\phi)}{r ^2} , \\ &\, \phi _{yy} = \frac{\cos ^2 (\theta) \cot (\phi)}{r ^2} + \frac{-  2 \sin ^2 (\theta) \sin(\phi) \cos(\phi)}{r ^2} . \end{aligned}} } }$$ 

Note that **atleast in the positive octant** 

$${ {\begin{aligned} &\, r _z = \frac{z}{\sqrt{x ^2 + y ^2 + z ^2}}, \\ &\, \theta _{z} = 0, \\ &\, \left( \frac{- \sqrt{x ^2 + y ^2}}{\sqrt{x ^2 + y ^2 + z ^2}} \right) \phi _{z}  = \frac{x ^2 + y ^2}{(x ^2 + y ^2 + z ^2) ^{3/2}} .  \end{aligned}}  }$$ 

Hence 

$${ {\begin{aligned} &\, r _z = \frac{z}{\sqrt{x ^2 + y ^2 + z ^2}}, \\ &\, \theta _{z} = 0, \\ &\,  \phi _{z}  = \frac{- \sqrt{x ^2 + y ^2}}{(x ^2 + y ^2 + z ^2)} .  \end{aligned}} }$$ 

That is 

$${ {\begin{aligned} &\, r _z = \frac{r \cos(\phi)}{r}, \\ &\, \theta _{z} = 0, \\ &\,  \phi _{z}  = \frac{- r \sin(\phi)}{r ^2} .  \end{aligned}} }$$ 

That is 

$${ \boxed{  {\begin{aligned} &\, r _z = \cos(\phi), \\ &\, \theta _{z} = 0, \\ &\,  \phi _{z}  = \frac{-  \sin(\phi)}{r} .  \end{aligned}} } }$$ 

Hence 

$${ {\begin{aligned} &\, r _{zz} = - \sin(\phi) \phi _{z}, \\ &\, \theta _{zz} = 0, \\ &\, \phi _{zz} = \frac{- \cos(\phi) \phi _{z} r + \sin(\phi) r _{z}}{r ^2} .  \end{aligned}}  }$$ 

That is 

$${ \boxed{ {\begin{aligned} &\, r _{zz} = \frac{\sin ^2 (\phi)}{r}, \\ &\, \theta _{zz} = 0, \\ &\, \phi _{zz} = \frac{2 \sin(\phi) \cos(\phi)}{r ^2} .  \end{aligned}} }  }$$ 

We are now ready to express ${ \nabla ^2 u }$ in spherical coordinates. 

Note that 

$${ {\begin{aligned} &\, \nabla ^2 u \\ = &\, \sum _{\nu = x, y, z} u _{\nu \nu}  \\ = &\,  \sum _{\nu = x, y, z} { \begin{pmatrix} r _{\nu \nu} &\theta _{\nu \nu} &\phi _{\nu \nu} \end{pmatrix} }  {\begin{pmatrix} u _{r} \\ u _{\theta} \\ u _{\phi} \end{pmatrix}} + \sum _{\nu = x, y, z} {\begin{pmatrix} r _{\nu} &\theta _{\nu} &\phi _{\nu} \end{pmatrix}} {\begin{pmatrix} u _{rr} &u _{r \theta} &u _{r \phi} \\ u _{\theta r} &u _{\theta \theta} &u _{\theta \phi} \\ u _{\phi r} &u _{\phi \theta} &u _{\phi \phi}  \end{pmatrix}} {\begin{pmatrix} r _{\nu} \\ \theta _{\nu} \\ \phi _{\nu} \end{pmatrix}}.  \end{aligned}}  }$$ 

We will look at each term separately. 

Note that 

$${ {\begin{aligned} &\, u _{r} \text{ term} \\ = &\, u _{r} \sum _{\nu = x, y, z} r _{\nu \nu} \\ = &\, \frac{2}{r} u _{r} . \end{aligned}}  }$$ 

Note that 

$${ {\begin{aligned} &\, u _{\theta} \text{ term} \\ = &\, u _{\theta} \sum _{\nu = x, y, z} \theta _{\nu \nu} \\ = &\, 0  . \end{aligned}}  }$$ 

Note that 

$${ {\begin{aligned} &\, u _{\phi} \text{ term} \\ = &\, u _{\phi} \sum _{\nu = x, y, z} \phi _{\nu \nu} \\ = &\, \frac{\cot(\phi)}{r ^2} u _{\phi} .   . \end{aligned}}  }$$ 

Note that 

$${ {\begin{aligned} &\, u _{rr} \text{ term} \\ = &\, u _{rr} \sum _{\nu = x, y, z} r _{\nu} ^{2} \\ = &\, u _{rr} .  \end{aligned}}  }$$ 

Note that 

$${ {\begin{aligned} &\, u _{r\theta} \text{ term} \\ = &\, 2 u _{r \theta} \sum _{\nu = x, y, z} r _{\nu} \theta _{\nu} \\ = &\, 0  .  \end{aligned}} }$$ 

Note that 

$${ {\begin{aligned} &\, u _{r\phi} \text{ term} \\ = &\, 2 u _{r \phi} \sum _{\nu = x, y, z} r _{\nu} \phi _{\nu} \\ = &\, 0  .  \end{aligned}} }$$ 

Note that 

$${ {\begin{aligned} &\, u _{\theta \theta} \text{ term} \\ = &\,  u _{\theta \theta} \sum _{\nu = x, y, z} \theta _{\nu} ^{2} \\ = &\, \frac{1}{r ^2 \sin ^{2} (\phi)} u _{\theta \theta}  .  \end{aligned}} }$$ 

Note that 

$${ {\begin{aligned} &\, u _{\theta \phi} \text{ term} \\ = &\,  u _{\theta \phi} \sum _{\nu = x, y, z} \theta _{\nu} \phi _{\nu} \\ = &\, 0  .  \end{aligned}} }$$ 

Note that 

$${ {\begin{aligned} &\, u _{\phi \phi} \text{ term} \\ = &\,  u _{\phi \phi} \sum _{\nu = x, y, z} \phi _{\nu} ^{2} \\ = &\, \frac{1}{r ^2} u _{\phi \phi}   .  \end{aligned}}  }$$ 

Hence 

$${ \boxed{ {\begin{aligned} &\, \nabla ^{2} u \\ = &\, \frac{2}{r} u _{r} + \frac{\cot(\phi)}{r ^2} u _{\phi} + u _{rr} + \frac{1}{r ^2 \sin ^{2} (\phi)} u _{\theta \theta} + \frac{1}{r ^2} u _{\phi \phi}  \end{aligned}} }  }$$ 

Equivalently, clubbing "${ u _{r} }$ and ${ u _{rr} }$ terms" and "${ u _{\phi} }$ and ${ u _{\phi \phi} }$ terms", we have 

$${ \boxed{ {\begin{aligned} &\, \nabla ^{2} u \\ = &\, \frac{1}{r ^2} \frac{\partial}{\partial r} \left(r ^2 \frac{\partial u}{\partial r}  \right) + \frac{1}{r ^2 \sin(\phi)} \frac{\partial}{\partial \phi}  \left( \sin (\phi) \frac{\partial u}{\partial \phi} \right) + \frac{1}{r ^2 \sin ^2 (\phi)} \frac{\partial ^{2} u}{\partial \theta ^{2}}   \end{aligned}} }  }$$ 

as needed. 



















