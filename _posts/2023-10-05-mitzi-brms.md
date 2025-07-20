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

The full transcript is below, following the timestamps.

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

---

## Transcript

#### 00:00 Intro
Reshama: Hello, everyone. Welcome to Data Umbrella and our collaboration with R-Ladies New York City webinar today. First of all, we're going to have the R-Ladies introduction and I'd like to introduce you all to Dorota Ritzik and she is going to share a bit about the R-Ladies community particularly the New York City Chapter. So, welcome Dorota.

#### [00:25] R-Ladies NYC Intro

Dorota: Thank you. Yes. Hi, everybody. I'm here to just give a very quick intro to R-Ladies and what we're about and I am one of the lead organizers for R-Ladies NYC, the New York City Chapter. So, there's R-Ladies Global which I'll talk about it a little bit at first and then I'll go into more detail about our specific chapter. So, what is R Ladies? R-Ladies is a worldwide organization that promotes gender diversity in our community via meetups and mentorships in a friendly and a safe environment. And our mission is to have more women and non-binary coders, developers, speakers, and leaders in our community. We believe firmly that more diversity, equity, inclusion of people developing our packages and being a part of our community is a fantastic thing and that's what we strive for. And R-Ladies Global is huge.

We have a ton of chapters all over the world. I am actually not 100% sure when this image was taken. So, it's possible there are even more chapters at this point but we are everywhere and it's actually not that hard to get involved. If you don't have a local chapter where you live, there's a way to very easily start one. So, I highly recommend looking into that. To do that, you can just send an email to info@Rladies.org to get in touch. You can follow R-Ladies on social media, on Twitter, LinkedIn, and yeah, you can follow all these different chapters from all over the world. It's great. It's a really wonderful community to be a part of.

So more about R-Ladies NYC. We were founded around 2017. So, several years after R-Ladies initially began and was already in several different places both in the US and beyond.

A few fun facts. So, we currently have actually we're up to like 2900 members on meetup at this point. So, it's quite large. That said, we don't always have a huge turnout at meetup events. So, don't be discouraged by that very large number. We host events monthly and contacting us is really easy. You can check out our website, “RLadiesNYC.org”. You could find us on meetup or on Twitter and LinkedIn and there on the left is a list of our current board members, our wonderful group of R-Ladies that helps make these monthly events possible.

So, join us. We host meetup events like presenters giving talks both technical and professional development talks. We host a book club. We host networking and social events and we typically try to attend a few conferences here and there and it's great. It's wonderful. We have a wide variety of ways to participate.

And speaking of participating, here are few ways to get involved. First and foremost, attend our meetups, follow us on Twitter and other social media pages. Join our Slack Channel and GitHub pages. And ask questions. You could even write a blog post for our website if you want to try your hand with that. We are always encouraging folks who haven't really written or presented on about our technical topic before to get involved. So, please reach out if you're interested in either of those options. And like I mentioned earlier, you could also sponsor a local chapter if you don't have one near you. Or join the board of the New York City Chapter if you're in the area. And most importantly, spread the word and tell your friends. We are always looking for more R-Ladies to join our community. Here's some information and that is it. That's the end of my presentation.

[04:40] Laura: Okay. So, Reshma, you're muted?

[04:45] Reshama: Yes, I'm going to do the Data Umbrella introduction. Hang on.

[04:48] Laura: Okay, sorry, sorry, sorry.

[04:50] Reshama: That's okay. Slides, there we go. Okay.

#### 04:55 Data Umbrella Intro:
Hey, everybody. So, I'm going to introduce the data umbrella part of it. We're really happy to do this co-promotion and co organization with R-Ladies. It's been something we've wanted to do for a while. So, I'm going to do a brief introduction. Mitzi will do a presentation and you can ask any questions in the chat and we will answer them as a good time to stop and answer. This is being recorded and the video will be available on YouTube typically within 24 hours.

Data Umbrella is a community for underrepresented persons in data science and we are a non-profit organization. This is the team of Data Umbrella. We are in a few different countries around the world and there's a bunch of people that make it happen behind the scenes. We have a code of conduct and we thank you for helping to making a welcoming, friendly, professional environment for everybody. There are various ways to support Data Umbrella. One of those ways is to follow our code of conduct. Another way that you can do it is to ask general questions and share job events and postings.

