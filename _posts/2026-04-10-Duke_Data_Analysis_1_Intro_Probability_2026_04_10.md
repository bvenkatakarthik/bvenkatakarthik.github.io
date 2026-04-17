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
Updated: 17/4/26 

**INTRODUCTION TO PROBABILITY AND DATA WITH R**

<a name="top"></a>

**Labs**: [Week 1 Lab](#1); 

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

[**Experimental Design**] 

The 4 principles of experimental design are: 

* **Control** 

* **Randomize** 

* **Replicate** 

* **Block** 

**Control**: To control means to compare treatment of interest to a control group. 

**Randomize**: To randomize means to randomly assign subjects to treatments. 

**Replicate**: To replicate means to collect a sufficiently large sample, or replicate the entire study. 

**Block**: To block means to block for variables known or suspected to affect the outcome. 

**Eg**: [More on Blocking] 

We would like to: Design an experiment investigating whether energy gels help you run faster. 

The treatment group gets the energy gels, and the control group does not get the energy gels. 

It is suspected that energy gels might effect pro and amateur athletes differently. 

Therefore we block for pro status. To do so: 

* We divide the sample into pro and amateur athletes. 
* We randomly assign pro and amateur athletes to treatment and control groups. Therefore, pro and amateur athletes are equally represented in the resulting treatment and control groups. 

This way, if we do find a difference in running speed between the treatment and ​control groups we will be able to attribute it to the treatment, ​the energy gel, and ​can be assured that the difference isn't due to pro status since both pro and ​amateur athletes were equally represented in the treatment and control groups.

How do we tell the difference between a blocking variable and an explanatory variable? 

Explanatory variables: Conditions we can impose on experimental units. 

Blocking variables: Characteristics that the experimental units come with, that we would like to control for. 

We will now look at some terminology. 

**Placebo**: Fake treatment, often used as the control group for medical studies. 

**Placebo effect**: Showing change despite being on the placebo. 

**Blinding**: Experimental units don't know which group they're in. 

**Double-blind**: Both the experimental units and the researchers don't know the group assignment. 

<a name="1"></a>

[**Week 1 Lab**] 

[Back to top](#top)

First, you will need to install R and RStudio. 

(R is the name of the programming language itself and RStudio is a convenient interface.)

Install R packages: 

First we install and load devtools:

We will use the devtools package to install the statsr package associated with this course. Launch RStudio, and enter the following commands in the Console:

```
install.packages("devtools")

library(devtools)
```


Now we install other packages: 

```
install.packages("dplyr")

install.packages("ggplot2")

install.packages("shiny")

install_github("StatsWithR/statsr")
```

Next, download the R Markdown file linked below, open it in RStudio, and click on Knit.

Link to the file: [Link](https://drive.google.com/file/d/1SfOURPlynuNAbFRfIK7NBTddMDe9SZ-h/view?usp=sharing). 

On knitting, we get a HTML file in a browser. (On knitting `Duke_Intro_R.rmd` file we get `Duke_Intro_R.html` file in the same directory). 

**Contents of Week 1 Lab File**: 

Today we begin with the fundamental building blocks of R and RStudio: the interface, reading in data, and basic commands.

**R Studio**: 

Your RStudio window has four panels.

Your R Markdown file (this document) is in the upper left panel.

The panel on the lower left is where the action happens. It’s called the _console_. Everytime you launch RStudio, it will have the same text at the top of the console telling you the version of R that you’re running. Below that information is the _prompt_. As its name suggests, this prompt is really a request, a request for a command. Initially, interacting with R is all about typing commands and interpreting the output.

The panel in the upper right contains your _workspace_ as well as a history of the commands that you’ve previously entered.

Any plots that you generate will show up in the panel in the lower right corner. This is also where you can browse your files, access help, manage packages, etc.

**R Packages**: 

We will use the following R packages:

- `statsr`: for data files and functions used in this course
- `dplyr`: for data wrangling
- `ggplot2`: for data visualization

You should have already installed these packages using commands like `install.packages` and `install_github`.

Next, you need to load the packages in your working environment. We do this with the `library` function. Note that you only need to **install** packages once, but you need to **load** them each time you relaunch RStudio.

```
library(dplyr)
library(ggplot2)
library(statsr)
```

To do so, you can

- click on the green arrow at the top of the code chunk in the R Markdown (Rmd) file, or
- highlight these lines, and hit the **Run** button on the upper right corner of the pane, or
- type the code in the console.

Going forward you will be asked to load any relevant packages at the beginning of each lab.

**Dataset 1: Dr. Arbuthnot's Baptism Records**: 

 Run the following command to load the data.

```
data(arbuthnot)
```

This command instructs R to load some data. The Arbuthnot baptism counts for boys and girls. You should see that the workspace area in the upper righthand corner of the RStudio window now lists a data set called `arbuthnot` that has 82 observations on 3 variables. As you interact with R, you will create a series of objects. Sometimes you load them as we have done here, and sometimes you create them yourself as the byproduct of a computation or some analysis you have performed.

The Arbuthnot data set refers to Dr. John Arbuthnot, an 18th century physician, writer, and mathematician. He was interested in the ratio of newborn boys to newborn girls, so he gathered the baptism records for children born in London for every year from 1629 to 1710. We can take a look at the data by typing its name into the console.

```
arbuthnot
```

```
## # A tibble: 82 × 3
##     year  boys girls
##    <int> <int> <int>
##  1  1629  5218  4683
##  2  1630  4858  4457
##  3  1631  4422  4102
##  4  1632  4994  4590
##  5  1633  5158  4839
##  6  1634  5035  4820
##  7  1635  5106  4928
##  8  1636  4917  4605
##  9  1637  4703  4457
## 10  1638  5359  4952
## # ℹ 72 more rows
```

However printing the whole dataset in the console is not that useful. One advantage of RStudio is that it comes with a built-in data viewer. Click on the name `arbuthnot` in the _Environment_ pane (upper right window) that lists the objects in your workspace. This will bring up an alternative display of the data set in the _Data Viewer_ (upper left window). You can close the data viewer by clicking on the _x_in the upper lefthand corner.

What you should see are four columns of numbers, each row representing a different year: the first entry in each row is simply the row number (an index we can use to access the data from individual years if we want), the second is the year, and the third and fourth are the numbers of boys and girls baptized that year, respectively. Use the scrollbar on the right side of the console window to examine the complete data set.

Note that the row numbers in the first column are not part of Arbuthnot’s data. R adds them as part of its printout to help you make visual comparisons. You can think of them as the index that you see on the left side of a spreadsheet. In fact, the comparison to a spreadsheet will generally be helpful. R has stored Arbuthnot’s data in a kind of spreadsheet or table called a _data frame_.

You can see the dimensions of this data frame by typing:

```
dim(arbuthnot)
```

```
## [1] 82  3
```

This command should output `[1] 82 3`, indicating that there are 82 rows and 3 columns (we’ll get to what the `[1]` means in a bit), just as it says next to the object in your workspace. You can see the names of these columns (or variables) by typing:

```
names(arbuthnot)
```

```
## [1] "year"  "boys"  "girls"
```

Let’s start to examine the data a little more closely. We can access the data in a single column of a data frame separately using a command like

```
arbuthnot$boys
```

```
##  [1] 5218 4858 4422 4994 5158 5035 5106 4917 4703 5359 5366 5518 5470 5460 4793
## [16] 4107 4047 3768 3796 3363 3079 2890 3231 3220 3196 3441 3655 3668 3396 3157
## [31] 3209 3724 4748 5216 5411 6041 5114 4678 5616 6073 6506 6278 6449 6443 6073
## [46] 6113 6058 6552 6423 6568 6247 6548 6822 6909 7577 7575 7484 7575 7737 7487
## [61] 7604 7909 7662 7602 7676 6985 7263 7632 8062 8426 7911 7578 8102 8031 7765
## [76] 6113 8366 7952 8379 8239 7840 7640
```

This command will only show the number of boys baptized each year. The dollar sign basically says “go to the data frame that comes before me, and find the variable that comes after me”.

Notice that the way R has printed these data is different. When we looked at the complete data frame, we saw 82 rows, one on each line of the display. These data are no longer structured in a table with other variables, so they are displayed one right after another. Objects that print out in this way are called vectors; they represent a set of numbers. R has added numbers in [brackets] along the left side of the printout to indicate locations within the vector. For example, in the arbuthnot$boys vector, 5218 follows [1], indicating that 5218 is the first entry in the vector. And if [43] starts a line, then that would mean the first number on that line would represent the 43rd entry in the vector.

We can create a simple plot of the number of girls baptized per year with the command

```
ggplot(data = arbuthnot, aes(x = year, y = girls)) +
  geom_point()
```

It produces a plot of the points. 

**R as a calculator**: 

Now, suppose we want to plot the total number of baptisms. To compute this, we could use the fact that R is really just a big calculator. We can type in mathematical expressions like

```
5218 + 4683
```

```
## [1] 9901
```

to see the total number of baptisms in 1629. We could repeat this once for each year, but there is a faster way. If we add the vector for baptisms for boys to that of girls, R will compute all sums simultaneously.

```
arbuthnot$boys + arbuthnot$girls
```

```
##  [1]  9901  9315  8524  9584  9997  9855 10034  9522  9160 10311 10150 10850
## [13] 10670 10370  9410  8104  7966  7163  7332  6544  5825  5612  6071  6128
## [25]  6155  6620  7004  7050  6685  6170  5990  6971  8855 10019 10292 11722
## [37]  9972  8997 10938 11633 12335 11997 12510 12563 11895 11851 11775 12399
## [49] 12626 12601 12288 12847 13355 13653 14735 14702 14730 14694 14951 14588
## [61] 14771 15211 15054 14918 15159 13632 13976 14861 15829 16052 15363 14639
## [73] 15616 15687 15448 11851 16145 15369 16066 15862 15220 14928
```

What you will see are 82 numbers (in that packed display, because we aren’t looking at a data frame here), each one representing the sum we’re after. Take a look at a few of them and verify that they are right.

**Adding a new variable to the data frame**: 

We’ll be using this new vector to generate some plots, so we’ll want to save it as a permanent column in our data frame.

```
arbuthnot <- arbuthnot %>%
  mutate(total = boys + girls)
```

What in the world is going on here? The `%>%` operator is called the **piping** operator. Basically, it takes the output of the current line and pipes it into the following line of code.

**A note on piping:** Note that we can read these three lines of code as the following:

_“Take the `arbuthnot` dataset and **pipe** it into the `mutate` function. Using this mutate a new variable called `total` that is the sum of the variables called `boys` and `girls`. Then assign this new resulting dataset to the object called `arbuthnot`, i.e. overwrite the old `arbuthnot` dataset with the new one containing the new variable.”_

This is essentially equivalent to going through each row and adding up the boys and girls counts for that year and recording that value in a new column called total.

**Where is the new variable?** When you make changes to variables in your dataset, click on the name of the dataset again to update it in the data viewer.

You’ll see that there is now a new column called `total` that has been tacked on to the data frame. The special symbol `<-` performs an _assignment_, taking the output of one line of code and saving it into an object in your workspace. In this case, you already have an object called `arbuthnot`, so this command updates that data set with the new mutated column.

We can make a plot of the total number of baptisms per year with the following command.

```
ggplot(data = arbuthnot, aes(x = year, y = total)) +
  geom_line()
```

Note that using `geom_line()` instead of `geom_point()` results in a line plot instead of a scatter plot. You want both? Just layer them on:

```
ggplot(data = arbuthnot, aes(x = year, y = total)) +
  geom_line() +
  geom_point()
```

Finally, in addition to simple mathematical operators like subtraction and division, you can ask R to make comparisons like greater than, `>`, less than, `<`, and equality, `==`. For example, we can ask if boys outnumber girls in each year with the expression

```
arbuthnot <- arbuthnot %>%
  mutate(more_boys = boys > girls)
```

This command add a new variable to the `arbuthnot` data frame containing the values of either `TRUE` if that year had more boys than girls, or `FALSE` if that year did not (the answer may surprise you). This variable contains different kind of data than we have considered so far. All other columns in the `arbuthnot` data frame have values are numerical (the year, the number of boys and girls). Here, we’ve asked R to create _logical_ data, data where the values are either `TRUE` or `FALSE`. In general, data analysis will involve many different kinds of data types, and one reason for using R is that it is able to represent and compute with many of them.

**Exploratory Data Analysis and Inference**: 

[**Visualizing Numerical Data**] 

We will discuss scatterplots for paired data, and other visualizations for describing distributions of numerical variables. 

Consider the following data from gapminder: 

<div align="center">
    <img src="https://c.l3n.co/cRtX23.png"/> 
</div>

Here is a scatterplot: 

<div align="center">
    <img src="https://b.l3n.co/cRt5RA.png"/> 
</div>

Since we might suspect that the economic wealth of a country might affect the average life expectancy of it's people, we set up our analysis with ​income as the explanatory and life expectancy as their response variable. (Note that labelling variables as explanatory and response does not imply causation.) 

Note that the potential outliers (to the rough curve) are labelled. 

In evaluating the relationship between two numerical variables, we must consider: 

* DIrection (Is it positive or negative?) 
* Shape (Is it linear or curved?) 
* Strength (Is the approximation strong or weak?) 
* Outliers

<div align="center">
    <img src="https://a.l3n.co/cRtGpM.png"/> 
</div>

Here is a histogram (number of countries vs life expectancy on the top; and number of countries vs income per person on the bottom): 

<div align="center">
    <img src="https://b.l3n.co/cRtaFQ.png"/> 
</div>

In a histogram, data are binned into intervals and height of the bars represent the number of cases that fall into each interval. 

Note that a histogram provides a view of the data density. 

Skewness: 

Distributions are said to be skewed to the side of the long tail. 

<div align="center">
    <img src="https://a.l3n.co/cR1Aok.png"/> 
</div>

Modality: 

A distribution may be unimodal with one prominent peak, or bimodal with two prominent peaks, and so on. 

<div align="center">
    <img src="https://b.l3n.co/cR1i2x.png"/> 
</div>

A bimodal distribution might indicate there are two distinct groups in your data. For eg, consider the distribution of heights of individuals at a preschool. There will be two peaks in the histogram, one for the kids and another for the teachers. 

Note that the chosen bin width can alter the story the histogram is telling. Here for eg, the middle bin width is ideal. 

<div align="center">
    <img src="https://b.l3n.co/cR1tFP.png"/> 
</div>

Another visalisation technique, especially useful for highlighting outliers, is a boxplot. 

<div align="center">
    <img src="https://b.l3n.co/cR1unH.png"/> 
</div>

Here median refers to the middle value of the data. Here IQR, or Inter Quartile Range, refers to difference between data ranked at 25% rank and data ranked at 75% rank. 

Here in the top box plot, it says the middle 50% of the countries have life expectancy between 65 and 77 years old. 

Note the outliers as well. 

Here are some box plot and histogram comparisions: 

<div align="center">
    <img src="https://a.l3n.co/cR1fOK.png"/> 
</div>

Consider the spatial map: 

<div align="center">
    <img src="https://b.l3n.co/cRRIWr.png"/> 
</div>

[**Measures of Center**] 

Commonly used **measures of center** are: 

* **Mean**: Arithmetic average. 

* **Median**: Midpoint of the distribution (50th percentile). 

* **Mode**: Most frequent observation. 

If these measurements are calculated from a sample, ​they're called sample statistics. ​Sample statistics are point estimates for the unknown population parameters. ​

Sample mean is denoted by ${ \overline{x} .}$ Population mean is denoted by ${ \mu . }$ 

**Eg**: 

<div align="center">
    <img src="https://a.l3n.co/cRbEPQ.png"/> 
</div>

[**Measures of Spread**] 

Some **measures of spread** are: 

* **Range**: (max - min). Not very reliable because it depends on the two most extreme values. 
* **Variance** 
* **Standard Deviation** 
* **Inter Quartile Range**

We denote sample variance by ${ s ^2 }$ and population variance by ${ \sigma ^2 . }$ 

Note that 

$${ s ^2 = \frac{1}{n-1} \sum _{i=1} ^{n} (x _i - \overline{x}) ^2 . }$$ 

**Eg**: Consider the life expectancy data. We find the variance is 

$${ s ^2 = 83.06 \text{ years} ^2 .  }$$ 

Standard deviation is roughly the average deviation around the mean. 

We denote sample standard deviation by ${ s }$ and population standard deviation by ${ \sigma . }$ 

Note that

$${ s = \sqrt{s ^2} = \sqrt{\frac{1}{n-1} \sum _{i = 1} ^{n} (x _i - \overline{x}) ^2 }.  }$$ 

Interquartile range is the range of the middle `50%` of the data, distance between the first quartile (`25th` percentile) and third quartile (`75th` percentile). 

The reason why the IQR is a more reliable measure of spread in sample data than ​the range, which is maximum minus minimum, is that it doesn't rely on the endpoints, which may be unusual observations or potential outliers.

[**Robust Statistics**] 

**Robust Statistics** are measures on which extreme observations have little effect. 

<div align="center">
    <img src="https://d.l3n.co/cTmnLD.png"/> 
</div>

<div align="center">
    <img src="https://a.l3n.co/cTmPPk.png"/> 
</div>

Robust statistics like median and IQR are used to study skewed data, with extreme observations. 

Non-robust statistics like mean and SD are used to study symmetric distributions. 

[**Transforming Data**] 

A transformation is a rescaling of the data using a function. 

When data are very strongly skewed, we sometimes transform them so they are easier to model. 

**Log transformation** is often applied when much of the data cluster near zero (relative to the larger values in the data set) and all observations are positive. 

<div align="center">
    <img src="https://d.l3n.co/cTpPVF.png"/> 
</div>

It is also used to make the relationship between the variables more linear, and hence easier to model with simple methods. 

<div align="center">
    <img src="https://c.l3n.co/cTpfv3.png"/> 
</div>

Some other transformations are 

<div align="center">
    <img src="https://c.l3n.co/cTpcED.png"/> 
</div>

Later we will see how to pick good transformations. 

Goals of transformations could be: 

* To see the data structure differently. 

* To reduce skew to assist in modelling. 

* To straighten a nonlinear relationship in a scatterplot.

[**Exploring categorical variables**] 

**Eg**: Frequency table and bar plot from a survey: 

<div align="center">
    <img src="https://a.l3n.co/ckOmBM.png"/> 
</div>

Note that barplots and histograms are different: 

* Note that we use barplots for categorical variables, and histograms for numerical variables. 

* Note that x-axis on a histogram is a number line, and the ordering of the bars are not interchangeable. 

**Eg**: Consider the contingency table of the above data: 

<div align="center">
    <img src="https://b.l3n.co/ckOpek.png"/> 
</div>
 







































