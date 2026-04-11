---
layout: post
title: "Duke Data Analysis-1 Intro Probability"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

**Ref**: Coursera - Duke Courses. 

Link to Coursera - Duke Courses: [Link](https://www.coursera.org/search?query=duke%20&partners=Duke%20University&sortBy=BEST_MATCH). 

Link to Coursera - Duke Data Analysis Course: [Link](https://www.coursera.org/specializations/statistics). 

**ROUGH NOTES (!)**    
Updated: 11/4/26 

**INTRODUCTION TO PROBABILITY AND DATA WITH R**

[**Introduction to Statistics with R**] 

How does a doctor decide that a new drug is more effective than an existing drug? 

How does Google use search terms to decide that a new flu season is starting? 

How confident should a politician be in their latest poll numbers?

How does Netflix make personalized movie recommendations? 

These are the types of questions you can answer with Statistical Data Analysis. 

[**Introduction to Data**] 

​This unit will introduce you to the basics of collecting, analyzing and ​visualizing data as well as making data based decisions.

The goal of this course is to teach you to make sense of data using statistical ​tools, in order to be able to explore relationships between variables and ​make informed decisions.

When faced with a new study or a data set, the first question you should always ​ask yourself is: 

* What is the population of interest?
* What is the sample?

**Eg**: Consider the study titled "Alcohol brand use and injury in the emergency department" (2013). 

The study explored the question: 

Are consumers of certain alcohol brands more likely to end up in the emergency room with injuries? 

Based on this question alone, ​it appears that the **population** of interest is everyone. ​In other words, ideally, ​the researchers would like to find an answer to this question ​that can result in a recommendation for everyone who consumes alcohol. ​However, a closer look at this study reveals that the **sample** used in this study ​was only a group of emergency room patients at the Johns Hopkins Hospital ​in Baltimore in the US.

And alcohol brand consumption data were collected from patients who drank within ​six hours of presentation at the hospital. ​Therefore the results of the study can really only be **generalized to** ​residents of Baltimore, since certain brands maybe more easily ​available in this area than others due to national brand market share.

In this unit: 

We will start by defining populations of interest, discuss methods of taking samples from this population, and designing studies that can best answer particular research questions. 

We will also learn to identify scope of inference for a study (such as whether we can make causal versus correlational statements, and whether we can generalize our conclusions to the population at large). 

We will also learn methods of exploratory data analysis ​such as data visualizations and summary statistics.

[**Data basics**] 

Consider the table from Google's Transparency Report released in 2011. 

Data are organized in a data matrix, where each row represents an observation or a case, and each column represents a variable. 

<div align="center">
    <img src="https://b.l3n.co/cIxWIF.png"/> 
</div>

In general what are the various types of variables? 

There are two types of **variables**: 

* **Numerical** (quantitative)

* **Categorical** (qualitative)

Numerical variables take on numerical values. It is sensible to add, subtract, take averages, etc. with these values. 

Categorical variables take on a limited number of distinct categories. Categories can be identified with numbers (eg 0 for male, 1 for female) but it's not sensible to do arithmetic operations. 

**Numerical variables** can further be categorized as: 
* **Continuous**
* **Discrete**

Continuous variables (eg height) can take on any of an infinite number of values within a given range. 

Discrete variables can take on a specific set of numeric values where we're able to count all of the possibilities. Eg, number of cars a household owns. 

**Categorical variables** that have ordered levels are called **Ordinal**.    
Eg: Think about a survey question where you're asked how satisfied you are with ​the customer service you received and the options are very unsatisfied, ​unsatisfied, neutral, satisfied and very satisfied. ​These levels have an inherent ordering, ​hence the variable would be called ordinal.

Let's get back to the Google Transparency Report. 

Here are the column labels: 

* **country**: Name of the country for which the data are gathered. 

* **cr_req**: Number of content removal requests made to Google by the country. (Discrete Numerical) 

* **cr_comply**: Percentage of content removal requests Google complied with (Continuous Numerical)

* **ud_req**: Number of user data requests as part of a criminal investigation. (Discrete Numerical)

* **ud_comply**: Percentage of user data requests Google complied with. (Continuous Numerical)

* **hemisphere**: Hemisphere that the country is located in. (Categorical) 

* **hdi**: Human Development Index (very high, high, medium, low). (Ordinal)

We will look at relationships between variables. 

Here is the relationship between ud_comply and ud_req. 

<div align="center">
    <img src="https://d.l3n.co/crVjiQ.png"/> 
</div>