You can also donate to our nonprofit. We are an open collective and if you work for a company that uses Benevity which is company match donations, that's another way to make a donation. You can subscribe to the Data Umbrella YouTube channel. We have over 80 videos there on all different data science topics and we have over 2000 subscribers. We have a bunch of playlists. One of them is career advice. We have playlists such as data visualization contributing to open source, scikit-learn, PyMC emcee, and NumPy.

We also have a monthly newsletter and I'll share the link in the chat to find out about upcoming events and announcements. Our website which we are in the process of redesigning at the moment has a lot of resources on open-source conferences allyship language. We encourage you to check it out.

We're on all social media platforms as Data Umbrella. The place to find out about upcoming events is meetup. I've mentioned YouTube and the newsletter and Twitter and LinkedIn are the two platforms where we are the most active.

This webinar platform is big marker and then on the top you'll see a CC for closed captioning, so you can have live transcripts enabled for this presentation if you would like.

We have a call for volunteers. So, for all of our videos we add timestamps. So, if you're available to add time stamps, I'll share the link to it for this video or some other videos. You can add those timestamps on GitHub.

We also have a feedback form which you'll find in the handout section and that is I'll also share the link once I'm finished speaking and if you have any technical issues or suggestions for future event topics or any general feedback.

We have couple of upcoming events in March. The first one is what's a sales engineer from a data science of computer science background. That's going to be a very fascinating talk and on March 21st, we have MLOps from concept to product.

#### 08:25 Speaker Introduction - Mitzi Morris:
Today's talk is Bayesian Data Analysis with BRMS with Mitzi Morris who is a returning speaker. Mitzi is a member of the Stan Development Team and serves on the Stan Governing Body. Since 2017, she's been a full-time Stan developer working for Professor Andrew Gelman at Columbia University where she has contributed to the Core Stan C++ platform and developed CmdStanPy, a modern python interface for Stan. She's also an active Stan user developing, publishing, and presenting on Bayesian Models for disease mapping. Prior to that, she has worked as a software NG in both academia and industry working on natural language processing and search applications as well as data analysis pipelines for genomics and bioinformatics. Feel free to tweet about this event at Data Umbrella. And with that, I will turn off my mic and video and hand over the screen shared to Mitzi.

#### [09:24] Mitzi Morris: 
Thank you so much for that really great introduction and yes, I used to do natural language processing which is what we're not going to talk about today. Today, we're going to talk about Bayesian data analysis with BRMS and yes. So, I as a Stan developer have not really used BRMS, but BRMS is just really, I think well, it's the most widely used interface of the Stan interfaces, so/and it is absolutely fantastic. So, why don't I keep going with my slides so we can make this all very concrete and clear for you.

#### 10:15 What is BRMS? (Bayesian Regression Models Using Stan):
So, BRMS stands for Bayesian Regression and multi-level modeling in Stan. The developer who started this project is Paul Berkner. He's German which I think is why multi-level modeling is such one-word noun phrase in that particular use of multi-level modeling. BRMS package uses the R-formula Syntax which if you're familiar with are and fitting regression models in R. This is the general syntax that's used to fit to describe a model, a regression model. And so, snippet of code here we're going to go through and get to see how BRMS works. But first, some more background. 

#### 11:15 Three reasons to use BRMS:
So, the question here is why should I use BRMS? If you want to do Bayesian modeling, if you want to do regression modeling, you should use BRMS. If you're working in R and you're at all, you've heard about Stan then you should actually learn about BRMS. Because BRMS simplifies model development and it uses the extended R-formula syntax to specify the likelihood. It has a function set prior to specify the priors on all the parameters and the BRMS package has lots and lots and lots of checks so that you can make sure that your model is actually fitting your data. And the downstream analysis packages that are also part of the Stan ecosystem, bayesplot, projpred and loo.

Bayesplot is the package that gives you plotting, lets you visualize everything in your fitted model. Projpred is used to investigate the particular of interest in your model and it's helping you see what kinds of predictions those particular parameters are going to make for you. And loo stands for (Leave One Out) cross validation and loo is a tool for comparing different models. BRMS generated Stan programs are efficient and robust. So, if you have a data set and you know how you would like to model your data. You have some idea of the multi-level model that you want. Which of the predictors are going to be most relevant which of the predictors have some kind of grouping structure. Working with BRMS is very nice, because you can quickly try out a lot of different variations on how much of the problem you want to put into your model and then with BRMS, you write a whole bunch of models and you can use the downstream analysis packages to do the model comparison.

