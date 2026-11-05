---
layout: post
title: "MLS-1 Simple Linear Regression"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Ref**: 

* CodeSignal's "Implementing AI algorithms from scratch" course. Link to the course: [Link](https://codesignal.com/learn/paths/implementing-ai-algorithms-from-scratch).  

* MIT Machine Learning course. Link to the course: [Link](https://learn.mit.edu/courses/course-v1:MITxT+6.86x). 

* Stanford Machine Learning course. Link to the course: [Link](https://cs229.stanford.edu/). 

Machine Learning from Scratch - 1. 

Simple Linear Regression. 

**ROUGH NOTES (!)**    
Updated: 5/11/2026 


Eg: Suppose you own a restaurant and want to predict your sales for the next week. You pull out your past data, relating your advertisement hours with sales details. 

Can we approximately model sales as a linear function (with some offset) of ad hours? 

This is the idea of simple linear regression. 

Suppose we have data points ${ \lbrace (x _i, y _i) :  i = 1, \ldots,  n \rbrace  .}$ (Note that here ${ x _i }$s are ad hours and ${ y _i }$s are sales). 

We want to find "good" values of ${ m, c }$ such that 

$${ \text{Each } \quad y _i \approx m x _i + c .  }$$ 

Hence we can consider the loss function 

$${ L(m, c) =  \sum _{i = 1} ^{n} (y _i - (m x _i + c)) ^2   }$$ 

and look for values of ${ m, c }$ which minimize the loss. 

Note that taking partial derivatives, we have 

$${ {\begin{aligned} &\, \frac{\partial L}{\partial m} \\ = &\, 2  \sum _{i = 1} ^{n} (y _i - (m x _i + c))  (- x _i)  \end{aligned}} }$$ 

and 

$${ {\begin{aligned} &\, \frac{\partial L}{\partial c} \\ = &\, 2 \sum _{i = 1} ^{n} (y _i - (m x _i + c)) (-1) .   \end{aligned}}  }$$ 

Setting the partial derivatives to ${ 0 , }$ we see the optimal ${ m, c }$ satisfy 

$${ {\begin{aligned} &\, \left( \sum x _i \right) \hat{m} + n \hat{c} = \sum y _i, \\ &\, \left( \sum x _i ^2 \right) \hat{m} + \left( \sum x _i \right) \hat{c} = \sum x _i y _i .  \end{aligned}} }$$ 

Link to notes: [Link](https://ocw.mit.edu/courses/18-05-introduction-to-probability-and-statistics-spring-2022/mit18_05_s22_class26-prep.pdf). 

Solving these, we see the best fit line is 

$${ y = \hat{m} x + \hat{c}  }$$ 

where 

$${ {\begin{aligned} &\, \hat{m} = \frac{\sum _{i = 1} ^{n} (x _i - \bar{x}) (y _i - \bar{y})}{\sum _{i = 1} ^{n} (x _i - \bar{x}) ^2} , \\ &\, \hat{c} = \bar{y} - \hat{m} \bar{x} . \end{aligned}} }$$ 

Here ${ \bar{x} }$ is the mean of ${ x _i }$s and ${ \bar{y} }$ is the mean of ${ y _i }$s. 

[**Calculating Regression Coefficients**] 

```
import numpy as np

# Step 1: Get the data set
x = np.array([1, 2, 3, 4, 5])
y = np.array([2, 4, 5, 4, 5])

# Step 2: Compute the mean of the X and y
mean_x = np.mean(x)
mean_y = np.mean(y)

# Step 3: Calculate the coefficients
m = np.sum((x - mean_x) * (y - mean_y)) / np.sum((x - mean_x)**2)
c = mean_y - m * mean_x

# We have our model
print(f"Model: y = {c} + {m}*x")  # Output: Model: y= 2.2 + 0.6*x
```

[**Visualizing Linear Regression**] 

We can see how the linear model represents the relationship within the data.

```
plt.scatter(x, y, color="red", marker="o", s=30)  # s is marker size

y_pred = c + m * x
plt.plot(x, y_pred, color="blue")
plt.xlabel('x')
plt.ylabel('y')
plt.title('Simple Linear Regression')
plt.show()
```

Here is the result: 

![](https://d.l3n.co/2rcrN6LS.png)

[**Example**] 

Consider the example of predicting sales based on ad costs. 

```
import numpy as np
import matplotlib.pyplot as plt

advertising_costs = np.array([100, 200, 300, 400, 500])
sales = np.array([300, 500, 600, 700, 800])

mean_adv = np.mean(advertising_costs)
mean_sales = np.mean(sales)

m = np.sum((advertising_costs - mean_adv) * (sales - mean_sales)) / np.sum((advertising_costs - mean_adv)**2)
c = mean_sales - m * mean_adv

print(f"Model: Sales = {c:.2f} + {m:.2f}*Advertising_Costs")

plt.scatter(advertising_costs, sales, color = 'blue')
plt.plot(advertising_costs, c + m * advertising_costs, color = 'red')
plt.xlabel('Advertising Costs')
plt.ylabel('Sales')
plt.title('Advertising Costs vs Sales')
plt.show()
```

Here is the graph of the linear model: 

![](https://d.l3n.co/C05Rue06.png)



