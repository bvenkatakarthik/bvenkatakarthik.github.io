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

* **cr_comply**: Percentage of content removal requests Google complied with. (Continuous Numerical)

* **ud_req**: Number of user data requests as part of a criminal investigation. (Discrete Numerical)

* **ud_comply**: Percentage of user data requests Google complied with. (Continuous Numerical)

* **hemisphere**: Hemisphere that the country is located in. (Categorical) 

* **hdi**: Human Development Index (very high, high, medium, low). (Ordinal)

We will look at relationships between variables. 

Here is the relationship between ud_comply and ud_req. 

<div align="center">
    <img src="https://d.l3n.co/crVjiQ.png"/> 
</div>

[**Observational Studies and Experiments**] 

There are two kinds of **studies**: 

* **Observational study**
* **Experimental study** 

In an **observational study**, we collect data in a way that does not directly interfere with how the data arise ("observe"). Using an observational study we can only establish an association.    
Within observational studies: Retrospective studies use past data, and prospective studies use data collected throughout the study. 

In an **experimental study**, we randomly assign subjects to treatments. Using an experimental study we can establish causal connections between explanatory and response variables. 

<div align="center">
    <img src="https://c.l3n.co/crq1b3.png"/> 
</div>

**Eg**: Suppose we ​want to evaluate the relationship between regularly working out and energy level. ​We can design this study as an observational study or an experiment. 

​In an **observational study**, we sampled two types of people from the population. ​Those who choose to work out and those who don't, ​then find the average energy level for the two groups of people and compare.

On the other hand, in an **experiment**, we sample a group of people from ​the population, then we randomly assign these people into two groups. ​Those who will regularly work out through the course of the study and ​those who will not

The difference is that the decision of whether to work out or ​not is not left up to the subjects as in the observational study, but ​is instead imposed by the researcher.

At the end, when we compare the average energy levels of the two groups based on ​the **observational study** even if we find the difference between ​the average energy levels of these two groups of people, ​we can't attribute this difference solely to working out. ​Because there may be other variables that we didn't control for ​in this study, that contribute to the observed difference. ​For example, people who are in better shape might be ​more likely to regularly work out and also have higher energy levels.

However, in the **experiment**, such variables that might also contribute to the outcome ​are likely equally represented in the two groups due to the random assignment. ​Therefore, if we find a difference between the two averages, we can indeed make ​a colossal statement attributing this difference to working out.

**Eg**: 

<div align="center">
    <img src="https://a.l3n.co/crqd6e.png"/> 
</div>

The title says "Breakfast cereal keeps girls slim". But there may be 3 explanations: 

<div align="center">
    <img src="https://d.l3n.co/crqqzk.png"/> 
</div>

**Confounding variables** are extraneous variables that affect both the explanatory and the response variable, and that make it seem like there is a relationship between them. 

<div align="center">
    <img src="https://a.l3n.co/crqBbx.png"/> 
</div>

Note that correlation does not imply causation. Broadly speaking, observational studies allow us to make correlation statements, and experiments allow us to make causal statements. 

[**Sampling and Sources of Bias**] 

Q) Wouldn't it be better to just include everyone and "sample" the entire population, i.e. conduct a **census**? 

Some reasons are: 

* Conducting a census takes lots of resources. 

* Some individuals are hard to locate or measure.    
Eg: Illegal immigrants are reluctant to fill out census form. 

* Populations rarely stand still. 

Sampling is reasonable. 

For eg, while cooking, we test the taste by taking a small spoonful.    
When you taste a spoonful of a soup and decide the spoonful you tasted isn't salty enough, you're doing exploratory analysis.    
When you taste a spoonful of soup and decide the whole pot of soup isn't salty enough, you're doing inference. For your inference to be valid, the spoonful you've tasted (your sample) needs to be representative of your entire soup (your population). For eg, if your spoonful is taken only from the surface and salty portions collect at the bottom it might not be representative sample. On the other hand if you stir your soup thoroughly before tasting, your spoonful will be more likely to be representative of the whole pot. 

A few sources of **sampling bias**: 

* **Convenience sample**: Individuals who are easily accessible are more likely to be included in the sample.    
Eg: For example, say you want to find out how ​people in your city feel about a recent increase in public transportation costs. ​If you only poll people in your neighborhood, ​as opposed to a representative sample from the whole city, ​your study would suffer from convenience bias.

* **Non-response**: If only a (non random) fraction of the (initially) randomly sampled people respond to a survey such that the sample is no longer representative of the population.    

* **Voluntary response**: Occurs when the sample consists of people who volunteer to respond because they have strong opinions on the issue.

We will consider some sampling methods: 

* **Simple Random Sample** (SRS) 
* **Stratified Sample** 
* **Cluster Sample** 
* **Multistage Sample** 

In **Simple Random Sampling**, we randomly select cases from the population, ​such that each case is equally likely to be selected. ​This is similar to randomly drawing names from a hat.

In **Stratified Sampling**, we first divide the population into homogenous ​groups called strata, and then randomly sample from within each stratum. ​For example, if we wanted to make sure both genders are equally represented ​in a study, we might divide the population first into males and females, and ​then randomly sample from within each group.

In **Cluster Sampling**, we divide the population into clusters, randomly sample ​a few clusters, and then sample all observations within these clusters.

In **Multistage Sampling**, we divide the population into clusters, randomly sample ​a few clusters, and then randomly sample within these clusters.    
For example, one might divide a city into geographic regions that are on average ​similar to each other, and then sample randomly a few of these regions, ​go to these randomly picked regions, and ​then, sample a few people from within these regions.

