#### 13:51 Bayesian Workflow Overview:
And this in a nutshell is the Bayesian workflow. The Bayesian workflow, a lot of times when you're learning about Stan or learning about a problem set in doing Bayesian data analysis, the model is presented to you. And you're taught the model, the structure of the model, how it fits in with the data, and how well it works with your data set. But what you need to understand is that model development is the first piece of the puzzle. The second piece of the puzzle is model comparison. Some models are going to be too simple. They're easy to write, simple to understand but they don't really work that well. Some models are too complex. Some models are difficult to fit or some models are going to by building in too much complexity in your model, you might build a model that gives you a very good analysis for the data set that you have. But it might be overfitting, because you've just put too much stuff in it.

And so, you want to do model development. You want rapid model development. You want to be able to specify a lot of models very quickly and then you want to be able to do model comparison and to do that BRMS package and its friends give you everything you need.

#### 15:25 Modeling Terminology and Notation:
And here's just a little bit of modeling terminology and notation because you're going to see these terms and you're going to see some of this notation everywhere. So, I feel like we always have to go through the slide. We're talking about data and when we say data Y. We're talking about all of the data. We're not making a distinction between your outcome and your predictors. When we talk about Theta, we mean all the parameters in your model and we're building a Bayesian model. So, we're build a joint probability distribution over all the data and the parameters and when you write a stand program, Stan is solving the joint probability density. So, it's fitting all of the parameters all at once.

Now, the important things to keep your eye on when you're doing Bayesian modeling is this notion of the prior probability distribution, P of Theta. This is what you know about your problem before any data are observed, and then P of Theta given why the posterior probability distribution is what you've learned from your data. So, it's the probability of the parameters being what you've estimated them to be conditional on the data that you've seen with that starting point of P of Theta, what you already knew before you started fitting the data to the model.

The thing that we're really talking about though is the probability of why given theta, the probability of the data given the parameters. And when you know the data, when you're fitting your model, this is the model's likelihood. Once you fitted your model and you've got an estimate for Theta which is fixed, this is your sampling distribution and you use this sampling distribution to generate new data or I mean to fit new, to make predictions for new previously unseen data. So, these are our terms and the things that we're going to be talking about are prior, our posterior probability distribution, and our likelihood.

#### 17:54 Multilevel Regression:
“Multi-level regression”, I'm quoting here Richard McElreath, if you haven't read statistical rethinking this is the book that we recommend to absolutely everybody. “Statistical Rethinking” is going to make statistics. It's designed to make thinking about statistics far less confusing than it probably has been in any statistics class that you've taken. So, get “Statistical Rethinking” and read it and the argument that McElreath makes is that multi-level regression is the default form of regression because multi-level regression models handle structured data and almost all of your data has some structure. Your observations can sometimes be repeated from the same source or else they're ordered or there's some group structure in the data.

So, example of group structure is a hierarchical model where you have students in classrooms, classrooms are in a school, schools are in districts, districts are in states, states are in regions. And each of those nested areas is going to probably make the data from that particular school be of a certain flavor. So, we expect that when there's a hierarchical structure, we're getting a little bit of information from node above your bottom most, your leaf note in the tree. We're getting information from all of those contributing to your observation. Or if you have say an auto, regressive you have time series data where the next item depends on the previous several items possibly. 

Spatial data where you have some observation a we expected to be sort of similar to observations that are neighboring, spatio-temporal where we blow the whole thing out into one big 4D. It's my neighbor because it happened to the time slice right before me in the region right next to me and the volume around me. So, these are all examples of structured data and multi-level models let you say more about the data. We can estimate the variation on all levels of the model and with the multi-level structure, we can also say, well, what if I have a new group. And then I can say well I don't know what you know, I don't know anything about the items in this new group. But if I know about the items in other similar groups, I can reason about unseen groups. And what you find though is once we start building these multi-level models, your big data suddenly isn't so big anymore because you've put all of these qualifiers on every data observation and this makes working with a multi-level model both more interesting and more challenging.

