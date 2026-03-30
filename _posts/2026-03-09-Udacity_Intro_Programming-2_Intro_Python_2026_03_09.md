---
layout: post
title: "Udacity Intro Programming-2 Intro Python-1"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Introduction to Programming**

**Updated:** 29/3/26

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

Note that the output is three balloons. 

<div align="center">
    <img src="https://b.l3n.co/Uo3rAz.png" width="400" height="300"/> 
</div>

[**If this equals that**] 

A conditional statement is one that tells Python to run some code only when a certain condition is true. 

**Eg**: 

```
if sides == 4: 
    bob.color("purple")
```

The == sign is called the equality operator. It compares two things to see if they are equal. 

[**Two color heart**] 

**Eg**: Consider the code below. 

```
import turtle

romeo = turtle.Turtle()
juliet = turtle.Turtle()

juliet.color("blue")
juliet.width(3)

romeo.color("red")
romeo.width(3)

romeo.left(40)
romeo.forward(100)
for side in range(185):
    romeo.forward(1)
    romeo.left(1)
romeo.hideturtle()


juliet.left(140)
juliet.forward(100)
for side in range(185):
    juliet.forward(1)
    juliet.right(1)
juliet.hideturtle()


input("Press Enter to continue...")

```

Note that the output is a two colored heart. 

<div align="center">
    <img src="https://a.l3n.co/UNh4X0.png" width="400" height="400"/> 
</div>

[**if else**] 

**Eg**: Consider the code below. 

```
import turtle
jack = turtle.Turtle()
jack.width(5)

for side in range(4):
    if side == 1:
        jack.color("blue")
    else:
        jack.color("red")
    jack.forward(100)
    jack.right(90)

jack.hideturtle()

input("Press Enter to continue...")

```

Note that the output is a square with one side blue and three sides red. 

[**Modulo**] 

% 

**Eg**: 13 % 5 is the remainder on division, hence 13 % 5 = 3. 

**Eg**: Consider the list ${ [0, 1, 2, 3, \ldots, 9] . }$ Note that the values mod 2 are ${ [0, 1, 0, 1, \ldots, 1] . }$ 

**Eg**: Consider the code below. 

```
import turtle

def bead(tur):
    tur.right(75)
    for _ in range(12):
        tur.forward(10)
        tur.left(30)
    tur.left(75)

t = turtle.Turtle()
t.speed(0)
t.width(2)

# Move to the left before starting.
t.penup()
t.back(200)
t.pendown()

# Draw ten beads.
for n in range(10):
    if n % 2 == 0:
        t.color("red")
    else:
        t.color("blue")
    bead(t)
    t.forward(40)


t.hideturtle()


input("Press Enter to continue...")
```

Note that the output is ten beads alternating between red and blue. 

<div align="center">
    <img src="https://a.l3n.co/UPuuGM.png" width="400" height="75"/> 
</div>

**Eg**: Consider the code below. 

```
import turtle
t = turtle.Turtle()
t.width(5)
t.color("blue")

for step in range(21):
  t.forward(20)

  # Alternate turning left and right.
  if step % 2 == 0:
    t.left(90)
  else:
    t.right(90)

t.hideturtle()

input("Press Enter to continue...")
```

Note that the output is a staircase. 

<div align="center">
    <img src="https://b.l3n.co/UfjOm2.png" width="400" height="300"/> 
</div>

**Eg**: Consider the code below. 

```
import turtle

t = turtle.Turtle()
t.width(5)

for n in range(12):
    t.color("gray")
    if n % 3 == 0:
        t.color("red")
    if n % 3 == 1:
        t.color("orange")
    if n % 3 == 2:
        t.color("yellow")
    t.forward(50)
    t.right(360/12)

t.hideturtle() 

input("Press Enter to continue...")

```

Note that the output is a 12 sided polygon with periodically colored sides. 

<div align="center">
    <img src="https://d.l3n.co/UfjHov.png" width="400" height="425"/> 
</div>

[**Returning a value**] 

**Eg**: Consider the function 

```
def simple_function(): 
    return 10 

distance = simple_function() 

```


