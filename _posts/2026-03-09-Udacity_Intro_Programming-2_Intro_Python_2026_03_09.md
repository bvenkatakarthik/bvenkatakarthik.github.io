---
layout: post
title: "Udacity Intro Programming-2 Intro Python-1"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Introduction to Programming**

**Updated:** 12/3/26

Link to Udacity subscription: [Link](https://www.udacity.com/plans). 

Link to Udacity course: [Link](https://www.udacity.com/course/intro-to-programming-nanodegree--nd000). 

**All rights of the (often wonderful) images found in these notes go to Udacity unless explicitly noted.**

We will learn the foundations of four of the most popular languages: HTML, CSS, Javascript, and Python. 

$${ \underline{\textbf{Introduction to Python - I}} }$$ 

[**Executing Python Code**] 

Run python3 \<your-file-name>.py in the terminal. You can open the file in VS code for this. 

We will now consider 

$${ \boxed{\textbf{Turtles and Code}} }$$ 

[**Starting out**] 

A program is a set of instructions for a computer. 

**Eg**: Consider the following python program. 

```
import turtle
fred = turtle.Turtle()
fred.color("red")
fred.forward(100)
fred.right(135)
fred.forward(140)
fred.right(135)
fred.forward(100)

input("Press Enter to continue...") # Keeps the window open
```

Here fred.forward refers to moving, and fred.right refers to turning right. 

Note that we get an output where a "turtle" draws a right angled triangle.

[**Variables**]

**Eg**: Consider the following python program. 

```
import turtle
george = turtle.Turtle()
george.color("yellow")
for side in [1, 2, 3, 4]:
    george.forward(100)
    george.right(90)

input("Press Enter to continue...")
```

Consider the line geroge = turtle.Turtle(). 

The right hand side creates a new turtle object (a data object placed in memory), and the left hand side says what the name will be. 

A variable is a connection between a name in the code and some data in the computer's memory. 

When we connect a name with some data in memory, we refer to this process as assignment. The = sign is called an assignment operator. 

[**Modules and Methods**] 