#### 21:30 Regression Models in R & brief recent history of Bayesian programming languages:
So, the history of regression models in R. From somebody who spends most of her time programming in C++ and Python is like this. We have the pre-existing packages. By preexisting, I mean pre-Stan which are LM and GLM for linear models and generalized linear models which handle single level linear models. And these are part of the base are statistics package and then you have lme4 which is designed to handle higher hierarchical linear models. The goal of the Stan Project which was started in 2010 was to build a better lme4. Andrew Gelman and Jennifer Hill in 2006, 2007 put out a really fabulous book “Multi-level Regression”, “Regression Analysis in Hierarchical Models”. I forget what the exact title is. It's in a subsequent slide. What's really interesting about that book is that in Gilman and Hill, they present a lot of data sets with lme4 syntax and our code actually.

And the fact of the matter is that those models can't really be fit with lme4. It doesn't really do the right thing on the data and Andrew's point was that this is what I want lme4 to do. So, then if you later he hired some post docs to build a better lme4. And the result was the Stan probabilistic programming language and the NUTS-HMC algorithm which gives you a much more efficient way of doing Monte Carlo, Markov Chain Monte Carlo samplers, but that's not what this talk is about. So, all I can say is we use on the back end and Stan fits your model using back-end algorithm which for the best inference is going to be NUTS-HMC. And the problem is that Stan was designed by computer scientists and so the Stan probabilistic programming language while it builds on BUGS has been relatively challenging for statisticians to work with. It's a programming language. It looks a bit for both and it's difficult to actually code up a model that does what you think it's going to do. It's very easy to put bugs in your BUGS.

BUGS by the way, BUGS stands for (Bayesian Uncertainty Under Gibbs Sampling). And when I tell this to non-statisticians who've never heard of BUG, they think it's really the best name for a programming language ever. But BUGS basically really changed the course of Bayesian modeling. It made it very easy for people to write down their models because prior to BUGS, you had to write not just your model but your Gibbs samplers. So, that really set it for a pretty high bar for people who wanted to do Bayesian data analysis. With BUGS, Bayesian data analysis really took off and Stan I think has helped everybody brought it along another order of magnitude.

So, BRMS was developed in about 2016 by Paul Berkner and the goal was to simplify model specification to relieve statisticians of the need to write stand programs. Instead, it appeals to our users because it uses lme4 style formulas and R-functions to wrap Stan. So, you can work in R, but you get the goodness of Stan and the comfort of thinking about your models in a way that if you were used to using lm, glm or lme4, a way that you're used to if you're a data analysis doing statistical modeling in R.

I should also mention that RStanARM is a package which gives you precompiled Stan models and it's similar to BRMS and Spirit in that with RStanARM, if there's a package that you've been using in R for a particular kind of model, RStanARM probably has a version of that model that has a precompiled Stan model on the back end and that will probably do a better job of analyzing your data than the package that it's replacing. And by better, I mean it will be faster and it will scale to larger data sets. So, this is sort of the landscape of packages and so when I talk about BRMS to the R-Ladies, I'm hoping that most of you are going to be relatively familiar with working with of regression package in R. but if you're not, please stay tuned. I'll show you how it's done.

#### 27:22 Linear Regression:
Linear regression, this is just a quick review of linear regression. So, and I'm got this slide here because I just want everybody to sort of be really clear on the terms that I'm going to be throwing around when we get to the notebook. So, we've got a linear model. We specify the linear model. In linear regression, we're trying to fit a line to or multiplane or a multiplane to some set of observations. And the definition of a line isn't intercept with the slope, and there's some amount of noise. If we assume that this noise is independent for every observation, then we've got the guts, we've got the specification of a linear model. So, the linear model is written where we say that every observation YI is drawn from a normal observation which is centered at α β alpha plus beta times XI with variance sigma. So, sigma is that error term that we see in the formula above in the equation in the first equation and alpha plus beta XI is our linear predictor, sigma is the variance term.

#### 28:52 Generalized Linear Regression:
In a generalized linear regression, we're going to kick it up a level. So, instead of assuming a normal distribution, we can use any distributional family. And I've bolded family because you'll see, well, actually, you won't see but family is what you specify when you're using glm package or the lme4 package or BRMS to talk about some other distribution. So, you can talk about a beta distribution, a Poisson distribution if your data is discreet Poisson. And the variance parameter sigma when we're talking about a normal distribution is going to be any family specific parameter Theta. And we can generalize our linear predictor alpha plus beta XI to Ada, which we just mean any linear predictor. And we transform our linear predictor by an inverse link function so that's where we're getting the generalized linear modeling, that's our link function coming into play. And then we can use group level subscripts on our parameters to allow for the structure in the data to make our model multi-level or hierarchical.

