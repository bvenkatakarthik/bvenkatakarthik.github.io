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
Updated: 20/4/26 

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


[**Integers and Floats**] 

**Eg**: 

```
print(3/4) 
```

gives the output 

```
0.75 
```

Here `0.75` is a float. 

A float is a real number that uses a decimal point. 

**Eg**: 

```
print(16/4)
```

gives the output 

```
4.0 
```

Here `4.0` is a float. 

Note that `int` and `float` are two kinds of data types. 

`type()` is a built in function that returns the type of an object. 

**Eg**: 

```
print(type(4)) 
```

gives the output 

```
<class 'int'> 
```

**Eg**: 

```
print(type(4.3)) 
```

gives the output 

```
<class 'float'> 
```

**Eg**: Converting a float to an int (The part of the number after the decimal point is cut off). 

```
print(int(49.7)) 
```

gives the output 

```
49 
```

**Eg**: 

```
print(int(-49.7)) 
```

gives the output 

```
-49 
```

**Eg**: Converting an int to a float. 

```
print(float(3520 + 3239)) 
```

gives the output 

```
6759.0 
```

Floating point numbers are approximations. 

This has surprising results. 

**Eg**: 

```
print(0.1 + 0.1 + 0.1) 
```

gives the output 

```
0.30000000000000004
```

In most contexts, these small differences are irrelevant. 

In general, there are two types of errors to look out for: 

* **Exceptions**
* **Syntax Errors**

An **Exception** is a problem that occurs when the code is running, but a **Syntax Error** is a problem detected when Python checks the code before it runs it.

[**Booleans, Comparision Operators, Logical Operators**] 

We've seen ints and floats so far. And we've used arithmetic operators to work with these values. 

Another type is `bool`. A boolean is a data type that can have a value of True or False. 

(Boolean algebra is a branch of algebra dealing with variables whose values are True or False.) 

Boolean logic underpins all digital devices. 

**Eg**:  We can assign Boolean values like this. 

```
the_sun_is_up = True 
the_sun_is_blue = False 
```

**Eg**: We can use comparision operators to compare values and produce a Boolean result. 

```
x = 42 > 43 
print(x) 
```

gives the output 

```
False 
```

The list of comparision operators are: 

* `<`: less than 
* `>`: greater than 
* `<=`: less than or equal to 
* `>=`: greater than or equal to 
* `==`: equal to 
* `!=`: not equal to 

We also have logical operators: 

* `and`: evaluates if both sides are true 
* `or`: evaluates if atleast one side is true 
* `not`: inverses a Boolean type

**Eg**: 

```
age = 14 
is_teen = age > 12 and age < 20 
print(is_teen) 
```

gives the output 

```
True 
```

[**Strings**] 

A string is a data type for immutable ordered sequences of characters (eg letters, numbers, spaces, and symbols). 

**Eg**: Creating a string. 

```
print("hello") 
```

gives the output 

```
hello 
```

**Eg**: Using quotation marks in a string. 

```
salesman = "\"I think you\'re an encyclopaedia salesman\""
print(salesman) 
```

gives the output 

```
"I think you're an encyclopaedia salesman"
```

We can use `+` to combine strings. We can use `*` to repeat strings. 

**Eg**: 

```
first_word = "Hello"
second_word = "There" 
print(first_word + second_word) 
```

gives the output 

```
HelloThere 
```

**Eg**: 

```
first_word = "Hello"
second_word = "There" 
print(first_word + " " + second_word) 
```

gives the output 

```
Hello There 
```

**Eg**: 

```
word = "Hello" 
print(word * 5) 
```

gives the output 

```
HelloHelloHelloHelloHello
```

`len()` is a built in function that returns the length of an object. 

**Eg**: 

```
udacity_length = len("Udacity") 
print(udacity_length) 
```

gives the output 

```
7 
```

[**Type and Type Conversion**] 

**Eg**: Checking type. 

```
print(type(633)) 
print(type("633")) 
print(type(633.0)) 
```

gives the output 

