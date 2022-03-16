---
layout: post
title:  Tutorial on Arrays, Linked Lists and Graphs; Identifying the Right Tool for the Job
description: Use Python to code a linked list and use graphs for efficiency.
date:   2022-03-15 15:01:35 +0300
image:  '/images/blogs/clair.png'
tags:   [python, graphs]
---

Summary posted by: [Reshama Shaikh](https://reshamas.github.io)

## Introduction

Clair Sullivan, a Developer Advocate for Neo4j, presented to the Data Umbrella community a tutorial on arrays, linked lists and graphs.

It is easy and convenient to treat all data as an array. They are the basis of much of Python and a simple data structure to deal with. But there are times that arrays fail us, such as on element insertion and the pre-allocation of memory. There is power and efficiency in linking data through data structures such as linked lists. We will see how using linked lists can reduce Big O complexity and solve a variety of problems. Then we will explore how graph data structures take this a step further and open up a world of new options and opportunities for efficient computation.

## Outline of Tutorial

Below is a summary of topics that were covered:  
- PART 1: Arrays
- PART 2: Linked Lists
- PART 3: LeetCode
- PART 4: Graphs

## Video
<p>
<iframe src="https://www.youtube.com/embed/gWGyvfU80kc" loading="lazy" frameborder="0" allowfullscreen></iframe>
</p>

## Key Links
- [Meetup Event](https://www.meetup.com/data-umbrella/events/283846178/)
- [Video](https://youtu.be/gWGyvfU80kc)
- [GitHub repo](https://github.com/cj2001/data_umbrella_linked_lists)
 
## Resources
- [#IWD2022 1-minute video](https://youtu.be/Z81fx_Fa34o)
- [Colab Notebook: welcome.ipynb](https://colab.research.google.com/notebooks/welcome.ipynb)
- [LeetCode reverse linked lists](https://leetcode.com/problems/reverse-linked-list/)
- Byte Size Neo4j [Series of videos](https://neo4j.com/video/bite-sized-neo4j-for-data-scientists/)
- [LeetCode Notebook: leetcode206.ipynb](https://github.com/cj2001/data_umbrella_linked_lists/blob/main/notebooks/leetcode206.ipynb)

## Summary of Topics
- Arrays
- Lists, a special array
- Linked lists
    - Singly-linked
    - Doubly-linked
- What to do when all of the above fails?

## Section Timestamps of Video  

- [00:00:00](https://www.youtube.com/watch?v=gWGyvfU80kc&t=0s) Reshama introduces Data Umbrella
- [00:04:39](https://www.youtube.com/watch?v=gWGyvfU80kc&t=279s) Clair begins introduction
- [00:06:14](https://www.youtube.com/watch?v=gWGyvfU80kc&t=374s) link to repo: https://github.com/cj2001/data_umbrella_linked_lists
- [00:06:35](https://www.youtube.com/watch?v=gWGyvfU80kc&t=395s) Summary of what will be covered
- [00:07:26](https://www.youtube.com/watch?v=gWGyvfU80kc&t=446s) Arrays
- [00:08:45](https://www.youtube.com/watch?v=gWGyvfU80kc&t=525s) Big O: O(n)
- [00:09:01](https://www.youtube.com/watch?v=gWGyvfU80kc&t=541s) Lists: Dynamic Arrays (insert, append)
- [00:10:45](https://www.youtube.com/watch?v=gWGyvfU80kc&t=645s) (Singly) Linked List (node, pointer)
- [00:13:05](https://www.youtube.com/watch?v=gWGyvfU80kc&t=785s) List Insertion
- [00:14:05](https://www.youtube.com/watch?v=gWGyvfU80kc&t=845s) repo intro: https://github.com/cj2001/data_umbrella_linked_lists
- [00:15:30](https://www.youtube.com/watch?v=gWGyvfU80kc&t=930s) list of resources
- [00:17:25](https://www.youtube.com/watch?v=gWGyvfU80kc&t=1045s) Notebook on linked lists: https://github.com/cj2001/data_umbrella_linked_lists/blob/main/notebooks/basic_linked_list.ipynb
- [00:17:44](https://www.youtube.com/watch?v=gWGyvfU80kc&t=1064s) Linked List 1: [Create a linked list in python]. There is no data structure in python called linked list. It needs to be created. Here is how.
- [00:20:12](https://www.youtube.com/watch?v=gWGyvfU80kc&t=1212s) Linked List 2: Insert a new node in the beginning of a list
- [00:21:20](https://www.youtube.com/watch?v=gWGyvfU80kc&t=1280s) Linked List 3: Insert a new node at the end of list
- [00:22:55](https://www.youtube.com/watch?v=gWGyvfU80kc&t=1375s) Linked List 4: Insert a new node in between items in a list
- [00:24:20](https://www.youtube.com/watch?v=gWGyvfU80kc&t=1460s) Linked List 5: Delete a node
- [00:27:39](https://www.youtube.com/watch?v=gWGyvfU80kc&t=1659s) (Doubly) Linked List
- [00:28:35](https://www.youtube.com/watch?v=gWGyvfU80kc&t=1715s) Benefits of Linked Lists vs Arrays
- [00:29:54](https://www.youtube.com/watch?v=gWGyvfU80kc&t=1794s) What You Need to Implement a Linked List
- [00:30:33](https://www.youtube.com/watch?v=gWGyvfU80kc&t=1833s) LeetCode #206: Reverse a Linked List (Iterative Solution) (https://leetcode.com/problems/reverse-linked-list/) (https://github.com/cj2001/data_umbrella_linked_lists/blob/main/notebooks/leetcode206.ipynb)
- [00:39:11](https://www.youtube.com/watch?v=gWGyvfU80kc&t=2351s) Graphs: collection of nodes and relationships
- [00:41:47](https://www.youtube.com/watch?v=gWGyvfU80kc&t=2507s) How to Get Into Graphs with Python
- [00:42:45](https://www.youtube.com/watch?v=gWGyvfU80kc&t=2565s) Graph python packages vs graph databases
- [00:44:20](https://www.youtube.com/watch?v=gWGyvfU80kc&t=2660s) sandbox.neo4j.com (get free databases instances)
- [00:52:00](https://www.youtube.com/watch?v=gWGyvfU80kc&t=3120s) Graph Data Science (https://github.com/cj2001/data_umbrella_linked_lists/blob/main/notebooks/graph_data_science.ipynb)
- [00:56:00](https://www.youtube.com/watch?v=gWGyvfU80kc&t=3360s) Cypher query
- [01:00:20](https://www.youtube.com/watch?v=gWGyvfU80kc&t=3620s) Q&A

## About the Speaker

### Bio

Dr. Clair Sullivan is currently a data science advocate at Neo4j, working to expand the community of data scientists and machine learning engineers using graphs to solve challenging problems. She received her doctorate degree in nuclear engineering from the University of Michigan in 2002. After that, she worked in a variety of research positions within the US national laboratory and federal government and as a professor at the University of Illinois at Urbana-Champaign. In 2017 she accepted a job at GitHub as a Machine Learning Engineer and in 2021 she joined Neo4j as a Data Science Advocate. She has authored 4 book chapters, over 20 peer-reviewed papers, and more than 30 conference papers.

### Connect with the Speaker, Clair Sullivan

- LinkedIn: [dr-clair-sullivan](https://www.linkedin.com/in/dr-clair-sullivan-09914342/)
- Twitter: [@CJLovesData1](https://twitter.com/CJLovesData1)
- GitHub: [@cj2002](https://github.com/cj2001)