When we say "a function returns the number 10" what we mean is: This code works the same as if the function call (here, simple_function()) were replaced by the number 10. 

In other words 

```
distance = simple_function() 
```

is equivalent to 

```
distance = 10 
```

So a return statement takes a value and returns it back to the place from which the function was called. 

**Eg**: Consider the code below. 

```
import turtle
t = turtle.Turtle()
t.color("black")
t.width(1)
t.speed(0)
t.hideturtle()

def square(number):
    return number * number

for n in range(540):
    angle = square(n)
    t.right(angle + .5)
    t.forward(5)

t.hideturtle() 

input("Press Enter to continue...")
```

Note that the output is this strange curve. 

<div align="center">
    <img src="https://d.l3n.co/UfI4j9.png" width="400" height="425"/> 
</div>

**Eg**: The code below creates a big green turtle. 

```
import turtle

def super_reptile():
    t = turtle.Turtle()
    t.width(10)
    t.color("green")
    return t

clark = super_reptile()
clark.forward(100)
clark.left(45)
clark.forward(100)
```

**Eg**: Consider the code below. 

```
import turtle

def bead_color(num):
    if num % 3 == 0:
        return "red"
    if num % 3 == 1:
        return "green"
    if num % 3 == 2:
        return "blue"

def bead(tur):
    tur.right(75)
    for _ in range(12):
        tur.forward(10)
        tur.left(30)
    tur.left(75)

t = turtle.Turtle()
t.speed(0)
t.width(2)

# Move to the left before starting.
t.penup()
t.back(200)
t.pendown()

# Draw ten beads.
for n in range(10):
    t.color(bead_color(n))
    bead(t)
    t.forward(40)

t.hideturtle() 

input("Press Enter to continue...")

```

Note that the output is a line of rgb beads. 

[**Passing arguments in loops**] 

When we call a function from inside a loop, we can use the loop variable as input for that function. This allows us to call the same function repeatedly, but pass it a different input each time.

**Eg**: Consider the code below. 

```

import turtle

def star(color, sides, length, angle, distance):
    galileo = turtle.Turtle()
    galileo.color(color)  # colorful!
    galileo.width(5)  # visible!
    galileo.speed(0)  # fast!
    galileo.penup()
    galileo.left(angle)  # away from center
    galileo.forward(distance)
    galileo.pendown()  # start drawing
    for side in range(sides):
        galileo.forward(length)
        galileo.left(720 / sides)
    galileo.hideturtle()  # just the star
    
for angle in [180, 135, 90, 45, 0]:
    star("red", 5, 50, angle, 100)
         
for angle in [180, 135, 90, 45, 0]:
    star("blue", 5, 30, angle, 60)

input("Press Enter to continue...")

```

Note that the output is many stars. 

<div align="center">
    <img src="https://a.l3n.co/UF0MS5.png" width="400" height="300"/> 
</div>

**Eg**: Consider the code below. 

```
import turtle

def star(color, sides, length, angle, distance):
    galileo = turtle.Turtle()
    galileo.color(color)  # colorful!
    galileo.width(5)  # visible!
    galileo.speed(0)  # fast!
    galileo.penup()
    galileo.left(angle)  # away from center
    galileo.forward(distance)
    galileo.pendown()  # start drawing
    for side in range(sides):
        galileo.forward(length)
        galileo.left(720 / sides)
    galileo.hideturtle()  # just the star

for angle in [315, 270, 225, 180, 135, 90, 45, 0]:
    star("violet", 5, 50, angle, 100)

for angle in [315, 270, 225, 180, 135, 90, 45, 0]:
    star("black", 5, 30, angle, 60)

input("Press Enter to continue...")

```

Note that the output is circles of stars. 

<div align="center">
    <img src="https://a.l3n.co/UFIi8H.png" width="400" height="420"/> 
</div>

**Eg**: Consider the code below. 

```
import turtle

def polygon(sides, length):
  t = turtle.Turtle()
  t.color("green")
  t.speed(0)
  angle = 360 / sides
  for side in range(sides):
    t.forward(length)
    t.right(angle)
  t.hideturtle()

for n in [3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14]:
    polygon(n, 35)

input("Press Enter to continue...")
```

