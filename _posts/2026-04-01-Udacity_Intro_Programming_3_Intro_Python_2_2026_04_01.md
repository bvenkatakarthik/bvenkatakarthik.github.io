---
layout: post
title: "Udacity Intro Programming-3 Intro Python-2"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Introduction to Programming**

**Updated:** 3/4/26

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

[**Relative Paths and Current Working Directory**] 

```
os.getcwd 
```

lets you get the current working directory. 

```
os.chdir 
```

lets you change it. 

**Eg**: 

```
>>> os.getcwd() 
"/Users/kelly"
>>> os.chdir('/Users/kelly/Photos')
```

[**os functions and shell commands**] 

os.getcwd -> pwd -> What's the current directory? 

os.listdir -> ls -> What files are here? 

os.mkdir -> mkdir -> Make a new directory 

os.rename -> mv -> Move or rename file or directory

Note that in Windows file names are like 

```
C:\Users\Kelly\Downloads\amazing_thing.py 
```

and in Mac or Linux file names are like 

```
/Users/Kelley/Downloads/amazing_thing.py
```

Note that 

```
os.path.join("Downloads", "amazing_things.py") 
```

appends with / on Mac or Linux and \ on Windows. 

Portable code is code that will work correctly on different systems. 

Python is a great language for writing portable code. 

[**Get a list of the file names**] 

Recall our task list 

1) **Get a list of what files I have.** 

2) Extract the place names from the file names. 

3) Make a directory for each place name. 

4) Move files into the right directories. 

The code for that is 

```
import os

os.chdir("notes28_photos")
originals = os.listdir()

print(originals) # Just for testing the code
```

[**Extract the place names**] 

Next on our task list 

1) Get a list of what files I have.

2) **Extract the place names from the file names.** 

3) Make a directory for each place name. 

4) Move files into the right directories. 

The code for that is 

```
def extract_place(filename):
    first = filename.find("_")
    partial = filename[first+1:]
    second = partial.find("_")
    return partial[:second]

# Here are some calls you can use for testing:
print(extract_place("2016-11-04_Berlin_09/42/22.jpg"))
print(extract_place("2018-01-03_Oahu_21/51/57.jpg"))
print(extract_place("2018-01_Scotland_11/51/27.jpg"))
```

Recall the split method on strings. 

**Eg**: 

```
>>> "this and that".split(" ") 
['this', 'and', 'that'] 
```

Here is another definition of extract_place. 

```
def extract_place(filename):
    return filename.split("_")[1]
```

[**Make place directories**] 

Next on our task list 

1) Get a list of what files I have.

2) Extract the place names from the file names. 

3) **Make a directory for each place name.** 

4) Move files into the right directories.

```
import os

def extract_place(filename):
    return filename.split('_')[1]

def make_place_directories(places): # Here's the function definition
    for place in places:
        os.mkdir(place)
        print(f"Created directory: {place}")

# Change the current working directory to 'notes28_photos'
os.chdir("notes28_photos")

# List all items in the current directory before cleanup
originals_before_cleanup = os.listdir()

# Remove existing directories (in case there are directories from previous executions of this script)
for item in originals_before_cleanup:
    if os.path.isdir(item):
        os.rmdir(item)
        print(f"Removed directory: {item}")

# Re-fetch the list of items in the directory after removing old directories
originals_after_cleanup = os.listdir()

# Initialize a list to hold the names of places
places = []

# Loop through each filename in the directory after cleanup
for filename in originals_after_cleanup:
    place = extract_place(filename)
    if place not in places: 
        places.append(place)

# Now, create directories for each unique place in the places list
make_place_directories(places)

# Print the list of items in the directory to verify the changes
print(os.listdir())



```

[**Move the files**] 

Next on our task list 

1) Get a list of what files I have.

2) Extract the place names from the file names. 

3) Make a directory for each place name. 

4) **Move files into the right directories.**

```
import os

def extract_place(filename):
    return filename.split('_')[1]

def make_place_directories(places): # Here's the function definition
    for place in places:
        os.mkdir(place)
        print(f"Created directory: {place}")

# Change the current working directory to 'notes28_photos'
os.chdir("notes28_photos")

# List all items in the current directory before cleanup
originals_before_cleanup = os.listdir()

# Remove existing directories (in case there are directories from previous executions of this script)
for item in originals_before_cleanup:
    if os.path.isdir(item):
        os.rmdir(item)
        print(f"Removed directory: {item}")

# Re-fetch the list of items in the directory after removing old directories
originals_after_cleanup = os.listdir()

# Initialize a list to hold the names of places
places = []

# Loop through each filename in the directory after cleanup
for filename in originals_after_cleanup:
    place = extract_place(filename)
    if place not in places:
        places.append(place)

# Now, create directories for each unique place in the places list
make_place_directories(places)

# Print the list of items in the directory to verify the changes
print(os.listdir())

for filename in originals_after_cleanup: 
    place = extract_place(filename) 
    os.rename(filename, os.path.join(place, filename)) 


```

[**The script footer**] 

Suppose we want to use our notes28_organize_photos.py code in another program. Can we use an import statement to do that?

It turns out yes. 

When you import a module, the code in that module gets run. But we only want to use the functions of the program...

Note that we can add the whole code into functions. We are left with a single execution statement in the code. 

