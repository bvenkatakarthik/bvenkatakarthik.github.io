---
layout: post
title: "Simulating the Economy"
author: "Karthik"
categories: journal
tags: [documentation,sample]
---

I am working on the problem of simulating the economy. 

It seems one can use multi agent systems to simulate the economy. 

```
"All models are wrong, but some are useful." 

- E. P. Box
```

Perhaps: One can run low risk experiments on the simulated economy and one might learn something about the real economy. 

Reading list: 

Updated: 5/11/2026 

* QuantEcon page. [Link](https://quantecon.org/about/). 

* Thomas Sargent's page. [Link](http://www.tomsargent.com/). 

* John Stachurski's page. [Link](https://johnstachurski.net/). 

* "An Introduction to Economic Dynamics" by Raghavendra, Piiroinen. 

* "Economic Networks" by Sargent, Stachurski. [Link](https://networks.quantecon.org). 

* "From Dynamics to Novelty: An Agent-Based Model of the Economic System" by Recio et al. 

* "Intelligent Agent-Based Modeling in Economics" By Gyawali et al. [Link](https://direct.mit.edu/isal/proceedings/isal2026/38/96/138136). 

* "Large Language Models as Simulated Economic Agents" by Horton et al. [Link](https://arxiv.org/abs/2301.07543). 

* "An AI can simulate an economy millions of times to create fairer tax policy" by Heaven. [Link](https://www.technologyreview.com/2020/05/05/1001142/ai-reinforcement-learning-simulate-economy-fairer-tax-policy-income-inequality-recession-pandemic/). 

* Economics Simulation. Hacker News post. [Link](https://news.ycombinator.com/item?id=10962026). 

* "Economics Simulation" by Norvig. [Link](https://www.norvig.com/ipython/README.html). 

* "Emergent Bartering Behaviour in Multi-Agent Reinforcement Learning" by Johanson et al. Google DeepMind. [Link](https://deepmind.google/blog/emergent-bartering-behaviour-in-multi-agent-reinforcement-learning/). 

* "Economic Simulations with AI". Digital Economy Lab. [Link](https://digitaleconomy.stanford.edu/project/economic-simulations-with-ai/). 

* "Economy of Minds" by Qi et al. [Link](https://arxiv.org/abs/2606.02859). 

* "Simulated Economy" by Fantl. Blogposts. [Link](https://jasonfantl.com/posts/Simulated-Economy-(1)/). 

* "ABIDES-Economist: Agent-Based Simulation of Economic Systems with Learning Agents" by Dwarakanath et al. [Link](https://arxiv.org/abs/2402.09563v1). 

* abcEconomics. [Link](https://abce.readthedocs.io/en/master/). 

* "The AI Economist Economic Policy Design using Deep Reinforcement Learning and AI Simulations" by Zheng. [Link](https://youtu.be/VKE9GFXNgLo?si=vTRIwxq8DQoM_hg8). 

* "Economic Models: Simulations of Reality" by Ouliaris. [Link](https://www.imf.org/external/pubs/ft/fandd/basics/models.htm). 

Related: 

* "The Mathematics of Inequality" by Boghosian. [Link](https://now.tufts.edu/2017/10/12/mathematics-inequality), [Link](https://youtu.be/q_S3rULyN8Q?si=cOH1eLrWW63YPiZt). 

* "The Mathematics of Poverty, Inequality, and Oligarchy" by Boghosian, Borgers. [Link](https://www.siam.org/publications/siam-news/articles/the-mathematics-of-poverty-inequality-and-oligarchy/). Forbes article. [Link](https://www.forbes.com/sites/eriksherman/2023/11/30/a-theory-of-wealth-inequality-is-the-flip-of-a-coin/). 

* Mandelbrot on Income Inequality. [Link](https://www.webofstories.com/play/benoit.mandelbrot/116). 

* "The Challenge of World Poverty" by Duflo, Banerjee. [Link](https://youtube.com/playlist?list=PLUl4u3cNGP620R91K4KP_fO4l3eeK5lDn&si=hkmRIoToTCu2Vv3l). 

* "Economic inequality from statistical physics point of view" by Yakovenko. [Link](https://youtu.be/nGl9I-dFRFs?si=qr11owpx9oDu4XPx). 

* GiveDirectly initiative. Article: [Link](https://news.mit.edu/2022/givedirectly-cash-charity-0816). Website: [Link](https://www.givedirectly.org/). 

* Psychology and Economics course. [Link](https://ocw.mit.edu/courses/14-13-psychology-and-economics-spring-2020/pages/syllabus/). 

* How can people contribute to a healthy economy? Gemini's response: [Link](https://drive.google.com/file/d/1_KNsGCEMiHK-n4RsgfTKO9SEFNY-fcV1/view?usp=sharing). 

* Countries which recovered from poverty. Gemini's response: [Link](https://drive.google.com/file/d/1krtB_Yt43zv4HnZmg6UN5G2N4tEMVWO5/view?usp=sharing). 

Attempt 1. 

The goal is to study an approximate model of an economy. 

I guess the model should be simple enough that one is able to study it, and complex enough that it capture key aspects of a current economy (like the tendency of wealth to be Pareto distributed). 

Consider ${ n }$ agents ${ P _1, \ldots, P _n . }$

Consider an "economy" with total wealth ${ 1 . }$ Suppose initially the wealth is equally distributed, that is ${ P _1 }$ has wealth ${ 1/n, }$ ${ \ldots, }$ ${ P _n }$ has wealth ${ 1/n . }$ 

Let ${ W _1 (t) }$ denote the wealth of ${ P _1 }$ at time step ${ t , }$ ${ \ldots , }$ ${ W _n (t) }$ denote the wealth of ${ P _n }$ at time step ${ t . }$ 

So we know the initial condition ${ W _1 (0) = 1/n, }$ ${ \ldots, }$ ${ W _n (0) = 1/n . }$ 

Suppose the wealths evolve as follows. 

Suppose in time step ${ t }$: 

* The agents ${ P _1 , \ldots, P _n }$ start with wealths ${ W _1 (t-1), \ldots, W _n (t-1) }$ respectively.

* One of ${ P _1 , \ldots, P _n }$ is chosen, with probability ${ W _1 (t-1), \ldots, W _n (t-1) }$ respectively. (So it is more likely that an agent with higher wealth is chosen). 

* Now, the chosen ${ P _i }$ creates economic value, and there is a wealth transfer of ${ \alpha W _i (t-1) ,}$ from each agent whose current wealth exceeds ${ \alpha W _i (t-1) . }$ (So intuitively the value created by the chosen agent is proportional to the wealth they currently have). 

This process continues. 

**Q**) Is this a good enough model of an economy? Any pointers? 

**Q**) How do the wealths evolve under this model? Or perhaps a different model?

One problem I see with the model is: In this model, once an agent's wealth is ${ 0 , }$ the model allows no scope for the agent to gain more wealth. This could perhaps be remedied. There is no credit system, investments, etc. There are probably other shortcomings as well. 

One sanity check for a good model can be: The wealths tend to be Pareto distributed. 

I am primarily an economics enthusiast. Any comments, pointers would be helpful. 

Thanks in advance! 
