---
layout: post
title: "Amazon SWE-1 Intro Software Dev"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Ref**: Coursera - Amazon Junior Software Developer Course. 

Link to the course: [Link](https://www.coursera.org/professional-certificates/amazon-junior-software-developer). 

**ROUGH NOTES (!)**    
Updated: 16/4/28 

**INTRODUCTION TO SOFTWARE DEVELOPMENT**  

We will consider 

**Introduction to Software Development**:

[**Intro to professional certificate**] 

One of the projects you will tackle will be building a "Virtual Zoo Management System". You will start by learning how to design classes that represent different animals in the zoo (like lions, elephants, eagles). Each class will define the attributes and behaviours of these animals. You will then use these classes to create actual animals called objects in Java, making the virtual zoo come alive. 

As you progress, you will implement user interaction features allowing users to navigate your zoo, select animals, and learn interesting facts about them. 

This hands on project will also introduce you to techniques like ​file i/o operations and serialization, ​which enable you to save and retrieve animal data efficiently.

[**Introduction to software development**] 

Java is a versatile, fast, and reliable programming language. 

The SDLC (Software Development LifeCycle): 

<div align="center">
    <img src="https://a.l3n.co/cRNdZo.png"/> 
</div>

[**Project preview**] 

The overarching goal of this project is to create a virtual zoo. But how will you do this? Just creating code is not good enough. You will be required to create unique and manageable code that does not repeat itself and runs smoothly. Let’s understand how you will come to do this.

**Writing less code** 

Let’s start with a simple concept—an animal. In your project, you’ll create a blueprint, or class, to represent this animal. Think of this class like a model for a cycle. It serves as a template, outlining all the basic features common to every cycle.

Now, when this model is used to create new versions with additional features, the original is known as the base class, and the new versions are called child classes. For instance, if you want to create a motorcycle, it will inherit all the characteristics of a cycle—like wheels, handlebars, and seats—just like a cycle. However, it will have extra features, such as an engine, making it distinct from a regular cycle. This enhanced version would be considered a child class of the base class 'cycle.'

Using this same concept, you will create a base ‘animal’ class which will represent the common characteristics of all the animals in your zoo. You will then reuse this class to create specific animals like a tiger and a dolphin. Imagine this to be something like creating a motorcycle or a snowmobile from the base class cycle.

Using this concept of reusing models, known as inheritance, you will reuse existing code instead of writing already existing code for every animal. This is known as extending the Animal class. You will also use techniques like abstract classes and inheritance; you can reuse your code in clever ways that save you time and effort.

**Adding the behaviours**

Tigers and dolphins not only have characteristics, but they also have certain behaviors, like moving and eating, which differ. You will implement these behaviors via something called an interface. For example, you would have an interface called ‘Walking’ or ‘Swimming’. An animal that wants to walk would declare its intent to walk by implementing the "Walking" interface, and an animal that wants to swim would implement the “Swimming” functionality. 

Imagine this to be like the ‘move’ functionality of a motorcycle or a snowmobile. Both would have the functionality but they would work differently.

**Having multiple behaviours**

You’ll need to add one more animal that can both walk and swim. Let’s go with a penguin. This penguin will be the star of your virtual zoo, showcasing your ability to use:

* Inheritance 
* Multiple interfaces

**Controlling user preferences**

In your project, after the code for your animals is set, you’ll create a menu-based system, which allows you, as the user of the program, to choose what you want your animal to do or, in other words, to display the animal’s specific characteristics and behaviors that you wish to.  

This menu will allow you to choose an animal—in this instance, a tiger, a dolphin, or a penguin. Once you have made your choice, you will be able to see the specific characteristics of your animal. You can modify these if you want. You will also be able to display the behaviors that the animal possesses, like walking, swimming, or eating.

**Conclusion**

You will be creating a menu-based system, which will enable you to get information about the characteristics and behaviors of different types of animals, as well as allow you to manipulate the characteristics of the animals. 

[**The role of a software developer**] 

**Software development** is the process of designing, implementing, and maintaining software applications or systems. 

We will look at the key tasks of a developer. 

As a developer, ​your journey often starts with

* Understanding what the end users need.

You'll work closely with clients or stakeholders to grasp the problem they ​want to solve or the functionality they want to achieve.

Once you have a clear picture, you should look at the requirements: 

* Functional requirements (Features software should have) 
* Non-Functional requirements (How software should perform) 
* Technical requirements (Choice of hardware and software) 

**Eg**: ​Imagine you're planning a new music streaming app called Airwaves. ​Here's how you would approach it. ​To start, you'll conceptualize the overall architecture by outlining ​its core features, playlist creation, song library access, ​track search, and personalized recommendations. ​Next, we'll break down airwaves into smaller manageable components. ​These include user authentication for secure logins, ensuring data protection, ​high quality music streaming that adapts to different Internet speeds, ​playlist management for a personalized music experience, and ​recommendation algorithms that learn from your behavior to suggest new music. ​Finally, you'll determine how these **components interact** seamlessly. ​For example, once you log in, you can access your playlists, ​stream music without interruptions, manage playlists in real time, and ​receive tailored recommendations based on your listening habits.

Then comes the coding part. 

Once you've written the code, it's crucial to ensure that it works as intended. **​Testing** involves running various test cases to identify bugs, errors, ​or unexpected behavior. ​**Debugging**, on the other hand, ​is the process of fixing these issues by tracing through the code, ​identifying the root cause, and making the necessary corrections.

**Version control** systems like git allow you to **track changes** to your code, **​collaborate with others**, and **revert to previous versions** if needed.

Writing clear and concise **documentation** ensures that your code ​is understandable not only to others, but also to your future self. ​It includes things like technical documentation for fellow developers, and it also includes comments within your ​code and README files outlining how to use your software.

[**Areas of expertise**] 

**Frontend development**: 

This specialization focuses on the visual side of software development that you interact with as a user daily. As a frontend developer, your main concern is what users see and interact with.

**Key tasks of a frontend developer**

- **Building user interfaces**: Your primary responsibility is to design and implement the user interface of web applications. This involves using languages like HTML, CSS, and JavaScript to create layouts, styles, and interactive elements that users can engage with. Think of different websites on which you had to make flight or hotel bookings. Some are simply easier to use than others, resulting from effective frontend development.
    
- **Cross-browser compatibility**: With the wild variation in device types today, it’s crucial to ensure that your websites or web applications look and function consistently across different web browsers and devices. You'll need to test your code on various browsers and devices to ensure a seamless user experience for all users. 
    
- **Responsive design**: Frontend developers need to ensure that their interfaces adapt and respond gracefully to different screen sizes, resolutions, and orientations. 
    
- **Optimization:** Performance matters! Optimizing the performance of your frontend code, including things like minimizing load times, reducing file sizes, and optimizing images, is essential for providing a smooth user experience.
    
- **Collaboration**: Frontend development often involves working closely with designers to bring their vision to life. Effective communication and collaboration skills are key to ensuring that the final product meets both design and functionality requirements.

One of the key tasks of a frontend developer is ensuring that websites and web applications are fully functional across various devices and browsers.

**Backend development**:

Backend development is the engine room of software development! If you're fascinated by how banking apps or e-commerce sites connect with databases behind the scenes, this specialization is for you. As a backend developer, you'll be responsible for the server-side logic and data manipulation that powers the frontend.

**Key tasks of a backend developer**

- **Server-side programming**: Your primary responsibility is to write code that runs on the server and handles tasks like processing requests, accessing databases, and generating dynamic content. Think of it as the engine of a car, powering all the functionalities behind the scenes.
    
- **Database management**: Backend developers often work with databases to store and retrieve data. This involves designing database schemas, writing Structured Query Language (SQL) queries, and optimizing database performance. It's similar to maintaining a well-organized library where information can quickly be found and efficiently managed.
    
- **API development**: Many web applications rely on APIs (Application Programming Interfaces) to communicate between the frontend and backend. Backend developers are responsible for designing and implementing these APIs, ensuring they are secure, efficient, and well-documented. An API is like a restaurant menu that lists available dishes and lets you place orders without needing to know how the kitchen prepares them.
    
- **Security**: Security is paramount in backend development. You'll need to implement measures to protect against common security threats like SQL injection, Cross-Site Scripting (XSS), and data breaches. Security-related tasks can include authenticating users, encrypting data, and performing penetration tests. These tasks are like typical home security measures you might be familiar with, like locking doors, screening visitors before allowing entry, and using security cameras to detect intruders. 
    
- **Scalability**: As web applications grow in popularity and usage, they must handle increased traffic and load. Backend developers are responsible for designing scalable architectures to accommodate growth without sacrificing performance. It's similar to adding more lanes to a highway: as traffic increases, more lanes are added to ensure smooth and efficient travel without congestion or delays.

**Full Stack Development**:

Full-stack developers are involved in every stage of the development process, from designing user interfaces to writing server-side logic to deploying and maintaining applications. It's like being a movie director who oversees the entire film production, from scriptwriting to directing actors to editing the final cut.