Note that the output is a pic of polygons, from 3 sided polygon to 14 sided polygon. 

<div align="center">
    <img src="https://c.l3n.co/UFIjQ1.png" width="400" height="350"/> 
</div>

[**Fizz Buzz, turtle style**] 

Consider counting from 0. Except that when a number is divisible by 3 (and not 5) we say fizz, and when a number is divisible by 5 (and not 3) we say buzz, and when a number is divisible by both 3 and 5 we say fizz buzz. 

**Eg**: Consider the code below. 

```
import turtle

def fizz(tur):
    # A red square bead.
    tur.color("red")
    tur.left(90)
    for side in [10, 20, 20, 20, 10]:
        tur.forward(side)
        tur.right(90)

def buzz(tur):
    # A green hexagonal bead.
    # Fits inside the red bead.
    tur.color("green")
    tur.left(60)
    for side in range(6):
        tur.forward(10)
        tur.right(60)
    tur.right(60)

def plain(tur):
    # A gray octagonal bead.
    tur.color("gray")
    tur.left(90)
    for side in [4, 8, 8, 8, 8, 8, 8, 8, 4]:
        tur.forward(side)
        tur.right(45)
    tur.right(45)

# Set up the turtle to draw beads.
t = turtle.Turtle()
t.speed(0)
t.width(2)
t.penup()
t.back(180)  # Back up to make room!
t.pendown()

for num in range(16):
    if num % 3 == 0:
        fizz(t)
        if num % 5 == 0:
            buzz(t)
    else:
        if num % 5 == 0:
            buzz(t)
        else:
            plain(t)
        
    # Advance to the next bead spot.
    t.color("gray")
    t.forward(22)
t.hideturtle()

input("Press Enter to continue...")
```


Note that the output is as below. Note that the red beads stand for fizz and green beads stand for buzz. 

<div align="center">
    <img src="https://c.l3n.co/UUgiO5.png"/> 
</div>


[**The random module**] 

So far we looked at deterministic programs. 

A deterministic program is a program that always produces the same output for a given input. 

Randomness can be useful in many situations. 

Python has a module called random. 

**Eg**: random.randint().

```
import random 

def die_roll(): 
    return random.randint(1, 6)

```

**Eg**: random.choice(). 

```
colors = ["red", "green", "blue"] 

c = random.choice(colors)

```

**Eg**: Consider the code below. 

```
import turtle
import random


colors = ["red", "orange", "yellow", "green", "blue", "purple"]

t = turtle.Turtle()
t.width(20)

for step in range(100):
    # Change this to use a random number.
    angle = random.randint(-90,90)

    # Change this to use a random color.
    color = random.choice(colors)

    t.color(color)
    t.right(angle)
    t.forward(10)

input("Press Enter to continue...")
```

Note that it produces a random pattern like this. 

<div align="center">
    <img src="https://b.l3n.co/UUsgPi.png" width="400" height="350"/> 
</div>

[**Comparision Operators**] 

a == b, a < b, a > b, a <= b, a >= b, a != b. 

**Eg**: Consider the code below. 

```
import turtle

def temperature_color(temp):
    # Change this code!
    if temp < 20:
        return "blue"
    if temp < 50:
        return "purple"
    if temp >= 50:
        return "red"
    return "green"

def draw_temperature(temp):
    t = turtle.Turtle()
    t.penup()
    t.back(100)
    t.width(20)
    t.pendown()
    for n in range(temp):
        t.color(temperature_color(n))
        t.forward(1)

def draw_therm_box():
    t = turtle.Turtle()
    t.speed(0)
    t.color("gray")
    t.penup()
    t.back(120)
    t.pendown()
    t.left(90)
    for side in [20, 240, 40, 240, 20]:
        t.forward(side)
        t.right(90)
    t.hideturtle()

draw_therm_box()
draw_temperature(120)

input("Press Enter to continue...")


```

Note that the output is a thermometer. 

<div align="center">
    <img src="https://a.l3n.co/UUstio.png" width="400" height="100"/> 
</div>


[**if and elif**] 

