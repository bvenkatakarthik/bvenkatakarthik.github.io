---
layout: post
title: "Udacity Intro Programming-3 Intro Python-2"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Introduction to Programming**

**Updated:** 7/4/26

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

We can also use `with`. 

**Eg**: 

```
with open("my_story.text") as my_story:
    print(my_story.read())
```

As long as this block of code is running, the file will remain open. But once this block finishes, the file will get closed automatically.


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

[**Writing output to a file**] 

Consider the profanity filter problem. Say I would like the program to write a new version of my text file with any rude words bleeped out using asterix. 

**Eg**: Suppose the text says `Well, darn it all to heck!`. We want the new file to say `Well, **** it all to ****!`.

How to write to a file: 

* Open the file in write mode
* Write to the file 
* Close the file 

**Eg**: For opening a file in write mode, 

```
>>> writefile = open("newfile.txt", "w") 
```

**(!) When you open a file in write mode, you are telling the OS that you intend to replace the contents of the file. This means the old contents of the file will be wiped out. There is no undo button for this.**

**So when you open a file in write mode, you want to use a new file name that doesn't exist yet. The open function will create the file if it does not exist and give you a file object that you can write to.**

**Eg**: For writing to a file, we use the `.write` method. 

```
>>> writefile.write("writin' my file, writin' my file\n") 
>>> writefile.write("i am so happy, writin' to my file\n") 
```

**Eg**: 

```
f = open("output.txt", "w") 

for num in range(100): 
    f.write(str(num)) 
    f.write("\n") 

f.close() 
```

We an also use `with` statements. 

```
with open("output.txt", "w") as f:
    for num in range(100):
        f.write(str(num)) 
        f.write("\n")
```

The output is the list from 0 to 99. 

```
0
1
2
.
.
.
99
```

[**Bleeper**] 

Recall the replace method on strings. 

**Eg**: 

```
>>> s = "I like to eat pizza."
>>> s = s.replace("pizza", "cake")
>>> s
'I like to eat cake.'
```

**Eg**: We can write a bleeper function as 

```
import string # Import the string module so we can use string.punctuation
test_words = ["crap", "darn!", "Heck!!!", "jerk...", "idiot?", "butt", "devil"]

def bleeper(word):
    pos = 0 # Track the position (index) of the character so we can replace it
    for character in word:
        if character not in string.punctuation:
            character = "*" # If it wasn't punctuation, replace it
        word = word.replace(word[pos], character) # Replace the character at the current position
        pos += 1 # Move to the next character position
    return word

for word in test_words:
    print(bleeper(word))
```

**Eg**: For the profanity filter problem where we need to bleep, here is a solution. 

```
import string
rude_words = ["crap", "darn", "heck", "jerk", "idiot", "butt", "devil"]

def check_line(line):
    rude_count = 0
    # We'll need the position of the current word in the list
    word_index = 0 
    words = line.split(" ")
    for word in words:
        # We need to check stripped words separately now
        stripped_word = word.strip(string.punctuation).lower() 
        if stripped_word in rude_words:
            rude_count += 1
            print(f"Found rude word: {word}")
            # Find the current word in the words list and replace it
            # with a bleeped version. Notice we use word rather than
            # stripped_word, in order to keep the punctuation.
            words[word_index] = bleeper(word)

        word_index += 1 # Moving on to the next word
    line = " ".join(words)
    # We now return both the count and the line itself, 
    # so we can write the line to a file
    return line, rude_count

def check_file(filename):
    with open(filename) as myfile:
        rude_count = 0
        # If the file has multiple lines, we will need
        # to collect them all for the final output
        lines = [] 
        for line in myfile:
            # Get the (potentially bleeped) line and 
            # the number of rude words in that line
            line, rude_subtotal = check_line(line)
            # Add to the total rude lines found in the file
            rude_count += rude_subtotal 
            # Add the current line to the lines list
            lines.append(line)

    if rude_count == 0:
        print("Congratulations, your file has no rude words.")
        print("At least, no rude words I know.")
    else:
      # If rude words were found, write them to a new file
      # and inform the user.
        with open("bleeped_copy.txt", "w") as bleeped_copy:
            bleeped_copy.write("\n".join(lines))         
        print(f"Found {rude_count} rude words in your file. See bleeped_copy.txt for a censored copy of your file.")
        
def bleeper(word):
    pos = 0 
    for character in word:
        if character not in string.punctuation:
            character = "*"
        word = word.replace(word[pos], character) 
        pos += 1
    return word

if __name__ == '__main__':
    check_file("my_other_story.txt")
```