```
<class 'int'> 
<class 'str'>
<class 'float'> 
```

Here the type function is run first and then its output is printed. 

**Eg**: Changing type. 

```
count = int(4.0) 
print(count) 
print(type(count)) 
```

gives the output 

```
4
<class 'int'> 
```

**Eg**: Changing int to str to print house address. 

```
house_number = 13 
street_name = "The Crescent" 
town_name = "Belmont" 
print(type(house_number)) 

address = str(house_number) + " " + street_name + ", " + town_name 
print(address)
```

**Eg**: Changing str to float. 

```
grams = "35.0" 
print(type(grams)) 
grams = float(grams) 
print(type(grams)) 
```

gives the output 

```
<class 'str'> 
<class 'float'> 
```

[**String Methods**] 

**Eg**: `.title()` method. 

```
print("sebastian thrun".title()) 
```

gives the output 

```
Sebastian Thrun 
```

A method is a function that "belongs" to an object. 

**Eg**: `.islower()` method. 

```
full_name = "sebastian thrun" 
print(full_name.islower()) 
```

gives the output 

```
True 
```

**Eg**: `.count()` method. 

```
print("One fish, two fish, red fish, blue fish.".count("fish")) 
```

gives the output 

```
4
```

**Eg**: `.format()` method. 

```
print("Mohammed has {} balloons".format(27))
```

gives the output 

```
Mohammed has 27 balloons. 
```

**Eg**: 

```
animal = "dog" 
action = "bite" 
print("Does your {} {}?".format(animal, action))
```

gives the output 

```
Does your dog bite? 
```

F-string, or "Formatted String Literals" is a method of string formatting. 

**Eg**: 

```
name = "John" 
print(f"Hello, {name}") 
```

gives the output 

```
Hello, John 
```

**Eg**: 

```
a = 5 
b = 3 
print(f"The sum of {a} and {b} is {a+b}") 
```

gives the output 

```
The sum of 5 and 3 is 8
```

[**Another string method - Split**] 

Consider the `.split()` method. This function or method returns a data container called a list that contains the words from the input string.

The split method has two arguments (_sep_ and _maxsplit_). The sep argument stands for "separator". It can be used to identify how the string should be split up (e.g., whitespace characters like space, tab, return, newline; specific punctuation (e.g., comma, dashes)). If the _sep_ argument is not provided, the default separator is whitespace.

The _maxsplit_ argument provides the maximum number of splits. The argument gives maxsplit + 1 number of elements in the new list, with the remaining string being returned as the last element in the list.

**Eg**: 

```
new_str = "The cow jumped over the moon." 
new_str.split()
```

gives the output 

```
['The', 'cow', 'jumped', 'over', 'the', 'moon.']
```

**Eg**: 

```
new_str.split(' ', 3)
```

gives the output 

```
['The', 'cow', 'jumped', 'over the moon.']
```

We will now consider 

$${ \boxed{\textbf{Control Flow}} }$$ 

[**Introduction**] 

Control flow describes the order in which your lines of code are run. This order is usually different than the sequence in which the lines of code appear! Execution can flow from one place in the code to another. 

[**Conditional Statements**] 

**Eg**: 

```
if phone_balance < 5: 
    phone_balance += 10 
    bank_balance -= 10 
```

An `if` statement is a conditional statement that runs or skips code based on whether a condition is True or False. The condition is specified in a boolean expression that evaluates to either True or False. (In the above example, the condition is `phone_balance < 5`.) 

**Eg**: 

```
if n % 2 == 0: 
    print("Number " + str(n) + " is even.") 
else: 
    print("Number " + str(n) + " is odd.") 
```

**Eg**: 

```
season = "fall" 

if season == "spring": 
    print("plant the garden!") 
elif season == "summer": 
    print("water the garden!") 
elif season == "fall": 
    print("harvest the garden!") 
elif season == "winter": 
    print("stay indoors!") 
else: 
    print("unrecognized season") 
```

In Python, indents conventionally come in multiples of four spaces.

