**Eg**: Consider the code below. 

```

mood = "happy"

import turtle
riley = turtle.Turtle()
riley.width(5)

if mood == "happy":
    riley.color("yellow")
elif mood == "sad":
    riley.color("blue")
else:
    riley.color("gray")

for side in range(5):
    riley.forward(100)
    riley.right(144)



```

Note that depending on what we set the mood to be, the turtle draws stars of different colors.

We will now consider 

$${  \boxed{\textbf{Shell Workshop}} }$$ 


[**Welcome**] 

A shell is simply the outermost layer of an operating system. It's designed to provide a way for you to interact with the tools and services that your operating system provides. 

The Finder in Mac is an example of a graphical shell (it has graphical user interface, GUI). In this course we will learn how to use a computer's text shell (it has command line interface, CLI).

Different operating systems use different shells. Mac and Linux computers use the BASH shell by default.  

[**Opening a terminal**] 

A terminal will allow you to interact with the shell (Like how your web browser is your interface to websites). 

[**Your first command  (echo)**] 

**Eg**: 

```
echo "Hello, shello."
```

returns Hello, shello. 

[**Variables**] 

In python we do it like 

```
x = 100 
```

In BASH we do it like 

```
x=100
```

Further, to refer to a variable we put a dollar sign in front. 

**Eg**: 

```
x=100
echo $x
```

returns 100

[**Navigating directories**] 

ls - List the contents in a directory. 

cd - Change directory. 

**Eg**: Example commands. 

```
ls 
ls Downloads 
cd Downloads/ 
ls 
cd .. ; ls 

```

The second and third commands work if Downloads is a folder visible in first ls command. The fourth command, ls, displays the contents in current directory namely Downloads. The fifth command is a actually two commands, namely cd to parent dirrectory (move one directory level up) and list the contents. 

pwd - Print working directory

**Eg**: Example commands. 

```
cd Downloads/Yellowstone/Bears/
ls 
pwd 
ls ~ 
```

ls \~ and cd \~ are used to list home directory and change to home directory respectively. 

[**Options**] 

**Eg**: 

```
ls -l
```

It is used for longer more detailed listing of files. 

**Eg**: 

```
ls -l Documents/*.pdf 
```

It is used to list all the pdf documents in Documents. 

[**Organizing files (mkdir, mv)**] 

mkdir - make directory. 

mv - move.

**Eg**: 

```
mkdir Documents/Books
```

**Eg**: 

```
mkdir Documents/Books
mv 'Documents/1911 Webster Dictionary.epub' Documents/Books 
```

**Eg**: 

```
mkdir Documents/Books
mv Documents/*.epub Documents/Books 

```

[**Downloading (curl)**] 

curl - To download a file from the web. 

curl stands for c url. 

**Eg**: 

```
curl -o google.html -L 'http://google.com'
```

The -o option writes the download to a file. The -L option is to redirect to https://www.google.com. 

**Eg**: 

```
curl -L -o dictionary.txt 'https://tinyurl.com/zeyq9vc'
```

[**Viewing files (cat, less)**] 

cat - Reads a file and outputs the contents. 

cat is short for concatenate. 

**Eg**: 

```
cat dictionary.txt 
```

**Eg**: 

```
less dictionary.txt 
```

Here press Q to quit. 

[**Removing things (rm, rmdir)**]

rm - Remove. 

(!) rm just removes the file, the file doesnt go to the recycle bin. 

**Eg**: 

```
rm 'Sillyfile.txt' 

```

**Eg**: 

```
rm -i 'ValueableFile.txt' 

```

The -i option is to add an additional YES/NO prompt to the command. 

**Eg**: 

```
rmdir 'TerribleDirectory'

```

We will now consider 

$${ \boxed{\textbf{Python at Home}} }$$ 

[**The Input Function**] 

**Eg**: 

```
name = input("What's your name? ") 
print("Hello,", name, "!") 

```

Note that for example print("abc", "def", "ghi") prints abc def ghi. Note that spaces are added. 

[**The Print Function**] 

**Eg**: 

```
print("Hello, world.") 

```


**Eg**: 

