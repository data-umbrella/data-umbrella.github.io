---
layout: post
title:  Tutorial on Automating Workflows Using GitHub Actionson
description: Learn about GitHub Actions and how they can accelerate your application development workflows.
date:   2022-01-23 15:01:35 +0300
image:  '/images/blogs/gh-actions2.png'
tags:   [python]
---

Author: [Reshama Shaikh](https://reshamas.github.io) and [Gonzalo Peña-Castellanos](https://twitter.com/goanpec)

## Introduction

In January 2022, Gonzalo Peña-Castellanos, presented to the Data Umbrella community a comprehensive tutorial on Automating Workflows with GitHub Actions.  

Below in the outline is a summary of topics that were covered. Learn about GitHub Actions and how they can accelerate your application development workflows. A workflow is a configurable automated process made up of one or more jobs. We will learn how to configure and use workflows existing current actions and start looking at how an action can be developed from scratch.

## Outline of Tutorial
- PART 1: GitHub, Workflows and GitHub Actions
- PART 2: Actions components
- PART 3: GitHub Actions marketplace
- PART 4: Workflow syntax
- PART 5: Creating a Workflow
- PART 6: Creating a custom action

## Video
<p>
<iframe src="https://www.youtube.com/embed/d48WGkePFq0" loading="lazy" frameborder="0" allowfullscreen></iframe>
</p>



## Key Links
- [Transcript](https://github.com/data-umbrella/event-transcripts/blob/main/2022/42-gonzalo-github-actions.md)
- [Meetup Event](https://www.meetup.com/data-umbrella/events/282772806/)
- [Video](https://youtu.be/d48WGkePFq0)

## Resources
- [Slides](https://bit.ly/github-workflows)
- [GitHub Support](https://support.github.com)
- [GitHub Actions documentation](https://docs.github.com/en/actions)

## References
- [Napari repo](https://github.com/tlambert03/napari-plugin-action)
- [Mariatta's talk on continuous integration](https://youtu.be/vLBr_AfomUY)

## Section Timestamps of Video

### Intro
- [00:00:00](https://www.youtube.com/watch?v=d48WGkePFq0&t=0s) Reshama introduces Data Umbrella
- [00:04:15](https://www.youtube.com/watch?v=d48WGkePFq0&t=255s) Gonzalo introduces self and projects
- [00:06:36](https://www.youtube.com/watch?v=d48WGkePFq0&t=396s) ---Outline of talk  


### PART 1: GitHub, Workflows and GitHub Actions
- [00:07:55](https://www.youtube.com/watch?v=d48WGkePFq0&t=475s) ---PART 1: GitHub, Workflows and GitHub Actions
- [00:11:00](https://www.youtube.com/watch?v=d48WGkePFq0&t=660s) GitHub Development Workflow with "events"
Can trigger "events" or "actions" based on these events: issue opened, PR submitted, comment on issue or PR is merged, closed or updated
- [00:11:55](https://www.youtube.com/watch?v=d48WGkePFq0&t=715s) Continuous integration and continuous development (CI/CD)
- [00:12:05](https://www.youtube.com/watch?v=d48WGkePFq0&t=725s) ("webhook" mentioned), cross-platform testing is done by CI/CD  
- [00:13:55](https://www.youtube.com/watch?v=d48WGkePFq0&t=835s) Microsoft and how GitHub Actions started; GH actions is a nice wrapper around Azure pipelines   
- [00:15:07](https://www.youtube.com/watch?v=d48WGkePFq0&t=907s) What are GitHub Actions? A platform to "automate development workflows"  
- [00:15:22](https://www.youtube.com/watch?v=d48WGkePFq0&t=922s) Mariatta's talk on CI/CD  
- [00:16:00](https://www.youtube.com/watch?v=d48WGkePFq0&t=960s) What are developer workflows?  CI/CD does not mean GitHub actions. It is one of *many* workflows you can automate, but it is not the only one.
- [00:16:13](00:16:13) Types of developer workflows

### PART 2: GitHub Action Components 
- [00:19:35](https://www.youtube.com/watch?v=d48WGkePFq0&t=1175s) ---PART 2: GitHub Action Components  
- [00:19:52](https://www.youtube.com/watch?v=d48WGkePFq0&t=1192s) Workflows (& YAML files)   
- [00:20:28](https://www.youtube.com/watch?v=d48WGkePFq0&t=1228s) Events  
- [00:20:55](https://www.youtube.com/watch?v=d48WGkePFq0&t=1255s) Jobs and Runners  
- [00:21:52](https://www.youtube.com/watch?v=d48WGkePFq0&t=1312s) Actions  

### PART 3: Workflow Syntax
- [00:22:55](https://www.youtube.com/watch?v=d48WGkePFq0&t=1375s) ---PART 3: Workflow Syntax  
- [00:23:15](https://www.youtube.com/watch?v=d48WGkePFq0&t=1395s) Workflow yaml file 
- [00:24:00](https://www.youtube.com/watch?v=d48WGkePFq0&t=1440s) YAML = YAML Ain't Markup Language   
- [00:26:21](https://www.youtube.com/watch?v=d48WGkePFq0&t=1581s) Event types: Labels  
- [00:26:44](https://www.youtube.com/watch?v=d48WGkePFq0&t=1604s) Event types: Pushing / PRs / Branches  
- [00:27:19](https://www.youtube.com/watch?v=d48WGkePFq0&t=1639s) Event types: Manual dispatch  
- [00:29:03](https://www.youtube.com/watch?v=d48WGkePFq0&t=1743s) Dependencies between jobs  
- [00:29:36](https://www.youtube.com/watch?v=d48WGkePFq0&t=1776s) Context: expressions (run jobs conditionally)
- [00:30:53](https://www.youtube.com/watch?v=d48WGkePFq0&t=1853s) Context: default environment variables
- [00:31:18](https://www.youtube.com/watch?v=d48WGkePFq0&t=1878s) Strategies
- [00:32:57](https://www.youtube.com/watch?v=d48WGkePFq0&t=1977s) User-defined environment variables: Global
- [00:33:52](https://www.youtube.com/watch?v=d48WGkePFq0&t=2032s) Actions
- [00:35:35](https://www.youtube.com/watch?v=d48WGkePFq0&t=2135s) Other topics

### PART 4: GitHub Actions Marketplace
- [00:37:06](https://www.youtube.com/watch?v=d48WGkePFq0&t=2226s) ---PART 4: GitHub Actions Marketplace
- [00:37:06](https://www.youtube.com/watch?v=d48WGkePFq0&t=2226s) Q&A: Can we use on MacOS and Windows?
- [00:38:03](https://www.youtube.com/watch?v=d48WGkePFq0&t=2283s) Q&A: Meaning of "17" in cron?
- [00:40:22](https://www.youtube.com/watch?v=d48WGkePFq0&t=2422s) Cron job in GitHub actions without need for Heroku?
- [00:41:00](https://www.youtube.com/watch?v=d48WGkePFq0&t=2460s) GitHub Workflow Rates (pricing)
- [00:42:26](https://www.youtube.com/watch?v=d48WGkePFq0&t=2546s) Q&A: Why is MacOS more expensive than others for GitHub pricing?
- [00:43:39](https://www.youtube.com/watch?v=d48WGkePFq0&t=2619s) Q&A: Can jobs be run in parallel?
- [00:47:40](https://www.youtube.com/watch?v=d48WGkePFq0&t=2860s) Q&A: Where to go for support for GitHub Actions?
- [00:49:48](https://www.youtube.com/watch?v=d48WGkePFq0&t=2988s) ---PART 4: GitHub Actions Marketplace  
- [00:55:10](https://www.youtube.com/watch?v=d48WGkePFq0&t=3310s) GH Actions: data science, conda
- [00:58:52](https://www.youtube.com/watch?v=d48WGkePFq0&t=3532s) stale issue labeler

### PART 5: Creating a Workflow: live examples
- 01:01:05 ---PART 5: Creating a Workflow: live examples
- 01:01:28 Migrating from other services (Azure Pipelines, CircleCI, GitLab CI/CD, Jenkins, Travis CI)
- 01:02:03 Starter Workflows!
- 01:02:20 https://github.com/actions/starter-wo...
- 01:02:35 Example: Create a new repository and start! First issue
- 01:08:00 Example: Suggested GH action for the repo: "Simple Workflow"

### PART 6: Creating a Custom GitHub Action
- 01:13:05 ---PART 6: Creating a Custom GitHub Action
- 01:13:20 Q&A: How to save (download) artifacts?
- 01:17:13 ---PART 6: Creating a Custom GitHub Action
- 01:17:20 3 ways to run GitHub Actions (Composite, JavaScript, Docker Container)
- 01:20:40 Example: Napari
- 01:21:45 napari-svg plugin
- 01:22:45 composite action
- 01:24:40 Other topics for custom actions (Docker, JavaScript / Typescript actions, Outputs on actions)
- 01:25:20 Talley Lambert with napari: https://github.com/tlambert03/napari-...
- 01:34:15 Q&A: What would an advanced GitHub Actions webinar cover?
- 01:34:35 Q&A: Resources for Learning GitHub Actions: https://docs.github.com/en/actions
- 01:36:20 Typescript example
- 01:37:35 JavaScript Action template
- 01:41:30 Closing words  


## About the Speaker

### Bio
Gonzalo is a Colombian Civil Engineer with an MSc. in Hydroinformatics and an MSc. in Sanitary Engineering that discovered a passion for Software Development and Data Science which led him to collaborate in different open source projects and to eventually join Anaconda, Inc (formerly known as Continuum Analytics) and currently Quansight, Inc as Senior Software Engineer, and Data Scientist (in development). 

He is an active member of the open source community contributing to different projects and a leader in the Python Colombia Community helping shape and organize communities such as Django Girls Colombia, Python Bucaramanga, Python Colombia and the national and Latin American Python Conferences, PyCon Colombia (2018, 2019, 2020) and SciPy Latam (2019, 2021) respectively.

Gonzalo is currently a core developer with Project Jupyter and Project napari. He is the author of the setup-miniconda Github Action to help automate conda environment and workflows.

### Connect with the Speaker, Gonzalo Peña-Castellanos

- LinkedIn: [@goanpeca](https://www.linkedin.com/in/goanpeca)
- Twitter: [@goanpeca](https://twitter.com/goanpeca)
- GitHub: [@goanpeca](https://github.com/goanpeca)
- Instagram: [@goanpeca](https://www.instagram.com/goanpeca/?hl=en)