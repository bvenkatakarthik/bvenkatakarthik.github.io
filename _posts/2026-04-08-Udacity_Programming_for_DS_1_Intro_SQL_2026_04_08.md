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

An entity-relationship diagram (ERD) is a common way to view data in a database. Below is the ERD for the database we will use from Parch & Posey. These diagrams help you visualize the data you are analyzing including:

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
 






