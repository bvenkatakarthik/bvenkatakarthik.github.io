---
layout: post
title: "MLS-3 Linear Regression using Gradient Descent"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Ref**: 

* CodeSignal's "Implementing AI algorithms from scratch" course. Link to the course: [Link](https://codesignal.com/learn/paths/implementing-ai-algorithms-from-scratch).  

* MIT Machine Learning course. Link to the course: [Link](https://learn.mit.edu/courses/course-v1:MITxT+6.86x). 

* Stanford Machine Learning course. Link to the course: [Link](https://cs229.stanford.edu/). 

Machine Learning from Scratch - 3. 

Linear Regression using Gradient Descent. 

**ROUGH NOTES (!)**    
Updated: 7/11/2026 

Gradient descent is an iterative optimization algorithm for minimizing a function, usually a loss function which quantifies the disparity between predicted and actual results.

Gradient descent operates in several iterative steps: 

1. Choose random values for initial parameters.
2. Calculate the cost (the difference between actual and predicted value).
3. Compute the gradient (the steepest slope of the function around that point).
4. Update the parameters using the gradient.
5. Repeat steps 2 to 4 until we reach an acceptable error rate or exhaust the maximum iterations.


A vital component of gradient descent is the learning rate, which determines the size of the descent towards the optimum solution. It is important to note that if the learning rate is too high, we may overshoot the minimum, and if it's too low, the convergence to the minimum may take too long.

[**Gradient Descent for Linear Regression**] 

Consider the multiple linear regression setup in previous post. Link to the post: [Link](https://bvenkatakarthik.github.io/MLS_2_Multiple_Linear_Regression_2026_11_05).

We are looking for a vector ${ \theta }$ such that 

$${ \mathbf{y} \approx \mathbf{X} \theta .  }$$ 

Hence we can consider the loss function 

$${ J(\mathbf{X}, \mathbf{y}, \theta) = \frac{1}{n} \sum _{i = 1} ^{m} ((\mathbf{X} \theta) _{i}  - y _i) ^{2} .   }$$ 

Here ${ J }$ is the cost, ${ \mathbf{X} }$ is the (feature) data, ${ \mathbf{y} }$ is the actual values, ${ \theta }$ is the parameters, and ${ n }$ is the number of feature-value pairs. 

Note that the loss function is 

$${ J(\mathbf{X}, \mathbf{y}, \theta) = \frac{1}{n}  \lVert \mathbf{X} \theta - \mathbf{y} \rVert ^2 .  }$$ 

We will look for vectors ${ \theta }$ which minimize the loss. 

Note that the gradient of the loss is 

$${ \nabla _{\theta} L(\theta) = 2 ( \mathbf{X} ^T \mathbf{X} \theta - \mathbf{X} ^{T} \mathbf{y} ) .  }$$ 

Hence gradient descent updates for ${ \theta }$ look like 

$${ \theta \longleftarrow \theta - \alpha \frac{1}{n} \mathbf{X} ^{T} (\mathbf{X} \theta - \mathbf{y} ) .  }$$ 

Here, ${ \alpha }$ is the learning rate, which determines the size of our steps in the descent.

[**Cost function in Python**] 

Here is the Cost Function in Python: 

```
import numpy as np

def cost(X, y, theta):
    m = len(y)
    predictions = X.dot(theta)
    cost = (1/m) * np.sum(np.square(predictions-y)) # Compute mean square error
    return cost
```

[**Gradient Descent in Python**] 

Here is the above Gradient Descent in Python: 

```
def gradient_descent(X, y, theta, alpha, iterations):
    m = len(y)
    cost_history = np.zeros(iterations)
    theta_history = np.zeros((iterations,2))
    for i in range(iterations): # Iterate until convergence
        prediction = np.dot(X,theta)  # Matrix multiplication between X and theta
        theta = theta - (1/m)*alpha*(X.T.dot((prediction - y))) # Gradient update rule
        theta_history[i,:] = theta.T
        cost_history[i] = cost(X,y,theta)
    return theta, cost_history, theta_history
```

Here we have considered simple linear regression, hence ${ \theta }$ is a ${ 2 }$ dimensional parameter.

```
X = 2 * np.random.rand(100,1)
y = 4 +3 * X+np.random.randn(100,1)

lr = 0.01 # Learning Rate
n_iter = 1000 # Max number of iterations
theta = np.random.randn(2,1) # Randomly initialized parameters, shape (2, 1)
X_b = np.c_[np.ones((len(X),1)),X] # add bias parameter to X, shape (100, 2)
theta, cost_history, theta_history = gradient_descent(X_b,y,theta,lr,n_iter) # Gradient Descent
```

Note that `np.random.randn(100, 1)` generates a ${ 100 \times 1 }$ numpy array filled with ${ 100 }$ numbers sampled from a standard normal distribution. Here we have used it to create feature-value pairs. 

[**Example**] 

Consider the problem of estimating real estate prices based on the size of houses. 

```
import numpy as np

# Real estate prices (in $1000's) based on the size of houses (in 1000 sqft)
house_sizes = np.array([[1], [2], [3]])
house_prices = np.array([[300], [550], [760]])

# Initialize parameters for gradient descent
theta = np.array([[0.0], [1.0]]) # theta[0] is the intercept(b), theta[1] is the slope(a)
learning_rate = 0.01 # Initial learning rate
iterations = 10

# Prepend 1's to house_sizes to accommodate the intercept term (bias)
X_b = np.c_[np.ones((len(house_sizes), 1)), house_sizes]

# Perform gradient descent
for i in range(iterations):
    gradients = 2/len(house_prices) * X_b.T.dot(X_b.dot(theta) - house_prices)
    theta = theta - learning_rate * gradients

# Calculate predictions using the trained parameters
pred = X_b.dot(theta)

# Calculate R-squared
ssr = np.sum((pred - house_prices)**2)
sst = np.sum((house_prices - np.mean(house_prices))**2)
r2 = 1 - (ssr/sst)
print(f'Trained parameters: {theta.ravel()}, R-squared: {r2}')
```

The output is: 

```
Trained parameters: [ 66.47420131 153.41274427], R-squared: 0.13201581241330607
```

[**Example**] 

Consider the problem of estimating real estate prices based on the size of houses. 

```
import numpy as np

# Sample house sizes in square feet, standardized
house_sizes = np.array([[1000], [1500], [2000]])
house_sizes = (house_sizes - np.mean(house_sizes)) / np.std(house_sizes)

# Sample house prices in 1000s of dollars
house_prices = np.array([[300], [450], [600]])

# We initialize our parameters: slope (a) and intercept (b)
theta_real_estate = np.random.rand(2, 1)

# Learning rate and iterations for gradient descent, adjusted learning rate
alpha_real_estate = 0.01
iterations = 500

# Add a column of ones to the house sizes to accommodate the intercept (b)
X_b_real_estate = np.c_[np.ones((len(house_sizes), 1)), house_sizes]

def gradient_descent(X, y, theta, alpha, iterations):
    m = len(y)
    cost_history = np.zeros(iterations)
    for i in range(iterations): # Iterate until convergence
        prediction = np.dot(X, theta) # Matrix multiplication between X and theta
        # TODO: Adjust the parameters 'theta' using the gradient descent update rule
        theta = theta - (1/m)*alpha*(X.T.dot((prediction - y))) # Gradient update rule
        # TODO: Calculate the mean square error cost and record it into cost_history
        cost = (1/m) * np.sum(np.square(prediction-y)) # Compute mean square error
        cost_history[i] = cost
    return theta, cost_history

# TODO: Use the gradient_descent function to update 'theta_real_estate' and 'cost_history'
theta_real_estate, cost_history = gradient_descent(X_b_real_estate, house_prices, theta_real_estate, alpha_real_estate, iterations)

for i, cost in enumerate(cost_history[::10]):    
    print(f'Iteration {i * 10}: Cost = {cost}')
```

The output is: 

```
Iteration 0: Cost = 216726.94810375525  
Iteration 10: Cost = 177262.47441833635  
Iteration 20: Cost = 144984.20760240898  
Iteration 30: Cost = 118583.5892400475  
Iteration 40: Cost = 96990.34032461519  
Iteration 50: Cost = 79329.07223141921  
Iteration 60: Cost = 64883.79853122961  
Iteration 70: Cost = 53068.90895635373  
Iteration 80: Cost = 43405.42880611753  
Iteration 90: Cost = 35501.601349906196  
Iteration 100: Cost = 29037.00603989949  
Iteration 110: Cost = 23749.56868708649  
Iteration 120: Cost = 19424.93699410998  
Iteration 130: Cost = 15887.790729871655  
Iteration 140: Cost = 12994.734261054982  
Iteration 150: Cost = 10628.483304349298  
Iteration 160: Cost = 8693.110230763621  
Iteration 170: Cost = 7110.155167039037  
Iteration 180: Cost = 5815.445238514019  
Iteration 190: Cost = 4756.493005797385  
Iteration 200: Cost = 3890.3686280743905  
Iteration 210: Cost = 3181.9594907126584  
Iteration 220: Cost = 2602.546742607238  
Iteration 230: Cost = 2128.64103619953  
Iteration 240: Cost = 1741.0302711617608  
Iteration 250: Cost = 1424.0007373499884  
Iteration 260: Cost = 1164.7000822221294  
Iteration 270: Cost = 952.6162774695455  
Iteration 280: Cost = 779.1514622103887  
Iteration 290: Cost = 637.2733863809092  
Iteration 300: Cost = 521.2303238670245  
Iteration 310: Cost = 426.3178979768884  
Iteration 320: Cost = 348.68836637716765  
Iteration 330: Cost = 285.194633919332  
Iteration 340: Cost = 233.26266964812353  
Iteration 350: Cost = 190.78715578765036  
Iteration 360: Cost = 156.04613832316375  
Iteration 370: Cost = 127.63121911977062  
Iteration 380: Cost = 104.39045957205174  
Iteration 390: Cost = 85.38168110294538  
Iteration 400: Cost = 69.83426931781372  
Iteration 410: Cost = 57.11793335707307  
Iteration 420: Cost = 46.71715395396675  
Iteration 430: Cost = 38.2102843237478  
Iteration 440: Cost = 31.252456635955614  
Iteration 450: Cost = 25.561601099505133  
Iteration 460: Cost = 20.907010875378013  
Iteration 470: Cost = 17.099989239393356  
Iteration 480: Cost = 13.9861998317372  
Iteration 490: Cost = 11.439409872999093
```

[**Example**] 

Now we will change our approach slightly in the real estate prediction model. 

Instead of using a fixed number of iterations in gradient descent, we're going to employ a cost threshold method. We can continue adjusting our model's parameters until the difference in cost between two consecutive iterations drops below a threshold of `0.01`. To simplify, we'll stop when the cost drops below `0.01`. 

```
import numpy as np

# Sample house sizes in square feet, standardized
house_sizes = np.array([[1000], [1500], [2000]])
house_sizes = (house_sizes - np.mean(house_sizes)) / np.std(house_sizes)

# Sample house prices in 1000s of dollars
house_prices = np.array([[300], [450], [600]])

# We initialize our parameters: slope (a) and intercept (b)
theta_real_estate = np.random.rand(2, 1)

# Learning rate and iterations for gradient descent, adjusted learning rate
alpha_real_estate = 0.01
iterations = 500

# Add a column of ones to the house sizes to accommodate the intercept (b)
X_b_real_estate = np.c_[np.ones((len(house_sizes), 1)), house_sizes]

def gradient_descent(X, y, theta, alpha, threshold=0.01):
    m = len(y)
    cost_history = []
    i = 0
    while True: # Iterate until convergence
        prediction = np.dot(X, theta) # Matrix multiplication between X and theta
        # Gradient update rule with correct cost function calculation
        theta = theta - (1/m) * alpha * (X.T.dot(prediction - y))
        cost = (1/(2*m)) * np.sum(np.square(prediction - y))
        cost_history.append(cost)
        i = i + 1
        if cost <= threshold:
            break
    return theta, cost_history

  

# Run gradient descent
theta_real_estate, cost_history = gradient_descent(X_b_real_estate, house_prices, theta_real_estate, alpha_real_estate)
for i, cost in enumerate(cost_history[::10]):
    print(f'Iteration {i * 10}: Cost = {cost}')
```

The output is: 

```
Iteration 0: Cost = 108388.40325807515
Iteration 10: Cost = 88651.62697986596
Iteration 20: Cost = 72508.78073611422
Iteration 30: Cost = 59305.43480078428
Iteration 40: Cost = 48506.3265607817
Iteration 50: Cost = 39673.66101142019
Iteration 60: Cost = 32449.362581121346
Iteration 70: Cost = 26540.558775707126
Iteration 80: Cost = 21707.70715035793
Iteration 90: Cost = 17754.884277606754
Iteration 100: Cost = 14521.843026890565
Iteration 110: Cost = 11877.516158391758
Iteration 120: Cost = 9714.70286737182
Iteration 130: Cost = 7945.722871919121
Iteration 140: Cost = 6498.861861167645
Iteration 150: Cost = 5315.464202735069
Iteration 160: Cost = 4347.555047966736
Iteration 170: Cost = 3555.8954353178565
Iteration 180: Cost = 2908.391545916801
Iteration 190: Cost = 2378.7936226544853
Iteration 200: Cost = 1945.6318070811521
Iteration 210: Cost = 1591.345753021514
Iteration 220: Cost = 1301.5727315121833
Iteration 230: Cost = 1064.565366891192
Iteration 240: Cost = 870.7153991060441
Iteration 250: Cost = 712.1641656015756
Iteration 260: Cost = 582.4840117536703
Iteration 270: Cost = 476.4177142527943
Iteration 280: Cost = 389.6653536815735
Iteration 290: Cost = 318.7099961174375
Iteration 300: Cost = 260.67511690603874
Iteration 310: Cost = 213.20798657641717
Iteration 320: Cost = 174.38429137199074
Iteration 330: Cost = 142.63012172112929
Iteration 340: Cost = 116.65816606604773
Iteration 350: Cost = 95.41552335279057
Iteration 360: Cost = 78.04101850471778
Iteration 370: Cost = 63.830290452162956
Iteration 380: Cost = 52.207237389670425
Iteration 390: Cost = 42.700661653796864
Iteration 400: Cost = 34.92516740663283
Iteration 410: Cost = 28.565536718629772
Iteration 420: Cost = 23.36395065835564
Iteration 430: Cost = 19.10953733314888
Iteration 440: Cost = 15.629823159056102
Iteration 450: Cost = 12.783740795210125
Iteration 460: Cost = 10.455910284847123
Iteration 470: Cost = 8.551961560870712
Iteration 480: Cost = 6.994708690701022
Iteration 490: Cost = 5.721020764596233
Iteration 500: Cost = 4.679262573501177
Iteration 510: Cost = 3.8272013217056746
Iteration 520: Cost = 3.1302945126043946
Iteration 530: Cost = 2.560289598581549
Iteration 540: Cost = 2.094078624937954
Iteration 550: Cost = 1.7127614352108183
Iteration 560: Cost = 1.400879460307917
Iteration 570: Cost = 1.145789029323336
Iteration 580: Cost = 0.9371487961063938
Iteration 590: Cost = 0.7665005018963634
Iteration 600: Cost = 0.6269260781728322
Iteration 610: Cost = 0.5127671886982117
Iteration 620: Cost = 0.41939584100845084
Iteration 630: Cost = 0.3430267679601913
Iteration 640: Cost = 0.2805639732962477
Iteration 650: Cost = 0.22947522019883407
Iteration 660: Cost = 0.1876893746072898
Iteration 670: Cost = 0.1535124416045818
Iteration 680: Cost = 0.12555889099580508
Iteration 690: Cost = 0.10269548802249824
Iteration 700: Cost = 0.08399535211355197
Iteration 710: Cost = 0.0687003812196004
Iteration 720: Cost = 0.05619051841509199
Iteration 730: Cost = 0.045958614838872536
Iteration 740: Cost = 0.03758986991907826
Iteration 750: Cost = 0.030745015390188007
Iteration 760: Cost = 0.02514656138417732
Iteration 770: Cost = 0.020567547012840595
Iteration 780: Cost = 0.016822339391165828
Iteration 790: Cost = 0.013759108094641773
Iteration 800: Cost = 0.011253669965754585
```










