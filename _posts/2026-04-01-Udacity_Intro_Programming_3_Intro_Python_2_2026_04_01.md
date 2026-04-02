---
layout: post
title: "Udacity Intro Programming-3 Intro Python-2"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Introduction to Programming**

**Updated:** 1/4/26

Link to Udacity subscription: [Link](https://www.udacity.com/plans). 

Link to Udacity course: [Link](https://www.udacity.com/course/intro-to-programming-nanodegree--nd000). 

**All rights of the (often wonderful) images found in these notes go to Udacity unless explicitly noted.**

We will learn the foundations of four of the most popular languages: HTML, CSS, Javascript, and Python. 

$${ \underline{\textbf{Introduction to Python - II}} }$$ 

We will consider 

$${ \boxed{\textbf{Working with files}} }$$ 

[**Files with Python**] 

Things on disk are in persistent storage. Things in memory are ephemeral. 

[**The photos problem**] 

Consider the notes28_photos file in the github repository. 

What would I do? 

I would: 

1) Look at what files I have. 

2) Make a list of place names. 

3) Make a directory for each place name. 

4) Move files into the right directories. 

What should the program do? 

The program should: 

1) Get a list of what files I have. 

2) Extract the place names from the file names. 

3) Make a directory for each place name. 

4) Move files into the right directories. 

```
for each file in the directory: 
    extract place name 
    add it to a list of place names
```

```
for each place name: 
    create a new directory for it 
```

```
for each file in the directory: 
    move it to the new directory 
```

[**The os module**] 

How do you get a list of the files in a directory in Python? 

It turns out we can use os.listdir. 

[**Functions on Files and Directories**] 

We will take a closer look at the three functions from the OS module we'll need to write the program: os.listdir, os.mkdir, and os.rename. 

```

>>> import os

>>> os.listdir()

['notes14_beads.py', 'notes21_fizzbuzz.py', '.DS_Store', 'notes9_draw_square_1.py', 'notes12_balloons.py', 'notes25_countdown.py', 'notes19_stars_circles.py', 'notes28_photos', 'notes6_hexagon_flower.py', 'notes18_stars_arcs.py', 'notes8_spiral_function.py', 'notes22_random.py', 'notes23_thermometer.py', 'notes27_words.py', '__pycache__', 'notes26_replace_substring.py', 'notes5_square_marked.py', 'notes4_up_arrow.py', 'notes7_colored_stars.py', 'notes16_12_sided_colors.py', 'notes17_strange_curve.py', 'notes2_square.py', 'notes24_print.py', 'notes20_polygons.py', 'notes1_triangle.py', 'notes11_triangle_boogie.py', 'notes27_silly.py', 'notes3_square_spiral.py', 'notes10_draw_square_spiral.py', 'notes13_two_color_heart.py', 'notes15_stairs.py'] 

```

Note that 

```
>>> import os 

>>> os.listdir("notes28_photos")

['2017-04-02_Brooklyn_23:15:06.jpg', '2016-11-29_Berlin_04:32:38.jpg', '2016-09-04_Berlin_08:25:50.jpg', '2018-12-18_Yosemite_11:00:17.jpg', '2017-04-02_Berlin_01:35:36.jpg', '2018-08-01_Oahu_21:51:37.jpg', '2017-09-27_Firenze_03:49:17.jpg', '2018-02-12_Scotland_00:05:24.jpg', '2017-06-20_Yosemite_12:17:53.jpg', '2018-01-08_Scotland_15:13:29.jpg', '2018-07-28_Berlin_02:38:04.jpg', '2018-06-27_Kyoto_22:14:01.jpg', '2017-01-13_Yosemite_03:36:50.jpg', '2017-02-35_Kyoto_18:12:25.jpg', '2018-01-23_Cancun_01:46:43.jpg', '2018-05-17_Cancun_06:43:19.jpg', '2018-11-05_Kyoto_17:12:22.jpg', '2018-06-10_Cancun_20:42:07.jpg', '2018-10-28_Firenze_10:00:18.jpg', '2016-11-04_Berlin_09:42:22.jpg', '2017-10-10_Brooklyn_22:09:38.jpg', '2018-02-09_Kyoto_19:11:24.jpg', '2017-06-29_Firenze_22:01:03.jpg', '2018-08-16_Oahu_22:12:06.jpg', '2018-02-07_Kyoto_17:42:59.jpg', '2018-01-03_Scotland_21:51:57.jpg', '2017-07-30_Cancun_07:50:45.jpg']

```

Note that 

```
>>> import os 
>>> os.makedir("notes28_organized") 
```

creates a new directory named notes28_organized. 

Note that the real name of a file is it's whole path name including what directory it's in. Moving it to a different directory is really just changing part of its name, and the rename function lets you do this. 

**Eg**: 

```
>>> os.rename("python/counting.py", "python/lettercount.py") 
```

**Eg**: Moving using rename.

```
>>> os.rename("python/lettercount.py", "Programs/lettercount.py") 
```

**Eg**: 

```
>>> os.rename('python/counting.py', 'Programs/lettercount.py')
```

This both moves the file (from the python directory  to the Programs directory) and renames it (from counting.py to lettercount.py). 

**Eg**: 

```
>>> import os
>>> os.listdir()
['Photos', 'Desktop', 'my_file.txt']
>>> os.listdir("Photos")
['bears.jpg', 'turtle.jpg', 'cat.jpg']
>>> os.mkdir("Documents")
>>> os.listdir()
['Photos', 'Desktop', 'my_file.txt', 'Documents']
>>> os.rename("my_file.txt", "Documents/my_file.txt")
>>> os.listdir("Documents")
['my_file.txt']

```