We will consider 

$${  \boxed{\textbf{Web APIs}} }$$ 

Often our computer is connected to the internet, and so our code can make use of internet-connected resources. 

API: Application Programming Interface. It just means a way for your code to interact with some other code or application. 

[**The requests module**] 

To install, use 

```
pip install requests
```

[**Making a request**] 

```
>>> import requests 
>>> requests.get("https://www.google.com")
<Response [200]>
```
Note that `<Response [200]>`is how Python displays an object that it doesn't entirely know how to display. 

**Eg**: 

```
>>> import requests 
>>> r = requests.get("https://www.google.com")
>>> r.status_code
200 
>>> r.text
[This returns a long code]
```

Here 200 is the way HTTP says that a request was completed successfully. The full name of this code is 200 okay. (If we made a request to a page that doesn't exist like google.com/monkeybagel, we will get a status code 404 as in 404 Not Found.)

[**Try and Exceptions**] 

**Eg**: 

```
x = int(input("Enter a number.")) 
try:
    print(3 / x) 
except ZeroDivisionError:
    print("Can't divide by zero!") 
```

This is kind of like an if else statement. 

This works with NameError, IndexError, ZeroDivisionError, etc. (These are called exceptions).

**Eg**: 

```
import requests

try:
    r = requests.get("https://www.udacity.com")
    print(r) # If you did print(r.status_code), that also works!
except requests.exceptions.ConnectionError:
    print("Could not connect to server.")
```

[**What is JSON?**] 

JSON: JavaScript Object Notation.

**Eg**: 

```
>>> r = requests.get('https://www.metaweather.com/api/location/2455920/')
>>> r.text 
[We get JSON text] 
```

Like HTML text, JSON text is also structured.

[**Dictionaries**] 

In a list, the elements are indexed by 0,1, etc.

In a dictionary, values are indexed by keys. 

**Eg**: 

```
>>> d = {} 
>>> d["squid"] = "A tentacled mollusk of the briny deep" 
>>> d["squid"] 
'A tentacled mollusk of the briny deep'
>>> d["squad"] = "A smallish horde" 
>>> d["squid"] = "A friendly sea monster"
>>> d 
{'squid': 'A friendly sea monster', 'squad': 'A smallish horde'}

```

The basic operations are: creating an empty dictionary, defining key value pairs, looking up a value by a key. 

**Eg**; 

```
>>> d = {'key1': 'value1'}
>>> d['key2'] = 'value2'
>>> d['key1']
'value1'
>>> d['key2']
'value2'
>>> d
{'key1': 'value1', 'key2': 'value2'}
>>> d['key2'] = 'foo'
>>> d['key2'] += 'bar'
>>> d['key2']
'foobar'
>>> d
{'key1': 'value1', 'key2': 'foobar'}
```

**Eg**: 

```
d = {'fish': 'salmon', 'cat': 'lion'}
del d['fish']
print(d)
```

This prints `{'cat': 'lion'}`.

[**Looping over dictionaries**] 

**Eg**: 

```
favorites = {'color': 'purple', 'number': 42, 'animal': 'turtle', 'language': 'python'}

for key in favorites.keys(): 
    print(key)
```

**Eg**: 

```

favorites = {'color': 'purple', 'number': 42, 'animal': 'turtle', 'language': 'python'}

for value in favorites.values():
    print(value) 

```

The output is 

```
purple
42
turtle
python
```

**Eg**: 

```
favorites = {'color': 'purple', 'number': 42, 'animal': 'turtle', 'language': 'python'}

for entry in favorites.items():
    print(entry) 
```

The output is 

```
('color', 'purple')
('number', 42)
('animal', 'turtle')
('language', 'python')

```

**Eg**: 

```
favorites = {'color': 'purple', 'number': 42, 'animal': 'turtle', 'language': 'python'}

for key, value in favorites.items():
    print(f"my favorite {key} is {value}") 
```

The output is 

```
my favorite color is purple
my favorite number is 42
my favorite animal is turtle
my favorite language is python

```

Note that tuples are sequences (like lists), but they are immutable. 

[**Nested dictionary**] 

**Eg**: 

```
pets = {
    'birds': {
        'parrot': 'Arthur',
        'canary': 'Ford'
    },
    'fish': {
        'goldfish': 'Zaphod',
        'koi': 'Trillian'
    }
}
```

[**Simple Weather Report**] 

**Eg**: 

```
import requests

r = requests.get('https://www.metaweather.com/api/location/2455920')
```

This request uses the WOEID (Where on Earth ID) to get weather for a specific city. In this example, the WOEID is `2455920`, which is for Mountain View, California.

**Eg**: 

```
>>> import requests

>>> r = requests.get('https://www.metaweather.com/api/location/2455920')

>>> d = r.json()

>>> print(d) 

{
    'consolidated_weather': [{
        'id': 5756340131594240,
        'weather_state_name': 'Heavy Cloud',
        'weather_state_abbr': 'hc',
        'wind_direction_compass': 'W',
        'created': '2018-09-03T13:19:47.023710Z',
        'applicable_date': '2018-09-03',
        'min_temp': 13.7975,
        'max_temp': 22.1725,
        'the_temp': 14.47,
        'wind_speed': 4.825861634719902,
        'wind_direction': 269.0843199650456,
        'air_pressure': 986.85,
        'humidity': 77,
        'visibility': 9.997862483098704,
        'predictability': 71
    }, {
        'id': 6707457686503424,
        'weather_state_name': 'Clear',
        'weather_state_abbr': 'c',
        'wind_direction_compass': 'W',
        'created': '2018-09-03T13:19:50.520020Z',
        'applicable_date': '2018-09-04',
        'min_temp': 13.5025,
        'max_temp': 25.685000000000002,
        'the_temp': 24.23,
        'wind_speed': 5.112756833426125,
        'wind_direction': 270.2794344092529,
        'air_pressure': 987.6,
        'humidity': 64,
        'visibility': 9.997862483098704,
        'predictability': 68
    }, {
        'id': 6129188230660096,
        'weather_state_name': 'Light Cloud',
        'weather_state_abbr': 'lc',
        'wind_direction_compass': 'W',
        'created': '2018-09-03T13:19:53.914860Z',
        'applicable_date': '2018-09-05',
        'min_temp': 13.375,
        'max_temp': 25.925,
        'the_temp': 26.73,
        'wind_speed': 5.52573398022217,
        'wind_direction': 274.17536913320464,
        'air_pressure': 987.2,
        'humidity': 64,
        'visibility': 9.997862483098704,
        'predictability': 70
    }, {
        'id': 6028561710317568,
        'weather_state_name': 'Light Cloud',
        'weather_state_abbr': 'lc',
        'wind_direction_compass': 'W',
        'created': '2018-09-03T13:19:56.527170Z',
        'applicable_date': '2018-09-06',
        'min_temp': 13.7025,
        'max_temp': 26.322499999999998,
        'the_temp': 27.47,
        'wind_speed': 5.296090166759458,
        'wind_direction': 278.6409999622535,
        'air_pressure': 989.74,
        'humidity': 63,
        'visibility': 9.997862483098704,
        'predictability': 70
    }, {
        'id': 6695273375989760,
        'weather_state_name': 'Heavy Cloud',
        'weather_state_abbr': 'hc',
        'wind_direction_compass': 'WNW',
        'created': '2018-09-03T13:19:59.229340Z',
        'applicable_date': '2018-09-07',
        'min_temp': 14.6675,
        'max_temp': 26.37,
        'the_temp': 20.62,
        'wind_speed': 5.071978578435272,
        'wind_direction': 289.5,
        'air_pressure': 1012.59,
        'humidity': 57,
        'visibility': 9.997862483098704,
        'predictability': 71
    }, {
        'id': 5627284954284032,
        'weather_state_name': 'Heavy Cloud',
        'weather_state_abbr': 'hc',
        'wind_direction_compass': 'NW',
        'created': '2018-09-03T13:20:02.498590Z',
        'applicable_date': '2018-09-08',
        'min_temp': 14.755,
        'max_temp': 26.11,
        'the_temp': 19.47,
        'wind_speed': 5.78301625175641,
        'wind_direction': 305.0323351994134,
        'air_pressure': 1010.77,
        'humidity': 52,
        'visibility': 9.997862483098704,
        'predictability': 71
    }],
    'time': '2018-09-03T07:46:46.850600-07:00',
    'sun_rise': '2018-09-03T06:40:29.947547-07:00',
    'sun_set': '2018-09-03T19:35:30.177997-07:00',
    'timezone_name': 'LMT',
    'parent': {
        'title': 'California',
        'location_type': 'Region / State / Province',
        'woeid': 2347563,
        'latt_long': '37.271881,-119.270233'
    },
    'sources': [{
        'title': 'Forecast.io',
        'slug': 'forecast-io',
        'url': 'http://forecast.io/',
        'crawl_rate': 480
    }, {
        'title': 'HAMweather',
        'slug': 'hamweather',
        'url': 'http://www.hamweather.com/',
        'crawl_rate': 360
    }, {
        'title': 'OpenWeatherMap',
        'slug': 'openweathermap',
        'url': 'http://openweathermap.org/',
        'crawl_rate': 360
    }, {
        'title': 'Weather Underground',
        'slug': 'wunderground',
        'url': 'https://www.wunderground.com/?apiref=fc30dc3cd224e19b',
        'crawl_rate': 720
    }, {
        'title': 'World Weather Online',
        'slug': 'world-weather-online',
        'url': 'http://www.worldweatheronline.com/',
        'crawl_rate': 360
    }, {
        'title': 'Yahoo',
        'slug': 'yahoo',
        'url': 'http://weather.yahoo.com/',
        'crawl_rate': 180
    }],
    'title': 'Mountain View',
    'location_type': 'City',
    'woeid': 2455920,
    'latt_long': '37.39999,-122.079552',
    'timezone': 'America/Los_Angeles'
}

```

**Eg**: 

```
import requests

r = requests.get('https://www.metaweather.com/api/location/2455920')
d = r.json()

for forecast in d['consolidated_weather']:
    date = forecast['applicable_date']
    humidity = forecast['humidity']
    print(f"{date}\tHumidity: {humidity}")
```

Note: The `\t` in the string inserts a tab (to space out the data and humidity data).

[**Weather Report**] 

```
#!/usr/bin/env python3

import requests

API_ROOT = 'https://www.metaweather.com'
API_LOCATION = '/api/location/search/?query='
API_WEATHER = '/api/location/'  # + woeid

def fetch_location(query):
    return requests.get(API_ROOT + API_LOCATION + query).json()

def fetch_weather(woeid):
    return requests.get(API_ROOT + API_WEATHER + str(woeid)).json()

def disambiguate_locations(locations):
    print("Ambiguous location! Did you mean:")
    for loc in locations:
        print(f"\t* {loc['title']}")

def display_weather(weather):
    print(f"Weather for {weather['title']}:")
    for entry in weather['consolidated_weather']:
        date = entry['applicable_date']
        high = entry['max_temp']
        low = entry['min_temp']
        state = entry['weather_state_name']
        print(f"{date}\t{state}\thigh {high:2.1f}°C\tlow {low:2.1f}°C")

def weather_dialog():
    try:
        where = ''
        while not where:
            where = input("Where in the world are you? ")
        locations = fetch_location(where)
        if len(locations) == 0:
            print("I don't know where that is.")
        elif len(locations) > 1:
            disambiguate_locations(locations)
        else:
            woeid = locations[0]['woeid']
            display_weather(fetch_weather(woeid))
    except requests.exceptions.ConnectionError:
        print("Couldn't connect to server! Is the network up?")

if __name__ == '__main__':
    while True:
        weather_dialog()
```

Link to reddit post: [Link](https://www.reddit.com/r/learnpython/comments/5uart2/trouble_understanding_while_not/).

We will consider 

$${ \boxed{\textbf{Objects and Classes}} }$$ 

[**Welcome**] 

Since the beginning of this course, you have been using objects in Python, objects such as turtles and strings and lists and files and functions. But so far, all of the kinds of objects that you have used have been provided for you. You have not yet created any new types of objects. Strings and lists of integers and functions are all built into the core of Python, and turtles come from the turtle module which also comes with Python. However, Python also lets you create new types of objects.

Just like the built-in types, these objects will have methods on them. But now, you will be able to define your own methods for them.

The subject of this section is called object oriented programming. That's just a software engineering term for programming by creating new objects as well as reusing existing ones. 

The way you will create new types of objects is by writing class definitions. Just as a function definition defines a function, a class definition defines a class or a type of object.

[**Objects belong to classes**] 

Note that objects belong to classes. 

**Eg**: Consider the code 

```
import turtle
george = turtle.Turtle()
for side in range(4):
  george.forward(100)
  george.right(90)
```

Here `george = turtle.Turtle()` is creating a new object that belongs to the turtle class. 

**Eg**: 

```
name = input("What is your name?")
```

The input function always returns an object that belongs to the string class. 

We can check whether an object is an instance of a class by using the `isinstance` function, which will return `True` or `False` depending on whether the given object does indeed belong to the given class:

**Eg**: 

```
>>> isinstance("tomato", str)
True
>>> isinstance(42, str)
False
>>> isinstance(42, int)
True
```

We can also use the `type` function: 

**Eg**: 

```
>>> type("tomato") 
<class 'str'>
```
**Eg**: 

```
>>> import turtle 
>>> george = turtle.Turtle() 
>>> isinstance(george, turtle.Turtle) 
True 
>>> type(george) 
<class 'tutle.Turtle'> 
```

Here `turtle.Turtle` is a class, and calling the class is a way to create new objects of that class. 

[**Defining a new class**] 

To define a class, we use a `class` statement. Class statements are compound statements that look a lot like function definitions. 

**Eg**: 

```
class Dog: 
    def speak(self): 
        print("Woof!") 
```

This defines a class named `dog`. Indented inside the class, there is a method definition (for a method named `speak`). 

Once we have defined a class, we can then create (or instantiate) an object from that class, like this:

```
>>> import animals.py 
>>> fido = animals.Dog() 
```

Once we have instantiated a `Dog` object and assigned it to a variable, we can then call that object's methods: 

```
>>> fido.speak() 
Woof!
```

**Eg**: 

```
class Dog:
    def speak(self):
        print("Woof!")

class Cat:
    def speak(self):
        print("Meow!")

```

**Eg**: 

```
class Dog:
    def speak(self):
        print("Woof!")

    def eat(self, food):
        if food == "biscuit":
            print("Yummy!")
        else:
            print("That's not food!")
```

[**The self parameter**] 

**Eg**: Consider the above `animals.py` file example. 

```
>>> import animals.py 
>>> fido = animals.Dog() 
>>> fido.speak() 
'Woof!' 
>>> Dog.speak(fido) 
'Woof!'
```

In the last line, when we do this, it assigns the `fido` object to the `self` parameter, and this tells Python which object we want to use with the method. 

 
[**Using class-level variables**] 

We use **class-level variables** when there is some value that should be shared across every object of a given class.

For example, all of our dogs should share the same scientific name:

**Eg**: 

```
class Dog:
  scientific_name = "Canis lupus familiaris"
  
  def speak(self):
    print("Woof!")
```

Now 

```
>>> import animals 
>>> fido = animals.Dog() 
>>> fido.scientific_name 
'Canis lupus familiaris' 
```

[**Using instance-level variables**] 










