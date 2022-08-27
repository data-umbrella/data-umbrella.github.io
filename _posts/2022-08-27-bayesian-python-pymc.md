---
layout: post
title:  Bayesian Modeling and Computation in Python
description: Learn to do data science and Bayesian analysis with the open source python library PyMC.
date:   2022-08-26 15:01:35 +0300
image:  '/images/blogs/bayesian-modeling.png'
tags:   [python, bayesian]
---

Summary posted by: [Reshama Shaikh](https://reshamas.github.io)

## Using Python for Bayesian Analysis

- [PyMC](https://www.pymc.io/welcome.html) is 100% **pure Python code**
- PyMC is **open source**
- PyMC is **fast** because it is built on top of [Theano](https://en.wikipedia.org/wiki/Theano), a python library for fast numerical computation
- Since PyMC is written in Python, we can [use the same syntax](https://www.superdatascience.com/podcast/pymc-for-bayesian-statistics-in-python) for other steps, such as: plotting, data input, outputting, and writing a model
- **Interoperability** with the rest of the Python ecosystem where it's really just a library and not a framework, including **deployability**
- PyMC can be compiled with [JAX](https://en.wikipedia.org/wiki/Google_JAX), which is a new compute library from Google


## Introduction

Given how popular Python is and how Bayesian methods are being more widely used, it makes sense that PyMC, a probabilistic programming language, is gaining in popularity.

In this presentation, a PyMC developer gives an overview of PyMC and why you should supercharge your data science skills with probabilistic programming. The talk is organized by layers from more generic to more specific. We will cover the main features of the Bayesian paradigm, then probabilistic progamming, then PyMC and we will finish covering some hands on examples of Bayesian modeling with PyMC.

## Video
<p>
<iframe src="https://www.youtube.com/embed/6dc7JgR8eI0" loading="lazy" frameborder="0" allowfullscreen></iframe>
</p>

## Topics
 
These are some of the topics covered in this presentation.  
- [00:00](https://youtu.be/6dc7JgR8eI0?t=0) Reshama introduces Data Umbrella
- [06:55](https://youtu.be/6dc7JgR8eI0?t=416) Oriol begins presentation
- [07:50](https://youtu.be/6dc7JgR8eI0?t=470) Bayesian Paradigm (Data is considered once fixed it has been observed; Model parameters are treated as random)
- [11:20](https://youtu.be/6dc7JgR8eI0?t=680) Prior information (prior distribution)
- [12:30](https://youtu.be/6dc7JgR8eI0?t=750)  Uncertainty
- [13:55](https://youtu.be/6dc7JgR8eI0?t=835)  Probabilistic programming
- [14:42](https://youtu.be/6dc7JgR8eI0?t=882)  Generative modeling
- [14:48](https://youtu.be/6dc7JgR8eI0?t=888)  Automagical solvers
- [15:55](https://youtu.be/6dc7JgR8eI0?t=955)  Inference algorithms (MCMC: HMC + NUTS, Metropolis, Gibbs); Variational inference: ADVI
- [16:55](https://youtu.be/6dc7JgR8eI0?t=1015) PyMC3
- [17:58](https://youtu.be/6dc7JgR8eI0?t=1078) PyMC version 4 is built on top of Aesara, whch is built on top of Theano
- [19:30](https://youtu.be/6dc7JgR8eI0?t=1170) PyMC is extensible
- [20:30](https://youtu.be/6dc7JgR8eI0?t=1230) PyMC is open source and community-driven
- [23:45](https://youtu.be/6dc7JgR8eI0?t=1425) PyMC in practice
- [23:50](https://youtu.be/6dc7JgR8eI0?t=1430) Example 1: Coal mining disasters
- [30:00](https://youtu.be/6dc7JgR8eI0?t=1800) Example 2: Housing prices in Berlin
- [36:30](https://youtu.be/6dc7JgR8eI0?t=2190) Acknowledgments
- [38:15](https://youtu.be/6dc7JgR8eI0?t=2295) Resources, where to go next
- [40:45](https://youtu.be/6dc7JgR8eI0?t=2445) python code example
- [43:45](https://youtu.be/6dc7JgR8eI0?t=2625) Oriol's journey in open source and statistics; was a Google Summer of Code scholar

## More Resources on: Bayesian Modeling and Computation in Python

For more information and resources, check out our series of videos on probabilistic programming and [PyMC playlist](​​https://www.youtube.com/playlist?list=PLBKcU7Ik-ir99uTvN0315hIVLuyj4Q1Gt) by PyMC library team members:  
- [Intro to Probabilistic Programming with PyMC](https://youtu.be/Qu6-_AnRCs8) (Austin Rochford)
- [Contributing to PyMC Documentation](https://youtu.be/fzpmLWQNj4A) (Oriol Abril Pla)
- [My Experience Contributing to PyMC](https://youtu.be/Iq0dY5hU4D4) (Ricardo Vieira)
- [An Example Pull Request to PyMC](https://youtu.be/NbmdFJsnuuo) (Reshama Shaikh)
- [Intro to NumPy Operations](https://youtu.be/oud3Jd1FJ7c) (Meenal Jhajharia)


<p float="left">
   <a href="https://www.youtube.com/playlist?list=PLBKcU7Ik-ir99uTvN0315hIVLuyj4Q1Gt">
  <img src="../images/pymc-sprint/pymc-playlist.png" width="60%" height="60%" style="border:0px;margin:0px">
</a>
</p>