So, given all of that, we just have the equation specification for general multi-level model which says that YI is drawn from some distributional family and we have R-function, our inverse link function applied to our linear predictor Ada and there should an XI there in that subscript, but there isn't. And we have some distributional parameters, Theta. But what we really are going to be talking about when we're working with BRMS and thinking about the models that we're fitting in BRMS are the intercept and the slope terms in our linear predictors.

#### 31:05 Regression Formula Syntax in BRMS:
So, this is the regression formula syntax. This is the very first example I had in that first call to the BRM function in BRMS. Reaction is distributed with according to an intercept term and the number of days and actually I don't even want to try to explain what this guy is saying. I just want you to observe that this is a formula that on the left-hand side we have reaction, and on the right-hand side, we have a specification for our linear predictor. And in the linear predictor because we're building a multi-level model. We have things which are population level terms, fixed effects and those are parameters where we don't differentiate. They're the same parameter for every observation no matter what group membership it might have in the structure of the data whereas group level terms which are sometimes called random effects vary by grouping factor. 

So, we're going to start putting subscripts on our parameters to talk about which group a parameter is applied, being applied to. And in BRMS, we have these group level terms where we say coefficients vertical bar group. By coefficients, we mean the terms in the linear predictor. So, if you think of the intercept is being the first column in your design matrix or your set of predictors, the intercept term is just designated by one and everything is going to be designated by the column label that it has in the predictor in your data frame which is your set of predictors. So, here in this sleep study which is where this example comes from. One of the columns in the sleep study data is labeled reaction. One of the columns is day, one of the columns is subject.

So, when we say (1+Days|subject) what we mean is that the subject is the grouping factor and we're going to see that both the intercept term and the days, the slope of the days are varying with the grouping factor. I hope that wasn't too confusing and we'll show a whole bunch of examples when we get to the notebook.

#### 34:33 BRMS Processing Steps:
What BRMS actually does is quite impressive. BRMS is writing a Stan program for you. So, you just call the BRM function and to call the BRM function, you specify your formula, you specify your data, you specify your distributional family if it's not gaussian by default, and you can specify all kinds of priors. Prior specification is a whole talk in and of itself. So, I'm not going to say anything about priors here. You specify all of these things and then, the BRM call feeds all of that into make Stan code and make Stan data then so it generates a Stand model using the Stand, a model written in the stand probabilistic programming language. That is then going to have to be compiled to C++.

So, the model code, the data, and all sorts of additional arguments which BR BRMS is putting into your call are passed to a back end. The back end can be either cmdstanr or it can be RStan, but you should probably be at this point using cmdstanr. It's the modern interface, the modern R interface to stand. It's more robust and it supports the latest version of Stan and it's more scalable. I mean, for it can handle bigger models and more data. But otherwise under the hood it's all Stan goodness. It doesn't matter if you like to use our Stand, keep using RStan. The model is compiled and fitted in Stan and then BRMS does post processing and post processing is reversing a lot of the magic that goes into compiling up writing that Stan model.

So basically, it's translating all of the names of things that are fit inside the Stan model, back to the names that you specified when you in your formula and are used in your data set. And then all the results can be investigated using all sorts of our methods in the BRMS package or the bayesplot, projpred or loo package.

#### 37:13 Notebook - link to online notebook and data:
And whoa, there should be a link to that notebook but don't worry, we are going to now jump into the demo part of the live demo part of this talk. So, this is the notebook in my screen.

#### 37:38 Demo - in Markdown (.rmd):
I don't know if putting it into full screen mode will make it bigger. I hope so. So, I'm just going to work through this little, our markdown document. So, the first thing we're going to do is do some stuff that I always put into a notebook. And we're going to load all the packages that you might want. I not actually using ggplot2 in this notebook, but never hurts to have ggplot2.

#### 38:18 Load packages (readr, ggplot2, brms, bayesplot, loo, projprod, cmdstanr):
So, we're going to load the BRMS, the bayesplot, the loo, the projpred, and cmdstanr. Although, you probably don't need to load. Well, I don't know if you need to load cmdstanr. So, we're going to load everybody.

#### 38:38 Book – ARM:
The book that Andrew and Jennifer wrote in 2006 is “Data Analysis Using Regression and Multilevel Hierarchical Models”. Andrew refers to that as by short hand as ARM applied regression modeling. It's a really great book and it makes a lot of things very clear if you're at all interested in a really lucid discussion of causal inference. I highly recommend this book.

