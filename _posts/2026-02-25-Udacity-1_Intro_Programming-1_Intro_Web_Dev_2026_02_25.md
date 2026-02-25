---
layout: post
title: "Udacity-1 Intro Programming-1 Intro Web Dev"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Introduction to Programming**

Updated: 25/2/26

Link to Udacity subscription: [Link](https://www.udacity.com/plans). 

Link to Udacity course: [Link](https://www.udacity.com/course/intro-to-programming-nanodegree--nd000). 

We will learn the foundations of four of the most popular languages: HTML, CSS, Javascript, and Python. 

$${ \underline{\textbf{Introduction to Web Development}} }$$

**Sections**: [The Web and HTML](); 

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


























