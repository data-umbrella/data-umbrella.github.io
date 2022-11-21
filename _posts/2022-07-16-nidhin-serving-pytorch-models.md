---
layout: post
title:  Serving PyTorch Models in Production
description: Learn to optimize pytorch model and deploy them into production
date:   2022-11-20 15:01:35 +0300
image:  '/images/blogs/nidhin-vishal-serving-pytorch-models.png'
tags:   [pytorch, deployment]
---

Summary posted by: [Sangam SwadiK](https://www.linkedin.com/in/sangam-swadi-k/)

## Event
This talk is for a data scientist or ML engineer looking to serve their PyTorch models in production. It will cover post training steps that should be taken to optimize the model such as quantization and torch script. It will also walk the user in packaging and serving the model through Facebook's TorchServe.

## Video
<p>
<iframe src="https://www.youtube.com/embed/fx_NaKwFYbg" loading="lazy" frameborder="0" allowfullscreen></iframe>
</p>

## Resources
- Repo: [GitHub Repository](https://github.com/npatta01/pytorch-serving-workshop)

## Section Timestamps of Video  
- [00:00:00](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=0s) About session
- [00:00:47](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=47s) About Data Umbrella
- [00:04:18](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=258s) Introduction
- [00:05:16](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=316s) Session agenda
- [00:06:01](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=361s) Machine learning at Walmart
- [00:12:11](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=731s) Review of some deep learning concepts
- [00:15:24](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=924s) BERT: Different architectures
- [00:16:07](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=967s) Bi-LSTM vs BERT
- [00:21:59](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=1319s) Model inference
- [00:24:21](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=1461s) Load the model
- [00:25:21](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=1521s) Test prediction
- [00:28:01](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=1681s) Inference review(inference time vs accuracy tradeoff)
- [00:29:17](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=1757s) BERT large
- [00:30:03](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=1803s) Distilled-BERT
- [00:33:54](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=2034s) Optimizing model for production
- [00:34:03](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=2043s) Post training optimization: Quantization
- [00:35:50](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=2150s) Types of Quantization
- [00:37:35](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=2255s) Quantization results
- [00:38:23](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=2303s) Post training optimization: Distillation
- [00:39:44](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=2384s) Distillation results
- [00:40:35](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=2435s) Eager execution vs Script mode
- [00:42:02](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=2522s) TorchScript JIT: Tracing vs Scripting
- [00:43:11](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=2591s) TorchScript Timing
- [00:45:21](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=2721s) Optimizing the model(Hands On)
- [00:47:36](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=2856s) Quantization(Hands On)
- [00:52:00](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=3120s) TorchScript(Hands On)
- [00:56:33](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=3393s) Deploying the model
- [00:57:13](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=3433s) Options for deploying Pytorch model
- [00:57:42](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=3462s) Benefits of TorchServe
- [00:59:41](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=3581s) Packaging a model/MAR
- [01:00:00](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=3600s) Pytorch BaseHandler
- [01:03:00](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=3780s) Built in handlers
- [01:04:15](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=3855s) Serving
- [01:05:10](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=3910s) APIs
- [01:05:32](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=3932s) Deploying the Model(Hands On)
- [01:22:11](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=4931s) Lessons Learned
- [01:23:50](https://www.youtube.com/watch?v=fx_NaKwFYbg&t=5030s) Q/A

## About the Speakers
### Bio
Nidhin Pattaniyil is a Machine Learning Engineer in Walmart Search

Vishal Rathi is a Software Engineer in Walmart Search

### Connect with the Speaker, Nidhin Pattaniyil and Vishal Rathi
- Nidhin's LinkedIn: [Nidhin Pattaniyil](https://www.linkedin.com/in/nidhinpattaniyil/)
- Vishal's Linkedin: [Vishal Rathi](https://www.linkedin.com/in/vishalkumarrathi/)
- Nidhin's GitHub: [@npatta01](https://github.com/npatta01)

## Key Links
- [Event transcripts](https://github.com/data-umbrella/event-transcripts/tree/main/2022)
- [Meetup Event](https://www.meetup.com/data-umbrella/events/286639683/)
- [Video](https://www.youtube.com/watch?v=fx_NaKwFYbg)
- [GitHub repo](https://github.com/npatta01/pytorch-serving-workshop)
