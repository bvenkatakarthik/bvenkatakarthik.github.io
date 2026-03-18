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

[**Statements**] 

A statement is a piece of code that provides complete instructions for some action that Python will carry out. 

Statements like 

```
pretty_color = "blue"
mary = turtle.Turtle()
```

are assignment statements. 

Statements like 

```
import turtle 
import math 
import random 
```

are import statements. 

Statements like 

```
mary.forward(100) 
mary.right(90) 
mary.color("blue")
```

are call statements, since they are all calling another piece of code. 

All the above statements are simple statements. 

**Eg**: The statement 

```
for side in [1, 2, 3, 4, 5]: 
    mary.forward(10) 
    mary.right(72) 
```

is a compound statement. 

So far we only saw for loop compound statements.

Compound statements are used to control: 

* **Whether** the code runs. 
* **When** the code runs. 
* **How many times** the code runs. 

Control flow is the order in which statements are executed in a piece of code. 

Compound statements alter control flow. 

[**The range function**] 

**Eg**: 

```
sides = range(512)
```

The above line creates the equivalent of the list ${ [0, \ldots, 511] . }$ 

[**Crunching numbers**] 

+, -, \*, /. 

An expression is a piece of code that resolves to some value. 

**Eg**: Code for drawing a regular polygon. 

```
import turtle

sides = 100
length = 10
t = turtle.Turtle()
t.color("orange")
for side in range(sides):
    t.forward(length)
    t.right(360 / sides)
```

[**Functions**] 

Statement like range(100) is a function call. Here we are passing the input 100. We get the output which is an equivalent of the list ${ [0, 1, \ldots, 99] . }$ 

A call statement is a statement that, when it is run, executes a block of code.

Statement like mary.forward(100) is a method call. A method is a function associated with an object (such as the turtle mary). 

**Eg**: Function defining a spiral. 

```
import turtle

def spiral():
    t = turtle.Turtle()
    t.color("cyan")
    for n in range(100):
        t.forward(n)
        t.right(20)

spiral()

```


**Eg**: Spiral function with arguments. 

```
import turtle

def spiral(sides, turn, color, width):
    t = turtle.Turtle()
    t.color(color)
    t.width(width)
    for n in range(sides):
        t.forward(n)
        t.right(turn)
    input("Press Enter to continue...")

spiral(50, 45, "cyan", 5)

```

Note that the output is an octagonish spiral. 

<div align="center">
    <img src="https://b.l3n.co/Uoqxmz.png" width="400" height="400"/> 
</div>

[**draw_square**] 

**Eg**: Consider the following code. 

```
import turtle
jack = turtle.Turtle()
jack.color("blue")

def draw_square():
    for side in range(4):
        jack.forward(100)
        jack.right(90)

draw_square()
jack.forward(100)
draw_square()
jack.forward(100)
draw_square()

input("Press Enter to continue...")

```


Note that the output is a row of three squares. 

**Eg**: Consider the following code. 

```
import turtle
jack = turtle.Turtle()
jack.color("blue")
jack.speed(0)

def draw_square():
    for side in range(4):
        jack.forward(100)
        jack.right(90)

for square in range(80):
    draw_square()
    jack.forward(5)
    jack.left(5)

jack.hideturtle()

input("Press Enter to continue...") 
```

Note that the output is a spiral of many squares. 

<div align="center">
    <img src="https://a.l3n.co/UoBD3q.png" width="400" height="400"/> 
</div>

[**Example function**] 

**Eg**: Consider the code below. 

```
import turtle

# Write a function here that creates a
# turtle and draws a shape with it.
def triangle_boogie(color, start):
  t = turtle.Turtle()
  t.color(color)
  t.speed(0)
  t.width(5)
  t.right(start)
  for shape in range(6):
    for side in range(3):
      t.forward(100)
      t.right(120)
    t.right(15)
  t.hideturtle()

# Call the function multiple times.
triangle_boogie("green", 0)
triangle_boogie("orange", 120)
triangle_boogie("blue", 240)

input("Press Enter to continue...") 

```

Note that the output is 

<div align="center">
    <img src="https://b.l3n.co/UomELb.png" width="400" height="400"/> 
</div>

[**Variable Scope**] 

The scope of a variable is simply the part of the code for which that variable is defined. 

A variable that is defined inside a function can only be used inside of that function. We would say a variable like this has local scope or is a local variable. 

In contrast, a variable that is defined outside of a function can be used anywhere in the file. We would say a variable like this has global scope or is a global variable. 

[**Balloons**] 

**Eg**: Consider the following code. 

```
import turtle

def balloon(t, color):
    t.speed(0)
    t.color(color)

    # Draw balloon body.
    for side in range(30):
        t.forward(10)
        t.left(12)

    # Draw balloon knot.
    t.right(60)
    for side in range(3):
      t.forward(10)
      t.right(120)
    
    # Draw balloon string.
    t.color("gray")
    t.right(30)
    t.forward(100)


t = turtle.Turtle()

t.penup()
t.back(100)
t.pendown()
balloon(t, "red")

t.penup()
t.home()
t.pendown()
balloon(t, "blue")

t.penup()
t.home()
t.forward(100)
t.pendown()
balloon(t, "purple")

t.hideturtle()

input("Press Enter to continue...")

```

Note that the output is 

<div align="center">
    <img src="https://b.l3n.co/Uo3rAz.png" width="400" height="300"/> 
</div>


