#### 39:07 Example - Multilevel hierarchical model (with EPA radon dataset):
And the example that they wait till chapters 11 & 12 to get to actual multi-level hierarchical models. And one of the first example data sets they use is the radon level dataset, which is a dataset that I did my previous talk on and in the chat earlier, there's a link Lubliana lecture that's more digging into what's going on with that particular dataset. Which is an old historical dataset that's mainly of interest to play around with hierarchical models. So, this was a national level survey. Andrew and Jennifer analyze data for the state of Minnesota, which consists of 919 measurements from residential houses from 85 counties. And the measurements were taken either in the basement or on the ground floor and although it's not entirely clear, I'm pretty sure that if the house had a basement, the measurement was taken in the basement. So, the only times that a measurement would have been taken on the ground floor in a house is if there no basement. And another EPA data set provides the soil uranium level for each county.

#### 40:32 Further description of radon:
So why is this interesting? Radon gas is a carcinogen that happens to be particularly deadly if you're a smoker. So, if you're a smoker and you have a house that has a basement and you're living in the basement and there's no better ventilation, your chance of contracting lung cancer somewhere along the way goes up really astronomically. So, nowadays, modern building codes and general awareness of radon has made this much less of a problem. Thanks in part to this EPA activity in the 1990s. So, radon gas comes from the ground. It's a byproduct of uranium decay. Uranium is radioactive and it has a very very long half-life, decaying slowly. One of those products of uranium decay is radon.

#### 41:37 Regression model:
And the regression model is going to try to predict the home radon level on the log scale. Based on the county in which the house is located, the floor on which the measurement was taken and the amount of soil uranium for that county. So, the data looks like this.

#### 42:02 Demo - data example:
We have the floor, the county name, the amount of data, the log radon level, the log uranium level which as you can see is uniform across the county, and the county ID which is a factor which will be very useful when we're trying to group by county ID.

#### 42:26, 3 Modeling Choices:
So, the modeling choices that we have, to completely pull all the data across the state of Minnesota. So, we're going to do a single regression, average home radon level in Minnesota is based on all 919 observations. Or we can try to use county information and a stupid model is the no-pooling model where we run 85 separate regressions to estimate the home radon levels by county. So, we just say as much data as I have on a county, that's as much data as I'm going to use to figure out what's going on in that county and then we have partial pooling, a multi-level model. Counties are similar. So, we're going to build a multi-level regression which says that we're going to share information across all counties.

For every county, we estimate what's going on in that county, but at the hierarchical one level up we say that all counties are drawn from a distribution for that is a county distribution. So, that there's a certain amount, there's a certain location that we expect, certain set of parameters that are common hyper parameters in the model. Which say that, okay, for any county in Minnesota we sort of expected to have this general characteristic. We expect a certain radon level and we expect a certain amount of variants across the county and given that hype, that set of hyper parameters, then we're going to estimate what's going on in each individual county.

#### 44:31 Choice 1 - Complete Pooling Model (simple linear regression formula):
So, the complete pooling model is just a simple linear aggression formula. And so, in BRMS, the BRM function, all we need to do, the first argument to the BRM function is the formula. The formula is very simple here and the data set is the Minnesota radon data set. So, we can just run that and what going to happen? Well, actually we're going to see a little bar. Right now, this is the C++ compiler compiling the generated Stan code. As soon as it's done compiling it, this model runs like lightning because it's a really, really, really simple model and it runs four chains using the NUTS-HMC sampler and then, it gives us the summary of how well it fit that model. So, for this gaussian family that works and we're just doing the simple the not simple but we're doing yeah, we are doing a simple linear regression where we expect everything to be distributed normally.

We have the identity, the links here. This is your generalized linear model links where we're using the identity function for both the MU and the sigma of the gaussian. The formula is log radon is distributed according to the floor. The level on which the measurement is taken and we have estimate for the models intercept and for the floor. And this all makes perfect sense because the way that things are coded, the basement is coated as floor zero and ground floor is coded as floor one. And we know that radon gas, the levels of radon gas increase the lower you go in a building. So, we expect the slope of the regression line to be negative. Meaning, that if you're in the basement, your radon level will probably be higher than if you're on the ground floor and there's a certain amount of variants here. That's our sigma parameter.