```
print(2 + 2) 

```

[**Interactive mode**] 

Type and run python in terminal. We get python in interactive mode. 

**Eg**: 

```
>>> 2 + 2 
4 
```

[**Use Print to Debug**] 

Whenever there's a variable in your code and you want to check what value it is referring to, you can use the print function.

We will now consider 

$${ \boxed{\textbf{Strings and Lists}} }$$ 

[**More Complex Strings**] 

**Eg**: 

```
>>> print("a\n(very short)\npoem")
a
(very short) 
poem

```

**Eg**: 

```
>>> print("Give us\n\nsome\n\nspace") 
Give us 

some 

space
```

**Eg**: 

```
>>> print("\"It\'s long,\" said the Knight, \"but it\'s very very beautiful.\"")    
"It's long," said the Knight, "but it's very very beautiful."
```

We can also do this using triple quotes. 

**Eg**: 

```
>>> print(""" "It's long," said the Knight, "but its very very beautiful." """) 

```

[**Length**] 

**Eg**: 

```
word = "Python" 
len(word) 
```

Here len(word) returns 6. 

**Eg**: The empty string "" has length 0. 

**Eg**: len([3, 4, 5]) is 3. len([]) is 0. 

**Eg**: 

```
len("AB\nCDE")
```

Here the length of the string is 6. 

[**Looping over things**] 

**Eg**: 

```
for thing in ["some", "list", "of", "things"]:
    print(thing) 
```

Note that the output is 

```
some 
list
of
things
```

**Eg**: 

```
for ch in "Hello!": 
    print(ch) 
```

Note that the output is 

```
H 
e
l 
l 
o 
!
```

[**Counting Things**] 

**Eg**: 

```
count = 0

for ch in "bonobos":
    if ch == "o":
        count = count + 1
        
print(count)
```


**Eg**: 

```
def count_character(string, target):
    count = 0
    for ch in string:
        if ch == target:
            count = count + 1
    return count
```

[**Indexing**] 

Lists and strings have some things in common. They both: 

* Have a length. 

* Are sequences. 

* Can be looped over. 

It turns out both have indexing as well. 

**Eg**: 

```
"Hello"[0] 
```

is the string "H". 

```
"Hello"[1] 
```

is the string "e". And so on. 

**Eg**: Consider 

```
colors = ["red", "orange", "yellow"] 
```

Here 

```
colors[0] 
```

is "red". 

```
colors[1]
```

is "orange". And so on. 

[**Range function**] 

**Eg**: 

```
for n in range(1, 4): 
    print(n) 
```

The result is 

```
1
2
3
```

**Eg**: 

```
for n in range(0, 10, 2) : 
    print(n) 
```

The result is 

```
0
2
4
6
8
```

And so on. 

[**Slicing**] 

**Eg**: 

```
"apple"[0:3] 
```

The above expression gives "app". (From 0, and upto but not including 3). 

```
"apple"[1:3]
```

The above expression gives "pp". And so on. 

[**Concatenation**] 

**Eg**: 

```
"apple" + "pie"
```

The above expression gives "applepie". 

[**f-strings**] 

**Eg**: 

```
>>> animal = "kitten" 
>>> f"Who's a cute {animal}?" 
"Who's a cute kitten?" 
```

[**Strings to Numbers to Strings**] 

**Eg**: 

```
n1 = input("Enter a number: ")
n2 = input("Enter another number: ")
n3 = input("Enter a third number: ")
sum = int(n1) + int(n2) + int(n3)
print(f"{n1} + {n2} + {n3} = {sum}")
```

We can also convert into floats. For eg, float("123.456") is 123.456. 

We can also convert numbers to strings. For eg, str(42) is "42". 

[**starts_with**] 

**Eg**: 

```
def starts_with(long, short):
    for position in range(len(short)):
        if long[position] != short[position]:
            return False
    return True
```

Alternately and more naturally, 

```

def starts_with(long, short):
    return long[0:len(short)] == short
```

[**Methods on Strings**] 

**Eg**: 

```
>>> "banana".startswith("ban")
True 
>>> "bonobo".startswith("ban") 
False 
```

