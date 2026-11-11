---
layout: post
title: "MLS-4 Logistic Regression"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Ref**: 

* CodeSignal's "Implementing AI algorithms from scratch" course. Link to the course: [Link](https://codesignal.com/learn/paths/implementing-ai-algorithms-from-scratch).  

* MIT Machine Learning course. Link to the course: [Link](https://learn.mit.edu/courses/course-v1:MITxT+6.86x). 

* Stanford Machine Learning course. Link to the course: [Link](https://cs229.stanford.edu/). 

Machine Learning from Scratch - 4. 

Logistic Regression. 

**ROUGH NOTES (!)**    
Updated: 11/11/2026 

We'll now consider the problem of Classification. 

So far, we've dealt with tasks where a continuous output needs prediction based on one or more input variables- these tasks are known as regression tasks. 

There is another category of tasks known as classification tasks, where the objective is to predict a categorical outcome. These categories are often binary, like "spam"/"not spam" for an email or "malignant"/"benign" for a tumor. 

Logistic regression is a classification algorithm that can predict the probability of a binary outcome.

Consider the post: [Link](https://stats.stackexchange.com/a/672232/319581). 

Hence to recall this is the setup. 

Suppose we have ${ n }$ data points, each with ${ m }$ features and one corresponding ${ y \in \lbrace 0, 1 \rbrace  }$ value. 

The data looks like ${ \lbrace (\mathbf{x} _1, y _1), \ldots, (\mathbf{x} _n, y _n) \rbrace .  }$ 

We can arrange the feature values in a matrix 

$${ \mathbf{X} = \begin{pmatrix} 1 &x _{1,1} &\cdots &x _{1,m} \\ 1 &x _{2, 1} &\cdots &x _{2, m} \\ \vdots &\vdots &\ddots &\vdots \\ 1 &x _{n,1} &\cdots &x _{n, m} \end{pmatrix} .  }$$
Here each row represents the ${ m }$ features for a single data point. 

For each row, there is a corresponding ${ y }$ value. We can arrange these ${ y }$ values like 

$${ \mathbf{y} = \begin{pmatrix} y _1 \\ \vdots \\ y _n \end{pmatrix} , \quad \text{Each } y _i \in \lbrace 0, 1 \rbrace .  }$$ 

We consider the model generating the labels to be 

$${ {\begin{aligned} &\, (y \vert \mathbf{x}, \theta) \text{ is Bernoulli, } \\ &\, p(y = 1 \vert \mathbf{x}, \theta) =  \sigma  \left( \theta ^T \overset{\circ}{\mathbf{x}} \right)  \end{aligned}} .   }$$ 

Note that ${ \overset{\circ}{\mathbf{x}} }$ is ${ \mathbf{x} }$ with ${ 1 }$ appended to it. 

Note that ${ \sigma }$ is the sigmoid function 

$${ \sigma(t) = \frac{1}{1 + e ^{-t}} .  }$$ 

Now we want to estimate ${ \theta }$ from the data and the model.  

We will now do maximum likelihood estimation with respect to the random variable ${ (y \vert \mathbf{x}, \theta) . }$ 

The likelihood function for the data is 

$${ {\begin{aligned} & L(\theta) \\ = &\, \prod _{i = 1} ^{n} p(y = y _i \vert \mathbf{x} = \mathbf{x} _i, \theta) \\ = &\, \prod _{i = 1} ^{n} \sigma \left( \theta ^T \overset{\circ}{\mathbf{x} _i} \right) ^{y _i} \left( 1 - \sigma \left( \theta ^T \overset{\circ}{\mathbf{x} _i} \right) \right) ^{1 - y _i} .  \end{aligned}}  }$$ 

Hence the log likelihood for the data is 

$${ {\begin{aligned} &\, \ell(\theta) \\ = &\, \sum _{i = 1} ^{n} y _i \log \left( \sigma \left( \theta ^T \overset{\circ}{\mathbf{x} _i} \right) \right) + (1 - y _i) \left( 1 - \sigma \left( \theta ^T \overset{\circ}{\mathbf{x} _i} \right) \right) \end{aligned}} }$$ 

Now maximizing the log likelihood is equivalent to minimizing the cost 

$${ {\begin{aligned} &\, J(\theta) \\ = &\, \frac{1}{n} \sum _{i = 1} ^{n} - \left[ y _i \log \left( \sigma \left( \theta ^T \overset{\circ}{\mathbf{x} _i} \right) \right) + (1 - y _i) \left( 1 - \sigma \left( \theta ^T \overset{\circ}{\mathbf{x} _i} \right) \right) \right] . \end{aligned}}    }$$ 

Note that the cost for a single training instance is 

$${ - [y \log(\hat{p}) + (1 - y) \log(1 - \hat{p})]  }$$ 

where ${ y }$ is the label and ${ \hat{p} }$ is the predicted probability of label being ${ 1 .}$

Note that because of the somewhat thoughtful choice of ${ \sigma , }$ the gradient of the cost is 

$${ {\begin{aligned} &\, \nabla _{\theta} J(\theta) \\ = &\, \frac{1}{n} \sum _{i = 1} ^{n} - \left( y _i - \sigma \left( \theta ^T \overset{\circ}{\mathbf{x} _i} \right) \right) \overset{\circ}{\mathbf{x} _i} .  \end{aligned}}   }$$ 

Hence the gradient descent updates for ${ \theta }$ look like 

$${ \theta \longleftarrow \theta + \frac{\alpha}{n} \sum _{i = 1} ^{n} \left( y _i - \sigma \left( \theta ^T \overset{\circ}{\mathbf{x} _i} \right) \right) \overset{\circ}{\mathbf{x} _i} .  }$$ 

Equivalently, the gradient descent updates for ${ \theta }$ look like 

$${ \theta \longleftarrow \theta + \frac{\alpha}{n} \sum _{i = 1} ^{n} \left( \mathbf{y} _{i} -  \left( \sigma(\mathbf{X} \theta) \right) _i \right) \left( \text{i} ^{\text{th}} \text{ col of } \mathbf{X} ^T \right).   }$$ 

Equivalently, the gradient descent updates for ${ \theta }$ look like 

$${ \theta \longleftarrow \theta + \frac{\alpha}{n} \mathbf{X} ^{T} \left( \mathbf{y} - \sigma \left( \mathbf{X} \theta \right) \right) .  }$$ 

Here, ${ \alpha }$ is the learning rate, which determines the size of our steps in the descent. 