We can visualize what's going on by using the BRMS conditional effects on (fit_complete_pool). And that is going to give us a beautiful plot. The floor is actually discrete. So, it's either zero or it's one, but here you see the regression line in blue and the amount of uncertainty that's about the 50% interval around the regression line in dark gray. So, if you're in the basement, your log radon level is going to be higher than if you're taking the measure on the ground floor, and this confidence that the uncertainty grows because we have far fewer measurements which are taken on the ground floor. Pretty much 80% of the measurements in this data set were taken in the basement. Because in Minnesota, most homes that were in the survey had basements.

#### 48:22 Choice 2 - No Pooling Model (not ideal):
The no pooling model looks kind of silly because it's silly. So, what we're doing here in this formula is we're saying there is no general intercept and that is because for each county we're going to have its own intercept. So, we can fit that model too. And again, we can see that BMS has generated the Stan code and C++ is compiling the Stan code, takes a few seconds to do that. Takes like zero time to run the model and now, we get oh yeah. So, if we look at this, let's look at this in the output window. Oh no, we definitely want to look at this here. This is so beautiful. This is the conditional effects plot for when we have 85 separate intercepts.

So, we've got a linear regression model and if we go up to the previous one of these guys, here we see if we pull all of the data, we only have a single regression line. Here, we're saying that we're going to still use the floor as the slope of the line and we're having 85 different intercepts. So, we get 85 different beautiful lines that are all parallel and I think this is just really fabulous. This is also a really stupid model and you don't want to do it.

#### 50:17 Choice 3 - Partial Pooling Model:
So, let's move on to the first model which we say that we want to have a partial pooling model where we're going to pull information between counties but for every county, we're going to estimate its own intercept. So, this is what the formula looks like in BRMS and now we can fit this model. And when we're done fitting the model, again, it takes the thing that takes the longest when running BRMS is just the C++ compiler translating your model to C++. Because the C++ compiler is doing a lot of optimizations so that your resulting model will run will be performant. And this plot the base plot MCMC interval plot here we’re just plotting the county level the estimates for the county level regression parameter.

So, we have 85 different parameters, one per county and what's going on in this plot which is not actually that easy to read, because there are 85 things is that four counties which have a lot of observations, we get much tighter 50% intervals around the estimated mean. And in this data set, there are very few counties in Minnesota where all the people live. They're essentially the counties for the Minnesota, Saint Paul, and also for Duluth. The rest of Minnesota is really rural and so for most counties, you have three or four maybe five observations, which is why you want to be building a multi-level model because you need to pull your information across your regions. And then finally, we have the [INAUDIBLE WORD 52:26] which is the varying slope varying intercept model. Which says that, okay, for every county we expect that the floor effect, the slope might be different for that county as well as the intercept term. So, then we can fit this model and we can do exactly the same plots.

And I think we're getting almost to 8 o'clock. I don't know how much longer I have to talk here, but one more example and then we will be ready for questions. So, now the sampling is actually taking a little bit longer because this is a more complicated model. It has more levels. It has more parameters and it has more hard choices to make. So, if we look at what's going on here, this plot doesn't look that much. Well, actually it looks quite a bit different than this plot. Things are moving around and what we see is that the regression now is pulling ever more closer to the center, the means now are pulling more together. So, you're getting more and more pulling especially down here.

And finally, we can add in one more predictor. The “log uranium”, which is the same across all observations in the county. We can see what adding log uranium is going to do to this model. So, this is a varying slope varying intercept model adding in another predictor the log uranium and we don't need to do anything on the county level for log uranium because log uranium is already on a per county level. Although you know play around with it by all means don't take my word for it. See what happens if you add log uranium into this group level effects. And adding log uranium, does it change things? It does, yes. It pulls things way more towards the center. So, that's pretty much it.

#### [56:21] Reshama: 
Hey, Mitzi. We have a question which is, how do you compare the different models?

#### [56:26] Mitzi Morris: 
Oh, yes. Perfect question. Yes. Great.

#### 56:26 Q&A - How to compare the different models? (Run loo):
So, am I still sharing my R screen?

[56:31] Reshama: Yes.

#### [56:32] Mitzi Morris: 
Okay. So, now we've got, well, we'll just go over here. We're done with the notebook. So, thank you. This is the last, this should be the list, selling the notebook, so you're going to add it yourself. So, we've now got these various fits, right? Now, if we say, now we're going to run the loo function and so, what this is saying is that, you've asked me the right question. But we're all going to have to together read the documentation for the loo package to understand what these estimates are doing and what it is saying is that, you know what? I'm not really sure. Let's try it, a simpler one. The loo function is designed specifically to compare your models. So, the short answer to your question is you run loo.