Similarly we have .endswith(). 

**Eg**: 

```
def possible_tag(word):
    if word.startswith("<") and word.endswith(">"):
        print(word, "could maybe be an HTML tag")
    else:
        print(word, "is definitely not an HTML tag (but might contain one)")
```

[**Boolean Values**] 

Boolean Values: True, False. 

Boolean Operations: and, or, not. 

**Eg**: For the and operation: 

True and True is True. True and False is False. False and False is False. 

**Eg**: For the or operation: 

True or True is True. True or False is True. False or False is False. 

**Eg**: For the not operation: 

(not True) is False. (not False) is True. 

[**Operations on Lists**] 

Strings and Lists are sequences. 

Note that on sequences we can use: 

* Indexing 

* Slicing 

* len function. 

**Eg**: Total length of a list of strings. 

```
def total_length(list_of_strings):
    total = 0
    for string in list_of_strings:
        total = total + len(string)
    return total

```

For example, 

```
total_length(["foo", "bar"]) 
```

is 6. 

[**Methods on Lists**] 

**Eg**: Consider the list 

```
words = ["echidna", "dingo", "crocodile", "bunyip"] 
```

Now 

```
words.append("platypus") 
```

makes the list 

```
["echidna", "dingo", "crocodile", "bunyip", "platypus"]

```


**Eg**: Consider the list 

```
words = ["echidna", "dingo", "crocodile", "bunyip"] 
```

Now 

```
words.extend(["kangaroo", "wallaby"]) 

```

makes the list 

```
["echidna", "dingo", "crocodile", "bunyip", "kangaroo", "wallaby"] 
```

Now 

```
words.extend("abc") 
```

makes the list 

```
["echidna", "dingo", "crocodile", "bunyip", "kangaroo", "wallaby", "a", "b", "c"] 

```

Hence we usually use .extend() in the format list.extend(another_list). 

**Eg**: Consider the list 

```
words = ["echidna", "dingo", "crocodile", "bunyip"]
```

Note that 

```
words.reverse() 
```

makes the list 

```
["bunyip", "crocodile", "dingo", "echidna"]
```

**Eg**: Consider the list 

```
words = ["echidna", "dingo", "crocodile", "bunyip"]
```

Note that 

```
words.sort() 
```

makes the list 

```
['bunyip', 'crocodile', 'dingo', 'echidna']
```

Note that all the 4 methods above: append, extend, reverse, sort, they all work on a list and they all modify that list and dont return any value. 

[**Mutable vs Immutable**] 

Strings and lists differ in one way. We can modify a list (appending, extending, using list[t] assignments, etc), we cannot modify a string. 

Mutable means changeable. 

Immutable means unchangeable. 

List is a mutable data type. String is an immutable data type. 

[**Augmented Assignments**] 

**Eg**: The assignment 

```
n = n + 1 
```

can be written as 

```
n += 1 
```

[**While loops**] 

A for loop tells Python to repeat a section of code once for each item in a list, range, or other iterable. 

Another kind of loops are while loops. 

A while loop will run while some condition is True. As soon as the condition is False, the loop will stop.

**Eg**: 

```
def password_check():
    while input("Password: ") != "swordfish":
        print("Wrong! Try again!") 
    print("Okay, come on in!") 

password_check()
```

**(!) This isn't a real example of a password check.**

**Eg**: Here is an example countdown from 10. 

```
import time

n = 10
while n > 0:
    print(n)
    time.sleep(1)
    n -= 1
print("Blastoff!")

```

Note that the output is 

```
10
9
8
7
6
5
4
3
2
1
Blastoff!
```

**Eg**: 

**Q**) Write a function called until_dot that takes a string argument and returns the portion of that string before the first dot character ".". For example: 

```
>>> until_dot("This is a sentence. This is another.")
'This is a sentence'
>>> until_dot("192.168.200.2")
'192'
```

**A**) Here is a solution. 

```
def until_dot(s):
    index = 0
    while index < len(s) and s[index] != '.':
        # No dots yet, keep going.
        index += 1
    # We either found a dot or ran out of string.
    return s[:index]

```

This is an example of linear search. 




