```
import os

def make_place_directories(places): # Here's the function definition
    for place in places:
        os.mkdir(place)

def extract_place(filename):
    return filename.split('_')[1]

def organize_photos(directory):
    os.chdir(directory)
    originals = os.listdir()
    places = []
    for filename in originals:
        place = extract_place(filename)
        if place not in places: # This is the key change
            places.append(place)

    make_place_directories(places)

    for filename in originals:
        place = extract_place(filename)
        os.rename(filename, os.path.join(place, filename))

organize_photos("notes28_photos")
```

We now replace the execution statement as so. 

```
import os

def make_place_directories(places): # Here's the function definition
    for place in places:
        os.mkdir(place)

def extract_place(filename):
    return filename.split('_')[1]

def organize_photos(directory):
    os.chdir(directory)
    originals = os.listdir()
    places = []
    for filename in originals:
        place = extract_place(filename)
        if place not in places: # This is the key change
            places.append(place)

    make_place_directories(places)

    for filename in originals:
        place = extract_place(filename)
        os.rename(filename, os.path.join(place, filename))

if __name__ = '__main__':
    organize_photos("notes28_photos")
```

Here `__name__` and `__main__` are called dunder variables (dunder is short for double underscore). 

What is `__name__`?    
Every script has its own copy of `__name__` variable. Before running the code, python assigns a value to this variable. The value it assigns depends on whether the script is being imported or getting directly executed.    
If it is directly executed, python assigns the value `__main__` to `__name__`.    
If we import `my_script.py` python assigns the value `my_script` to `__name__`. 


[**The Profanity Filter Problem**] 

Here is a simpler problem. 

**Q**) Suppose we generate a string of 100 characters. All of these will be the letter `a` except for one, which will be the letter `b`. The position of the `b` character will be random, and our task is to find this location.

**Generating the string**: 

```
import random 

letters = ['a']*100

b_location = random.randint(0, 99) 

letters[b_location] = 'b' 

letters = "".join(letters)

```

**Searching the string**; 

```
print("Looking for 'b' ...")
pos = 0 # Start at position 0, the first character in the string
while letters[pos] != 'b': # If the current character is NOT 'b', enter the loop.
    pos += 1 # Move on to the next character.
    print("Not yet.")
# If we have exited the loop, that means the current character must be 'b'.
print(f"Found it! The letter 'b' is at position {pos}." )

```

**But how efficient is this solution?**

We will consider 2 approaches. 

Design One: 

* read file contents into a string 
* for words in the rude-words list: 
    * Is the word in the file-contents string?
         * if so, alert!
* at the end, print a message

Design Two: 

* read file contents into a string 
* split string into a list of words 
* for word in the file-contents list: 
    * is the word in the rude-words list?
         * if so, alert!
* at the end, print a message

Which approach to use? 

How much work do these programs do? 

**Reasonable guesswork**: 

Suppose file is 1000 words and 5000 characters long. Suppose we have 10 rude words. 

Program 1: Loop over rude words = 10 times, Each loop scans 5000 characters.    
50,000 character comparisions at least. 

Program 2: Loop over file words = 1000 times, Each loop checks 10 rude words.    
10,000 comparisions at least. On average, 2 characters per comparision. Hence 20,000 character comparisions. For the original split operation, + 5000 character comparisions. Hence 25,000 character comparisions.

Hence we will use the second approach. 

[**Opening and reading a file**] 

In our profanity problem, the text is originally stored in a text file. So before we do anything else, we need to get the text from the file into a string that we can scan.

**Eg**: First, we need to tell the operating system which file we're interesting in looking at, which we do with the `open` function:

```
my_story = open('my_story.txt') 
```

Python will create a file object and store it in the `my_story` variable. We can use this file object to read the contents of the file:

```
contents = my_story.read()
```

[**Closing a file**] 

When you're done using a file object, it is important to close the file. 

**Eg**: 

```
my_story.close() 
```

**Eg**: 

```
my_file = open("read_me.txt")
print(my_file.read())
my_file.close()
```

[**One word at a time**] 

```
rude_words = ["crap", "darn", "heck", "jerk", "idiot", "butt", "devil"]

def check_line(line):
    rude_count = 0
    words = line.split(" ")
    for word in words:
        if word in rude_words:
            rude_count += 1
            print(f"Found rude word: {word}")
    return rude_count

def check_file(filename):
    with open(filename) as myfile:
        rude_count = 0
        for line in myfile:
            rude_count += check_line(line)

    if rude_count == 0:
        print("Congratulations, your file has no rude words.")
        print("At least, no rude words I know.")
        
if __name__ == '__main__':
    check_file("my_story.txt")
```

There are bugs. For example "jerk." is not equal to "jerk", etc. 

We need to take punctuation off of the string. 

[**Fixing some bugs**] 

Note that 

```
>>> "rudarrrcityrr".strip("r") 
'udarrrcity'
>>> import string 
>>> string.punctuation
'!"#$%&\'()*+,-./:;<=>?@[\\]^_`{|}~'
```

Hence here is our fix. 

```
import string
rude_words = ["crap", "darn", "heck", "jerk", "idiot", "butt", "devil"]

def check_line(line):
    rude_count = 0
    words = line.split(" ")
    for word in words:
        word = word.strip(string.punctuation).lower()
        if word in rude_words:
            rude_count += 1
            print(f"Found rude word: {word}")
    return rude_count

def check_file(filename):
    with open(filename) as myfile:
        rude_count = 0
        for line in myfile:
            rude_count += check_line(line)

    if rude_count == 0:
        print("Congratulations, your file has no rude words.")
        print("At least, no rude words I know.")

if __name__ == '__main__':
    check_file("my_other_story.txt")
```





