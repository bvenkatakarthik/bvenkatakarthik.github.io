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

A module is a file that has a collection of useful code that can be used in other Python programs. 

For eg once we imported the turtle module, its as if all the module code were part of our own program.

Consider the turtle module. A named block of code that can be called to get the turtle to do something is called a method. 

Statements like amy.forward(100), amy.right(90), amy.color("yellow") are method calls. We will study methods later on. 

[**Comments**] 

In code, a comment is a message for human readers. The computer ignores comments when running a code. In Python, a comment line begins with #. 

[**Using Variables**] 

**Eg**: 

```
color = "purple"
sides = [1, 2, 3, 4, 5]
angle = 72
distance = 100
mary.color(color)
for side in sides:
    mary.forward(distance)
    mary.right(angle)
```

One advantage of using variables is that on changing what a variable stands for in one place of the code, it affects all places wherever the variable is used at once. 

[**Looping**] 

Loops are useful when there is some task that we need to perform repeatedly. 

**Eg**: 

```
amy.forward(100)
amy.left(90)
amy.forward(100)
amy.left(90)
amy.forward(100)
amy.left(90)
amy.forward(100)
amy.left(90)
```

is equivalent to 

```
for side in [1, 2, 3, 4]:
    amy.forward(100)
    amy.left(90)
```

[**Lists and Loops**] 

In Python, a list of items is written with square brackets around it. 

**Eg**: 

```
import turtle

lengths = [10, 20, 30, 40, 50, 60, 70, 80, 90, 100]

dizzy = turtle.Turtle()
dizzy.color("blue")
dizzy.width(5)

for length in lengths:
    dizzy.forward(length)
    dizzy.right(90)
```

Note that the code creates a squarish spiral. 

[**Up Arrow**] 

**Eg**: Consider the python code below. 

```
import turtle

builder = turtle.Turtle()
builder.color("red")
builder.width(5)

angles = [-90, 0, 0, -90,
          135, 0, 0, 0, 
          90, 0, 0, 0,
          135, -90, 0, 0,
          90, 0, 0, 0]

for angle in angles:
    builder.right(angle)
    builder.forward(25)

input("Press Enter to continue...")
```

Note that it outputs an upward arrow. 

[**Loops within Loops**] 

**Eg**: 

```
import turtle 

paul = turtle.Turtle()
paul.color("red")

for side in [1, 2, 3, 4]:
    paul.forward(100)
    paul.right(90)
    for side in [1, 2, 3, 4]:
        paul.forward(10)
        paul.right(90)

input("Press Enter to continue...")
```


Note that the output is a square with smaller squares at the corners. 

<div align="center">
    <img src="https://a.l3n.co/UlJmr1.png" width="400" height="350"/> 
</div>

**Eg**: 

```
import turtle

links = [1, 2, 3, 4, 5, 6, 7, 8]
sides = [1, 2, 3, 4, 5, 6]

weaver = turtle.Turtle()
weaver.width(5)
weaver.color('orange')

weaver.penup()
weaver.back(80)
weaver.pendown()

for link in links:
    for side in sides:
        weaver.forward(50)
        weaver.right(60)

    weaver.penup()
    weaver.forward(20)
    weaver.left(60)
    weaver.pendown()

weaver.hideturtle()

input("Press Enter to continue...")
```

Note that the output is a hexagonish flower. 

<div align="center">
    <img src="https://a.l3n.co/UlQZqZ.png" width="400" height="400"/> 
</div>

[**Colored stars**] 

**Eg**: Consider the following code. 

```
import turtle

rainbow = ["red", "orange", "yellow", "green", "blue", "purple"]

# Write whatever code you want here!
stars = turtle.Turtle()
stars.width(5)
stars.speed(0)
for color in rainbow:
    stars.color(color)
    for side in [1, 2, 3, 4, 5]:
        stars.forward(50)
        stars.right(144)
    stars.right(60)
    stars.penup()
    stars.forward(50)
    stars.pendown()

input("Press Enter to continue...")
```

Note that the output gives colored stars in a circle. 

<div align="center">
    <img src="https://c.l3n.co/Ulq1uC.png" width="400" height="400"/> 
</div>


We will now consider 

$${ \boxed{\textbf{Python Functions}} }$$ 



















