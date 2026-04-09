---
layout: post
title: "Udacity Programming for DS-1 Intro SQL"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Programming for Data Science** 

**Updated**: 8/4/26 

Link to Udacity subscription: [Link](https://www.udacity.com/plans). 

Link to Udacity course: [Link](https://www.udacity.com/course/programming-for-data-science-nanodegree--nd104). 

We will learn programming skills needed to uncover patterns and insights in large data sets. 

$${ \underline{\textbf{Introduction to SQL}} }$$ 

[**Welcome to Programming for DS**] 

Why do you need programming for analysis? 

Broadly speaking, both statistics and programming are foundational for analyzing data. 

* Programming allows you to work with much larger datasets than is possible with spreadsheet applications.

* Programming gives the ability to automate processes. 

We will consider 

$${ \boxed{\textbf{Basic SQL}} }$$

SQL is pronounced Sequel. 

[**The Parch and Posey Database**] 

Parch & Posey (not a real company) is a paper company and the database includes sales data for their paper.

They have 50 sales reps spread across the United States in four regions. They sell three types of paper: regular, poster, and glossy. Their clients are primarily large Fortune 100 companies whom they attract by advertising on Google, Facebook, and Twitter. 

Using SQL, we will be able to help Parch and Posey answer tricky questions like: Which of their product lines is worst performing? Which of their marketing channels should they make a greater investment in? 

[**Entity Relationship Diagrams**] 

One way to store data is using spreadsheets. 

Sometimes you need lots of spreadsheets to store data from different sources. 

We can visualize the relationships between these spreadsheets using an ERD, namely an Entity Relationship Diagram. 

Below is the ERD for the database we will use from Parch & Posey. These diagrams help you visualize the data you are analyzing including:

1. The names of the tables.
2. The columns in each table.
3. The way the tables work together.

You can think of each of the boxes below as a spreadsheet.

Parch & Posey Database ERD

### web_events

|Column Name|Description|
|---|---|
|id|Unique identifier for each web event|
|account_id|Foreign key referencing the accounts table (id)|
|occurred_at|Timestamp when the web event occurred|
|channel|Channel through which the web event occurred|

Relationship:

- account_id in the web_events table is a foreign key linked to the id (primary key) in the accounts table.

### accounts

|Column Name|Description|
|---|---|
|id|Unique identifier for each account|
|name|Name of the account|
|website|Website of the account|
|lat|Latitude of the account location|
|lang|Longitude of the account location|
|primary_poc|Primary point of contact for the account|
|sales_rep_id|Foreign key referencing the sales_reps table (id)|

Relationship:

- sales_rep_id in the accounts table is a foreign key linked to the id (primary key) in the sales_reps table.

### orders

|Column Name|Description|
|---|---|
|id|Unique identifier for each order|
|account_id|Foreign key referencing the accounts table (id)|
|standard_qty|Quantity of standard products ordered|
|poster_qty|Quantity of poster products ordered|
|glossy_qty|Quantity of glossy products ordered|
|total|Total quantity of products ordered|
|occurred_at|Timestamp when the order occurred|
|standard_amt_usd|Amount in USD for standard products|
|gloss_amt_usd|Amount in USD for glossy products|
|poster_amt_usd|Amount in USD for poster products|
|total_amt_usd|Total amount in USD for the order|

Relationship:

- account_id in the orders table is a foreign key linked to the id (primary key) in the accounts table.

### sales_reps

|Column Name|Description|
|---|---|
|id|Unique identifier for each sales representative|
|name|Name of the sales representative|
|region_id|Foreign key referencing the region table (id)|

Relationship:

- region_id in the sales_reps table is a foreign key linked to the id (primary key) in the region table.

### region

|Column Name|Description|
|---|---|
|id|Unique identifier for each region|
|name|Name of the region|

We will look into this more carefully later.

**Note: glossy_qty is incorrect, it is actually gloss_qty in the database**

[**Why SQL is Important**] 

Note that SQ**L** is a **Language**. 

For this class, you can think of a database as a bunch of excel spreadsheets all sitting in one place.

**Why do Data Analysts use SQL?** 

Most of the world's data lives in databases, and the world's databases are accessed using structured query language, abbreviated as SQL. 

SQL is popular for data analysis because: 

* SQL is semantically easy to understand. 

* It can be used to access large amounts of data directly where it's stored. (You don't have to copy data into other applications to view it, and you don't need to worry about your spreadsheet program crashing because of data overload.)

* Easy to audit and replicate. (In a spreadsheet tool like Excel, you have to click in to each cell to know how they're calculated. With SQL, you can just read a query from top to bottom, nothing's hidden.) 

*  SQL is a great tool for analyzing multiple tables at once.

**Eg**: SQL vs Google Analytics. 

Google Analytics: 

* Which pages recieve the most traffic? 

* Where does the traffic come from? 

We can use SQL to answer much complex and deeper questions: 

SQL: 

* How many return within 1 and 3 weeks of first visit? 

* What brings them back? 

**Why do Businesses choose SQL?** 

1. Data integrity is ensured - only the data you want to be entered is entered, and only certain users are able to enter data into the database.
2. Data can be accessed quickly - SQL allows you to obtain results very quickly from the data stored in a database. Code can be optimized to quickly pull results.
3. Data is easily shared - multiple individuals can access data stored in a database, and the data is the same for all users allowing for consistent results for anyone with access to your database.



 






