---
layout: post
title: "MLS-2 Multiple Linear Regression"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Ref**: 

* CodeSignal's "Implementing AI algorithms from scratch" course. Link to the course: [Link](https://codesignal.com/learn/paths/implementing-ai-algorithms-from-scratch).  

* MIT Machine Learning course. Link to the course: [Link](https://learn.mit.edu/courses/course-v1:MITxT+6.86x). 

* Stanford Machine Learning course. Link to the course: [Link](https://cs229.stanford.edu/). 

Machine Learning from Scratch - 2. 

Multiple Linear Regression. 

**ROUGH NOTES (!)**    
Updated: 5/11/2026 

Eg: Suppose we want to predict house prices. Note that they depend on multiple factors, like location, size, and number of rooms. 

Can we approximately model house price as a linear function (with some offset) of features like size, number of rooms, etc.? 

This is the idea of multiple linear regression. 

Suppose we have ${ n }$ data points, each with ${ m }$ features and one corresponding ${ y }$ value. 

We can arrange the feature values in a matrix 

$${ \mathbf{X} = \begin{pmatrix} 1 &x _{1,1} &\cdots &x _{1,m} \\ 1 &x _{2, 1} &\cdots &x _{2, m} \\ \vdots &\vdots &\ddots &\vdots \\ 1 &x _{n,1} &\cdots &x _{n, m} \end{pmatrix} .   }$$ 

Here each row represents the ${ m }$ features for a single data point. 

For each row, there is a corresponding ${ y }$ value. We can arrange these ${ y }$ values like 

$${ \mathbf{y} = \begin{pmatrix} y _1 \\ \vdots \\ y _n \end{pmatrix} .  }$$ 

Now we are looking for 

$${ \text{Looking for: } \quad \beta _0, \ldots, \beta _m  }$$ 

such that 

$${ \begin{pmatrix} y _1 \\ y _2 \\ \vdots \\ y _n \end{pmatrix} \approx {\begin{pmatrix} 1 &x _{1,1} &\cdots &x _{1,m} \\ 1 &x _{2, 1} &\cdots &x _{2, m} \\ \vdots &\vdots &\ddots &\vdots \\ 1 &x _{n,1} &\cdots &x _{n, m} \end{pmatrix}} \begin{pmatrix} \beta _0 \\ \beta _1 \\ \vdots \\ \beta _m \end{pmatrix} .    }$$ 

Equivalently we are looking for a vector ${ \beta }$ such that 

$${ \mathbf{y} \approx \mathbf{X} \beta .  }$$ 

Hence we can consider the loss function 

$${ L(\beta) = \lVert \mathbf{X} \beta - \mathbf{y} \rVert  ^{2}    }$$ 

and look for the vectors ${ \beta }$ which minimize the loss. 

Note that the partial derivative 

$${ {\begin{aligned} &\, \frac{\partial L}{\partial \beta _i} \\ = &\, \frac{\partial}{\partial \beta _i} (\mathbf{X} \beta - \mathbf{y}) ^T (\mathbf{X} \beta - \mathbf{y}) \\ = &\, \frac{\partial}{\partial \beta _i} \left( \beta ^T (\mathbf{X} ^T \mathbf{X} ) \beta - 2 \beta ^T \mathbf{X} ^T \mathbf{y} + \mathbf{y} ^T \mathbf{y} \right)  \\ = &\, 2 ((\mathbf{X} ^T \mathbf{X}) \beta ) _{i} - 2 (\mathbf{X} ^T \mathbf{y}) _{i} . \end{aligned}}  }$$ 

For more details, consider this post. Link to post: [Link](https://math.stackexchange.com/a/312271/303300). 

Hence the gradient of the loss is 

$${ \nabla _{\beta} L(\beta) = 2 (\mathbf{X} ^T \mathbf{X} \beta - \mathbf{X} ^{T} \mathbf{y}) .  }$$ 

Hence the optimal ${ \beta  }$ is typically given by 

$${ \hat{\beta} = (\mathbf{X} ^T \mathbf{X}) ^{-1} \mathbf{X} ^T \mathbf{y} . }$$ 

This is called the normal equation. 

[**Python Implementation**] 

First, we set up our dataset: 

```
X = np.array([[73, 67, 43], 
              [91, 88, 64], 
              [87, 134, 58], 
              [102, 43, 37], 
              [69, 96, 70]], dtype='float32')

y = np.array([56, 81, 119, 22, 103], dtype='float32')
```

Now we append a column of ${ 1 }$s to ${ \mathbf{X} . }$ 

```
ones = np.ones(shape=(len(X), 1))
X = np.append(ones, X, axis=1)
```

Now we compute the coefficients ${ \beta }$ using the normal equation. 

```
beta = np.linalg.inv(X.T @ X) @ X.T @ y

# Alternately, 
# even beta = np.linalg.inv(X.T.dot(X)).dot(X.T).dot(y)
# would work. 
```

[**Model's Performance Evaluation**] 

After completing our model, we need to evaluate its performance. We will use the coefficient of determination (${ R ^2  }$ score) for that. It indicates how well our model fits the data. 

Consider this post about ${ R ^2 . }$ Link to the post: [Link](https://stats.stackexchange.com/a/130114/319581). 

Note that in the context of the discussion and the red triangle in picture 

$${ R ^2 = \frac{\lVert \hat{\mathbf{y}} - \bar{y} \mathbf{1} _n \rVert ^2 }{\lVert \mathbf{y} - \bar{y} \mathbf{1} _{n} \rVert ^2} = \cos ^{2} (\theta) .  }$$ 

Hence intuitively the larger the ${ R ^2 }$ the better the fit. 

Here is the Python Implementation: 

```
predictions = X.dot(beta)
ss_residuals = np.sum(np.square(y - predictions))
ss_total = np.sum(np.square(y - np.mean(y)))
r2_score = 1 - (ss_residuals/ss_total)

print("R^2 Score:", r2_score)  # Output: R^2 Score: 0.9992
```










