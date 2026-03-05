---
layout: post
title: "Udacity Intro Programming-1 Intro Web Dev"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Introduction to Programming**

**Updated:** 5/3/26

Link to Udacity subscription: [Link](https://www.udacity.com/plans). 

Link to Udacity course: [Link](https://www.udacity.com/course/intro-to-programming-nanodegree--nd000). 

We will learn the foundations of four of the most popular languages: HTML, CSS, Javascript, and Python. 

$${ \underline{\textbf{Introduction to Web Development}} }$$ 

[**The Web and HTML**] 

HTML is used to structure and write web pages. 

In a sense, the web is a collection of documents written in HTML, along with other resources such as images and videos, as well as programs and services that interact with these documents and resources. 

<div align="center">
    <img src="https://c.l3n.co/UJTF93.png" width="400" height="200"/> 
</div>

The Web is a hypertext system. Hypertext is a form of text in which documents can refer (link) to other documents and resources. 

HTML stands for Hypertext Markup Language. 

[**Web Pages and Servers**] 

Most of the time, your browser gets webpages by communicating with servers over the internet. Servers are fundamentally also computers, but they have programs running on them that answer a browser's requests. 

One of the superpowers of the web is that you can make links to a file or document that's on a different server.    
A web page can include resources from the same web server or from other web servers. 

Web browsers and servers interact in a specific way. When you go to a webpage or follow a link, your browser makes a request to the server asking for a particular document by name, and the server sends a response back to the browser containing that document.    
The rules for how these requests and responses work are called the Hypertext Transfer Protocol (HTTP). 

HTML is the language that provides the structure and text of web pages. 

When you load up a website in your browser, the first thing that the server sends to your browser is a HTML file.    
If you look at that HTML file using programmer's tools, you will see all the technical details that tell the browser what to do. When you open the same file in a web browser, the browser will follow the instructions to build and display the page. 

[**HTML and Programming**] 

There are a few main concepts. 

Consider syntax. Syntax is the grammar rules of a language. 

Consider formalism. Computers take code literally. 

Consider nesting. Nesting is when some bits of code go inside other bits of code in an orderly way. 

Consider documentation. The manuals and tutorials that go along with software.

[**Text Editors**] 

HTML documents and programs in almost every programming language are written in text files. The layout of a web page as seen by the user, is put together by the web browser based on code in that text file.    
When a web page includes an image or a video, it does that by including a text-based address in the code of the page. The browser sees the address and then downloads the right images or videos to put into that page.

When you load an HTML file into a programmer's text editor, you'll see it displayed with colors and special formatting. This is called syntax highlighting, and it's a special feature of that editor. The editor knows the grammar of HTML and it applies colors in order to help you get the grammar right as you're editing it.

When you save a file, it is conventional to use a file name that has a particular ending or extension indicating the file type. This helps programs such as editors and browsers treat the file appropriately.    
For HTML, we'll use the filename endings .html. 

We will use VSCode. Install the "Live Preview" extension to get syntax highlighting of HTML files. 

[**The job of HTML**] 

A HTML file is made up of text that the user will actually read in the browser, and markup, which tells the browser what that text should look like or how its arranged. 

Within markup there can be references to include other documents and files, like images and videos. 

[**Markup**] 

Consider the following HTML code. 


```

This is an <strong>awesome</strong> example of HTML. 


```


Here, "\<strong>" and "\</strong>" are called tags, and the whole unit "\<strong>awesome\</strong>" is called an element. 

More specifically, "\<strong>" is called an opening tag, and "\</strong>" is called a closing tag. 

Note the output of the above HTML code, by saving it in a .html file and opening it in a browser. 

[**Breaks and Empty Elements**] 

Consider whitespace. 

Whitespace means spaces, tabs, and line breaks.

Note that when you enter text in the editor, despite putting multiple blank lines, when you render it, all whitespace gets collapsed into a single space. 

**Eg**: Here is a poem. 

```
Mary had a little toad<br>
Its skin as tough as shell<br>
And every file that toad would write<br>
It used HTML. 
```

Note how it renders. Note that "\<br>" is used to denote line break. 

[**Paragraphs**] 

To make a paragraph in HTML, we use the \<p> and \</p> tags. 

**Eg**: Here is the above poem 

```
<p>Mary had a little toad</p>
<p>Its skin as tough as shell</p>
<p>And every file that toad would write</p>
<p>It used HTML.</p> 
```

Note how it renders. Note that we get paragraphs with full blank lines between them.  

[**Lots of Elements**] 

**Eg**: 

```
This is a <em>story</em>
all about how 
<mark>my life</mark> got <sub>flipped,</sub>
turned <sup>upside down</sup> ...
```

Note how it renders. 

Note that "\<em>" tags are used to italicize text. 

Note that "\<mark>" tags are used to highlight text, and "\<sub>" tags are used to create subscript text, and "\<sup>" tags are used to create superscript text. 

[**Nested Elements**] 

We can nest elements. 

**Eg**: 

```
<p>These are some
<mark><em>important</em></mark> equations:
<em>E=mc<sup>2</sup></em>
</p>
```

[**Headings**] 

The \<h1> to \<h6> tags can be used for section headings in a document. 

**Eg**: 

```
<h1>Animals</h1>
<p>This is my super cool page about my favourite animals. For the main heading, I'm using an h1 element.</p>

<h2>Cats</h2>
<p>This part is about cats.</p> 

<h3>Cat behaviour</h3>
<p>This part is about cat behavior.</p>

<h3>Cat diet</h3>
<p>This part is about what cats eat.</p> 

<h2>Dogs</h2>
<p>This part is all about dogs.</p> 

<h3>Dog behaviour</h3>
<p>This part is about dog behavior.</p>

<h3>Dog Diet</h3>
<p>This part is about what dogs eat.</p> 


```

Note that like with the \<p> element, heading elements create a little bit of space around themselves. 

[**Block and Inline**]

\<p> tags create paragraph blocks. Hence we call these block elements. 

Elements which dont create a block, like \<em>, \<mark>, \<br> elements, are called inline elements. 

[**The div Element**] 

div is short for division. The div element can be used to divide up the page into different sections. 

Like the p element, the div element has an invisible box around it. Note that a p element is meant to contain text, and the dix element is a generic container. 

**Eg**: 

```
<div> 
    <p>Call me Ishmael.</p> 
    <p>Just don't call me late for dinner.</p> 
</div>
```

[**Lists and Implied close tags**]

There are a few HTML elements that are always used inside other elements. They dont make sense on their own. For example, \<li> element. 

**Eg**: \<li> as a part of an ordered list. 

```
<ol>
    <li> Lettuce </li>
    <li> Tomatoes </li>
    <li> Carrots </li>
</ol>
```

**Eg**: \<li> as a part of an unordered list. 

```
<ul>
    <li> Lettuce </li>
    <li> Tomatoes </li>
    <li> Carrots </li>
</ul>
```

**Eg**: Here is an example with nested lists. 

```
<h2> How to move to California: </h2>
<ol>
  <li> Pack your stuff. 
      <ul>
          <li> Kitchen stuff. </li>
          <li> Bedroom stuff. </li>
          <li> Garage stuff. </li>
      </ul></li>
  <li> Drive to California. </li>
  <li> Unpack stuff into tiny apartment. </li>
</ol>

```

HTML doesnt actually require us to write closing tags for \<li> elements. 

The \<p> element is another element for which the closing tag is optional. 

[**Nested Lists**] 

Here is another example of a nested list. 

**Eg**: Consider the output 

<div>
    <img src="https://c.l3n.co/UV6Ecc.png" width="400" height="200"/> 
</div>

For the above output the HTML code is

```
<ul>
  <li>Mammals
    <ol type="a">
      <li>Raccoons
      <li>Gorillas
    </ol>
  <li>Reptiles
    <ol type="a">
      <li>Iguanas
      <li>Cobras
    </ol>
  <li>Birds
    <ol type="a">
      <li>Ostriches
      <li>Ravens
    </ol>
</ul>
```

**Eg**: Here is an example where \<p style="color: blue;"> is used. 

<div align="center">
    <img src="https://a.l3n.co/UVC8ao.png"/> 
</div>

[**Web Addresses**] 

A web address is called a Uniform Resource Locator (URL). Here Uniform just means standardised. 

A bad example of using a web address: \<a href="www.example.com">. 

A good example of using a web address: \<a href="https://www.example.com">. 

<div align="center">
    <img src="https://d.l3n.co/U9Zkfr.png" width="400" height="200"/> 
</div>

[**Links and the \<a> tag**] 

The element for making links in a html file is called \<a>. 

\<a> stands for anchor, because an \<a> element anchors an address to a piece of text on the page. 

**Eg**: 

```
<a href="https://www.udacity.com">
        Learn to code 
        with Udacity
</a>
```

Here href stands for hypertext reference. Here "Learn to code with Udacity" is the link text. 

Adding the attribute target="\_blank" ensures that when we click on the link it is opened in a new browser tab. 

[**Adding Images**] 

The element for inserting images is \<img>. 

**Eg**: 

```
<img src="https://placebear.com/800/600" alt="photo of some bears">
```

[**Files and Relative URLs**] 

Suppose an image is locally in the same folder as the HTML file. In this case we can just put the file name in image tag and it would work. 

<div align="center">
    <img src="https://c.l3n.co/U9uyST.png" /> 
</div>

Here "kittens.jpg" is a relative url. 

<div align="center">
    <img src="https://b.l3n.co/U9ua17.png"/> 
</div>

[**Documents: DOCTYPE tag**] 

So far we have been working with HTML snippets. There are a few things to add to make them into full HTML documents. 

We indicate that we are usjng modern HTML by putting the DOCTYPE tag. 

**Eg**: \<!DOCTYPE html>. 

[**Documents: Head and Body**] 

A full HTML document actually has two parts. The HTML snippet stuff goes into the body. 

The head contains the title. The title tells the browser what title to put on a tab thats displaying the document. 

<div align="center">
    <img src="https://a.l3n.co/U9GWX0.png" width="400" height="400"/> 
</div>

The head can contain style sheet information. The head can include many other things. 

<div align="center">
    <img src="https://a.l3n.co/U9G03q.png" width="400" height="400"/> 
</div>

We can also include \<html lang="en"> in the \<html> tag. 

[**Validating HTML**] 

How do we ensure a HTML file is well written? 

Intuitively, if it looks right in the browser, it must be okay. But not quite, it might have a mistake that your browser can deal with but other browsers can't. 

We can use HTML validators to make sure the syntax is right. 

For eg, https://validator.w3.org/.

We will now consider 

$${ \boxed{\textbf{CSS}} }$$ 

[**Starting with Style**] 

CSS means Cascading Style Sheets. 

CSS is a language for describing the visual appearance of web pages, including properties such as their layout, colours, and fonts. 

[**Developer Tools**] 

Open a webpage. Open Developer Tools in Chrome. We can see the underlying files for the webpage. 

If we click on a HTML element, we can also see information about the style of the element. 

[**Text to Trees**] 

The browser reads a HTML file and turns it into a tree data structure. This tree data structure gets rendered in the browser window.

The tree structure is called DOM (Document Object Model). 

<div align="center">
    <img src="https://b.l3n.co/UdSiVm.png" width="400" height="350"/> 
</div>

[**Tree Structure**] 

A tree data structure seems to be different from a tree in graph theory. Link to Wikipedia page: [Link](https://en.wikipedia.org/wiki/Tree_(abstract_data_type)). 

Tree structures are very common in Computer Science. 

A tree is made up of parts called nodes, and the nodes have connections between them called branches. 

A tree always has a root, which is the start of a tree. The nodes which descend from a particular node are called its children. 

**Eg**: 

<div align="center">
    <img src="https://a.l3n.co/UB94n5.png"/> 
</div>

Outlines, slide decks, classifications are examples of tree data structures. 

The rules for trees are: 

* A tree has a root node. 

* Each node can have branches that lead to other nodes (its children). 

* Each node has only one parent (except the root). 

When we open developers tools and open elements tab, we are not looking at the original HTML source but a version reconstituted from the DOM tree. 

[**Trees to Boxes**] 

Every element that appears on the page gets laid out into a box. 

These boxes land inside other boxes, and the layout of these boxes is controlled by the tree structure with a little help from CSS. 

<div align="center">
    <img src="https://b.l3n.co/UBY76A.png"/> 
</div>

**Eg**: Consider how the following HTML file renders on a browser. 

```
<!DOCTYPE html>
<html>
    <head>
        <title>Listy list</title>
        <style>
            p { color: red; }
            ol { display: flex; }
            li { margin: 20px; }
        </style> 
    </head>
    <body>
        <p>These are some red red words.</p> 
        <ol>
            <li>Apple apple berry berry sauce sauce sauce.<br>
                Cook it on the stove and serve it to your boss.
            <li>Betty bought a bit of butter,
                but the butter's burning bitter.<br>
            <li>Crisp cookies claim Charlie's cookout crown.<br>  Clever Clara
                clocked the crows at <em>c</em> (clearly connivance!)
            <li>Daring drivers drove down Devil's Ditch in Dodges.
            <li>Evil eggs explode everywhere. Eww!
        </ol>
    </body>
</html>
```

It turns out the file renders as 

<div align="center">
    <img src="https://b.l3n.co/UBoK0o.png"/> 
</div>

[**Styling HTML directly**] 

We can use the style attribute on HTML opening tags. The problem is, the process is repetitive and errors can be hard to catch. 

**Eg**: 

<div align="center">
    <img src="https://c.l3n.co/UBugu9.png"/> 
</div>


Hence we prefer the CSS alternative of using the \<style> element. 

**Eg**: 

<div align="center">
    <img src="https://a.l3n.co/UButA2.png"/> 
</div>

**Eg**: Consider the HTML code. 

```
<p style="text-align: center">This is a haiku</p>
<p style="text-align: center">So I want each line centered</p>
<p style="text-align: center">Let's make it stylish</p>
```

When it renders it displays each line as a paragraph in the center. 

**Eg**: 

<div align="center">
    <img src="https://d.l3n.co/UBu6OT.png"/> 
</div>

[**CSS Syntax**] 

A CSS rule-set is made up of two parts: 

* Selector    
Which elements will the ruleset apply to?

* Declaration block    
How will the ruleset modify these elements? 

**Eg**: 

<div align="center">
    <img src="https://b.l3n.co/UBhSpr.png" width="400" height="300"/> 
</div>

**Eg**: 

<div align="center">
    <img src="https://d.l3n.co/UBhMYD.png" width="400" height="400"/> 
</div>

Here the selector is .weird. It means it will apply to any element with the class attribute equal to weird. 

[**Selectors: Type**] 

A CSS Selector tells the browser which elements the rule will affect. There are different kinds of selectors. 

Here are some examples of type selectors. 

**Eg**: 

<div align="center">
    <img src="https://b.l3n.co/UBhuJA.png" width="400" height="300"/> 
</div> 

**Eg**: 

<div align="center">
    <img src="https://c.l3n.co/UBh5JK.png" /> 
</div> 

[**Selectors: Class and ID**] 

A class is a group of things with the same characteristics.

**Eg**: Applying style using class. 

<div align="center">
    <img src="https://d.l3n.co/Um5yGM.png" width="400" height="400"/> 
</div> 

**Eg**: Applying style using id. 

<div align="center">
    <img src="https://d.l3n.co/Um5aHa.png" width="400" height="400"/> 
</div>

**Eg**: For example:

* To apply the same style to all \<p> elements, we use type selector. 

* To apply the same style to multiple (but not all) \<p> elements, we use class selector. 

* To apply a style to a single \<p> element, we use id selector. 







































