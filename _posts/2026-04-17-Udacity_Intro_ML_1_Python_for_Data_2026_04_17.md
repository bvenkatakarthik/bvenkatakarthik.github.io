---
layout: post
title: "Udacity Intro ML-1 Python for DA"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Ref**: Udacity MS AI curriculum. 

Link to Udacity MS AI curriculum: [Link](https://www.udacity.com/masters-artificial-intelligence). 

**INTRODUCTION TO MACHINE LEARNING WITH PYTORCH** 

**ROUGH NOTES (!)**    
Updated: 17/4/26 

Link to Udacity subscription: [Link](https://www.udacity.com/plans). 

Link to Udacity course: [Link](https://www.udacity.com/course/intro-to-machine-learning-nanodegree--nd229) 

**All rights of the content found in these notes go to Udacity unless explicitly noted.**

We will learn to build powerful Machine Learning models with Pytorch. We will learn supervised, unsupervised, and deep learning techniques through projects involving customer segmentation and image classification. 

$${ \underline{\textbf{Python for Data Analysis}} }$$  

We will now consider 

$${ \boxed{\textbf{Why Python Programming}}  }$$ 

[**Welcome**] 

Python is a powerful general purpose language with applications ranging from web development to data science. 

[**Programming in Python**] 

Unlike languages like SQL, Python is case sensitive. 

Spacing matters. 

Also, error messages can help you write better code. 

[**Course Overview**] 

<div align="center">
    <img src="https://d.l3n.co/ckGqoq.png"/> 
</div>

In this course, you will first learn how to write basic Python statements using building blocks like the print statement, variables, and different data types. 

You will then look into ways to group and order data types into different data structures. 

With an understanding of how data is structured and organized in programming, you will then control the flow of your code with conditionals, loops, and functions.

Then, in the Scripting lesson, you will combine all the concepts you’ve learned and write and run code in your local environment. 

Lastly, you will learn to apply Python to Data Science, using some pre-built collections of code, or packages. These include NumPy, a package for efficient scientific computation, and pandas, a popular data science package for manipulating data that’s built on top of NumPy.

We will now consider 

$${ \boxed{\textbf{Data Types and Operators}} }$$ 

[**Introduction**] 

`print()` is a built-in function that displays input value as text in the output. 

**Eg**: 

```
print(3 + 5) 
```

gives output 

```
8
```

[**Arithmetic Operators**] 

Arithmetic operators

- `+` Addition
- `-` Subtraction
- `*` Multiplication
- `/` Division
- `%` Mod (the remainder after dividing)
- `**` Exponentiation (note that `^` does not do this operation, as you might have seen in other languages)
- `//` Divides and **rounds down** to the nearest integer

**Eg**: 

```
print(7 // 2)
```

gives output 

```
3
```

**Eg**: 

```
print(-7 // 2)
```

gives output 

```
-4
```

[**Variables and Assignment Operators**] 

**Eg**: Here is a variable which stores the populatio of Mountain View. 

```
mv_population = 74728 
```

Here `mv_population` is the variable name, `=` is the assignment operator, and `74728` is the value of the variable.

In Python, the equal sign `=` is an operator that assigns the value on the right to the variable name on the left. 

**Eg**: 

```
x = 2 
y = x 
print(y)
```

gives output 

```
2
```

**Eg**: 

```
x = 2 
y = 3
z = 5
```

can be abbreviated as 

```
x, y, z = 2, 3, 5
```

**Eg**: Name variables well. For example, 

```
mv_population = 74728 
mv_area = 11.995 
mv_density = mv_population / mv_area 
print(mv_density) 
```

**Eg**: Updating a variable. 

```
mv_population = 74728 
mv_population = mv_population + 4000 - 600 
print(mv_population) 
```

gives output 

```
78128 
```

The same code can also be written as 

```
mv_population = 74728 
mv_population += 4000 - 600 
print(mv_population) 
```

We also have `-=` operator. 

Note that Python uses scientific notation to define large numbers. For example, `4.445e8` is equal to `4.445 * 10**8` which is equal to `444500000.0`.












