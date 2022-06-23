---
layout: post
title:  Intro to Probabilistic Programming with PyMC
description: Learn how open source probabilistic programming makes Bayesian inference algorithms near the frontier of academic research accessible to a wide audience.
date:   2022-01-11 15:01:35 +0300
image:  '/images/blogs/austin_r2.png'
tags:   [python]
---

Summary posted by: [Reshama Shaikh](https://reshamas.github.io)

## Introduction

Austin Rochford, a maintainer of PyMC, presented to the Data Umbrella community an introduction to probabilistic programming with PyMC, with a particular emphasis on the how open source probabilistic programming makes Bayesian inference algorithms near the frontier of academic research accessible to a wide audience.

In the last ten years, there have been a number of advancements in the study of Hamiltonian Monte Carlo and variational inference algorithms that have enabled effective Bayesian statistical computation for much more complicated models than were previously feasible. These algorithmic advancements have been accompanied by a number of open source probabilistic programming packages that make them accessible to the general engineering, statistics, and data science communities. PyMC is one such package written in Python and supported by NumFOCUS.

Below in the outline is a summary of topics that were covered.

## Topics Covered
- Probabilistic programming from two perspectives
    - Philosophical: storytelling with data
    - Mathematical: Monte Carlo methods
- Probabilistic programming with PyMC
    - The Monty Hall problem
    - Robust regression
- Hamiltonian Monte Carlo
    - Aesara
- Lego example
- Next Steps

## Video
<p>
<iframe src="https://www.youtube.com/embed/Qu6-_AnRCs8" loading="lazy" frameborder="0" allowfullscreen></iframe>
</p>

## Key Links
- [Transcript](https://github.com/data-umbrella/event-transcripts/blob/main/2022/41-austin-pymc.md)
- [Meetup Event](https://www.meetup.com/data-umbrella/events/282790294/)
- [Video](https://youtu.be/Qu6-_AnRCs8)

## Resources
- [GitHub repo](https://github.com/pymc-devs/pymc-data-umbrella/tree/main/webinars)
- [Jupyter Notebook](https://github.com/pymc-devs/pymc-data-umbrella/blob/main/webinars/probabilistic_programming_with_pymc/notebook.ipynb)
- [Austin's website](https://austinrochford.com/talks.htmlhttps://austinrochford.com/talks.html)
- [Arviz](https://github.com/arviz-devs/arviz)
- [PyMC Series of events](https://pymc-data-umbrella.xyz/en/latest/about/probabilistic_programming_with_pymc/index.html)

## Contribute to PyMC: upcoming online hackathon (sprint)
- [Data Umbrella & PyMC Online Open Source Sprint](https://www.meetup.com/data-umbrella/events/283178769/)


## Section Timestamps of Video

### Intro
- [00:00:00](https://www.youtube.com/watch?v=d48WGkePFq0&t=0s) Reshama introduces Data Umbrella
- [00:04:40](https://www.youtube.com/watch?v=Qu6-_AnRCs8&t=280s) Austin begins
- [00:06:15](https://www.youtube.com/watch?v=Qu6-_AnRCs8&t=375s) Talk agenda
- [00:08:08](https://www.youtube.com/watch?v=Qu6-_AnRCs8&t=488s) Probabilistic programming from two perspectives
- [00:08:53](https://www.youtube.com/watch?v=Qu6-_AnRCs8&t=533s) What is probabilistic programming?
- [00:10:15](https://www.youtube.com/watch?v=Qu6-_AnRCs8&t=615s) Mathematical: Monte Carlo Methods
- [00:13:55](https://www.youtube.com/watch?v=Qu6-_AnRCs8&t=835s) Monty Hall Problem (game: Let's Make a Deal)
- [00:16:15](https://www.youtube.com/watch?v=Qu6-_AnRCs8&t=975s) Solve Monty Hall Problem using PyMC (solution)
- [00:18:42](https://www.youtube.com/watch?v=Qu6-_AnRCs8&t=1122s) Using aesara
- [00:21:00](https://www.youtube.com/watch?v=Qu6-_AnRCs8&t=1260s) Doing inference with sampling
- [00:24:00](https://www.youtube.com/watch?v=Qu6-_AnRCs8&t=1440s) What is Aesara? (It is based on Theano.) PyMC's tensor computational backend, fills niche such as PyTorch or TensorFlow.
- [00:25:20](https://www.youtube.com/watch?v=Qu6-_AnRCs8&t=1520s) Using PyMC to do robust regression: with example Anscombe's Quartet
- [00:28:10](https://www.youtube.com/watch?v=Qu6-_AnRCs8&t=1690s) Using arviz (library with pre-built visualizations and statistical routines that will help you understand the results of your inference with PyMC.
- [00:33:08](https://www.youtube.com/watch?v=Qu6-_AnRCs8&t=1988s) What is Ridge Regression? (normal priors on your coefficients)
- [00:36:05](https://www.youtube.com/watch?v=Qu6-_AnRCs8&t=2165s) Student-T Distribution
- [00:39:00](https://www.youtube.com/watch?v=Qu6-_AnRCs8&t=2340s) Why are we using Aesara? To do Hamiltonian Monte Carlo.
- [00:43:10](https://www.youtube.com/watch?v=Qu6-_AnRCs8&t=2590s) Bayesian Analysis of Lego Prices
- [00:49:00](https://www.youtube.com/watch?v=Qu6-_AnRCs8&t=2940s) Recommended books
- [00:50:37](https://www.youtube.com/watch?v=Qu6-_AnRCs8&t=3037s) Meenal talks about upcoming PyMC sprint
- [00:56:30](https://www.youtube.com/watch?v=Qu6-_AnRCs8&t=3390s) Q&A with Austin

## About the Speaker

### Bio
Austin Rochford is the Chief Data Scientist at Kibo Commerce. He is a recovering mathematician and is passionate about math education, Bayesian statistics, and machine learning.

### Connect with the Speaker

- LinkedIn: [Austin](https://www.linkedin.com/in/austin-rochford/)
- Twitter: [@AustinRochford](https://twitter.com/AustinRochford)
- GitHub: [@AustinRochford](https://github.com/AustinRochford/)

## Upcoming Events
Join our Meetup group for more events: [Data Umbrella Meetup](https://www.meetup.com/data-umbrella)
