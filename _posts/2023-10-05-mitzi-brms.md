---
layout: post
title:  Bayesian Data Analysis with BRMS (Bayesian Regression Models Using Stan)
description: Quickly build robust models for data analysis and prediction using BRMS
date:   2023-10-05 15:01:35 +0300
image:  '/images/blogs/mitzi-brms.png'
tags:   [rstats]
---

Summary posted by: [Reshama Shaikh](https://www.linkedin.com/in/reshamas/)

## Intro
Mitzi Morris, a Stan developer, shows how you can quickly build robust models for data analysis and prediction using BRMS (Bayesian Regression Models Using Stan). After a brief overview of the the advantages and limitations of BRMS and a quick review of multi-level regression. We will work through an R-markdown notebook together, to see how to fit, visualize, and test the goodness of the model and resulting estimates.


## Video
<p>
<iframe src="https://www.youtube.com/embed/A1NWoKQhgJE" loading="lazy" frameborder="0" allowfullscreen></iframe>
</p>

## Resources
- [slides](https://github.com/generable/workshop-materials/raw/master/presentations/Bayesian_Multilevel_Modeling_brms_Stan.pdf)
- [repo: Mitzi's talk info](https://github.com/mitzimorris/brms_feb_28_2023)
- [video: Mitzi's talk on Software Engineering](https://youtu.be/INXMncbt09g)
- [R-Ladies New York](https://www.rladiesnyc.org/)
- [BRMS article](https://paul-buerkner.github.io/brms/articles/index.html) 
- [Statistical Rethinking](https://xcelab.net/rm/statistical-rethinking/)
- [Journal R Project](https://journal.r-project.org/archive/2018/RJ-2018-017/RJ-2018-017.pdf)
- [Barely Significant](https://www.barelysignificant.com/slides/RGUG2019/#1)
- [BRMS tutorails](https://ourcodingclub.github.io/tutorials/brms) 
- [article](https://onlinelibrary.wiley.com/doi/pdf/10.1111/eth.13225) 
- [tutorial rstanarm](https://mc-stan.org/users/documentation/case-studies/tutorial_rstanarm.html) 

## Section Timestamps of Video  
- [00:00:00](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=0s) R-Ladies NYC Intro
- [00:04:55](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=295s) Data Umbrella Intro 
- [00:08:25](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=505s) Speaker Introduction - Mitzi Morris
- [00:10:15](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=615s) What is BRMS? (Bayesian Regression Models Using Stan)
- [00:11:15](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=675s) Three reasons to use BRMS
- [00:13:51](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=831s) Bayesian Workflow Overview
- [00:15:25](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=925s) Modeling Terminology and Notation
- [00:17:54](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=1074s) Multilevel Regression
- [00:21:30](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=1290s) Regression Models in R & brief recent history of Bayesian programming languages
- [00:27:22](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=1642s) Linear Regression
- [00:28:52](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=1732s) Generalized Linear Regression
- [00:31:05](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=1865s) Regression Formula Syntax in BRMS
- [00:34:33](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=2073s) BRMS Processing Steps
- [00:37:13](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=2233s) Notebook - link to online notebook and data
- [00:37:38](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=2258s) Demo - in Markdown (.rmd)
- [00:38:18](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=2298s) Load packages (readr, ggplot2, brms, bayesplot, loo, projprod, cmdstanr)
- [00:38:38](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=2318s) Book - ARM
- [00:39:07](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=2347s) Example - Multilevel hierarchical model (with EPA radon dataset)
- [00:40:32](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=2432s) Further description of radon
- [00:41:37](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=2497s) Regression model
- [00:42:02](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=2522s) Demo - data example
- [00:42:26](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=2546s) 3 Modeling Choices
- [00:44:31](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=2671s) Choice 1 - Complete Pooling Model (simple linear regression formula)
- [00:48:22](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=2902s) Choice 2 - No Pooling Model (not ideal)
- [00:50:17](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=3017s) Choice 3 - Partial Pooling Model
- [00:56:26](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=3386s) Q&A - How to compare the different models? (run loo)
- [01:00:00](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=3600s) Q&A - Does BRMS have options for checking model assumptions?
- [01:01:00](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=3660s) Q&A What were the default priors? (student T-distribution with 3 degrees of freedom)
- [01:05:27](https://www.youtube.com/watch?v=A1NWoKQhgJE&t=3927s) References


## About the Speaker
### Bio
Mitzi Morris is a member of the Stan Development Team and serves on the Stan Governing Body. Since 2017 she has been a full-time Stan developer, working for Professor Andrew Gelman at Columbia University, where she has contributed to the core Stan C++ platform and developed CmdStanPy, a modern Python interface for Stan. She is also as an active Stan user, developing, publishing, and presenting on Bayesian models for disease mapping. Prior to that she has worked as a software engineer in both academia and industry, working on natural language processing and search applications as well as data analysis pipelines for genomics and bioinformatics.

### Connect with the Speaker
- GitHub: [@mitzimorris](https://github.com/mitzimorris)