[58:19] Reshama: Hey, Mitzi. Another question is this RMD available on Git? I did link to your GitHub. Is this the same exact R markdown file that people can access.

[58:33] Mitzi Morris: Oh yeah, I put it on my GitHub repo, yes.

#### [58:35] Reshama: Okay got it. And then another question that came up is can BRMS be used for non-hierarchical data structure and non-regression type of analysis?

[58:51] Mitzi: It can definitely be used for non-hierarchical data structure. So, there are plenty of multi-level models which are not hierarchical and a non-regression, what do you mean by a non-regression type of analysis? The answer there is no. The package is about regression. And how to view the trace of the parameters. To view the trace of the parameters, we can do something like plot. And I think this will give you, yeah. What is that doing? Not so bad. There you get some nice trace plots.

#### 01:00:00 Q&A - Does BRMS have options for checking model assumptions?
Reshama: Another question here is does BRMS have options for checking model assumptions?

[01:00:07] Mitzi Morris: What do you, yes, definitely. That is all about the prior predictive checking. So, your model assumptions essentially are your priors and BRMS has functions for prior predictive checks and it has posterior predictive checks. And yes, checking your model assumption is very, very, very important and that’s really part of the cool stuff of the generated Stan code for BRMS. It anticipates that you're going, it generates a Stan program that has everything you need to do the model checking and the posterior. Oh, thank you. Thank you, Richard Montes.

#### 01:01:00 Q&A What were the default priors? (Student T-distribution with 3 degrees of freedom):
I know it's not in scope, but curious what priors were used. These are the default priors. The default priors here are a student T distribution with three degrees of Freedom and Paul Berkner works a lot with Akivatari, one of the key Stan developers. Key contributors, coauthor of Bayesian Data Analysis and he's very interested in the effect of the priors. And so, you can specify whatever prior makes sense and there are a lot of different theories about what a good prior firm model is. The prior really depends on your data. So, you shouldn't rely on the default priors but the default priors are chosen to be very robust. And over the course of the time that the Stan project has existed, we've learned so much more about how these models behave, because we can fit more complex models with more different kinds of data and with larger datasets.

We've learned a lot about the behavior of what priors are good. And the difference between Hamiltonian Monte Carlo, the HMC algorithm that is used by the Stan MCMC sampler and the pre generation of MCMC samplers, the Gibbs samplers is that for Gibbs sampling, you had to choose certain kinds of priors just so that the Gibbs sampler didn't fall over and the Hamiltonian Monte Carlo algorithm behaves very differently. So, there was a lot a lot of discussion and investigation that's gone into what makes a good prior. And what is recommended as a good prior for a model has changed a lot from say 2007 when Gelman & Hill use all sorts of interesting priors in that text to now. And the priors are specified that Carlos wants to know how the priors are specified.

Laura, I'm really sorry. I don't know how you can use this in Excel, but Carlos wants to know how the priors are specified. The priors are specified via an argument to the BRM function and you create something called BRMS prior object. So, the BRMS documentation will tell you everything you need to know about how to specify your priors and there's several exam and vignettes in the BRMS documentation that should help you. They're written by academic researchers. They have a certain flavor but if you look around and ask questions on the Stand discourse, you should be able to do just fine. Anything else.

[01:04:47] Reshama: Last call for questions if anybody has any questions. Meanwhile, I'll read some of the comments which is thank you for the great talk. “Thank you, Mitzi. This was an incredibly approachable introduction”.

[01:05:02] Mitzi Morris: So glad to hear it. Thank you all. Great questions.

[01:05:13] Reshama: Alright.

[01:05:15] Mitzi Morris: Oh, oh, oh, I want to share one more thing.

[01:05:07] Reshama: Go ahead.

[01:05:18] Mitzi Morris: My final slide. I think I need to go to slide 13.

#### 01:05:27 References
Because these are everything that you should read next. So yeah, take a screenshot and check out some of those URLs and the slides and the notebook are up on GitHub for you.

[01:05:57] Reshama: Mitzi, thank you so much for the excellent talk. Everybody, thank you for joining us and the video will be available very soon. Have a great evening, morning, wherever you are. Bye everybody and thanks Dorota.

