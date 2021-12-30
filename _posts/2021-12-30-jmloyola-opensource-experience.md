---
layout: post
title:  "Data Umbrella Interview: Juan Martín Loyola"
description: Juan Martín Loyola shares his experience collaborating in open source.
date:   2021-12-30 15:01:35 +0300
image:  '/images/blogs/interview_image.jpg'
tags:   [opensource]
---

Author:  [Reshama Shaikh](https://reshamas.github.io) & [Juan Martin Loyola](https://jmloyola.github.io/)


1. __Tell us about yourself.__

	My name is Juan Martín Loyola, I'm a computer science Ph.D. student from San Luis, a province in the middle of Argentina, working on early classification models for text. This is related to the problem of document categorization where we are also interested in the classification speed (there is a cost associated with the classification delay).

2. __How did you first get involved in open source?__

	My involvement with the open-source world started, as with most people, as a user. First, as a teenager, when my father brought a [SUSE Linux](https://en.wikipedia.org/wiki/SUSE_Linux) cd and installed it on our home computer. Although it didn't last long as our main operating system it introduced me and my siblings to the GNU/Linux world. Later on, in college, I began to use open source software for many tasks, for example, the operating system, the browser, and the stack to program for my classes. It pushed me to keep learning about the system and its components. I loved that! Nevertheless, I still felt like a newcomer. I believed that to contribute to those projects, one needed to be an expert, thus I never thought of contributing back. As I realized later, that is not true.

	The first project I got involved in and that I sent some patches to was [PyMC](https://github.com/pymc-devs/pymc). I found out about the project thanks to [Osvaldo Martin](https://github.com/aloctavodia), a researcher and core contributor of PyMC that works in the same research institute as I do. I attended a couple of his graduate courses and seminars where he used PyMC for probabilistic modeling. We talked about the project and he suggested a couple of ideas I could work on. A couple of days later I sent [my first pull request (PR) to PyMC](https://github.com/pymc-devs/pymc/pull/3389). I was excited, but the review process had just started. Although it looked like a simple PR, I realized that there is a lot of "extra" work you should do to get your code accepted. For example, discuss with other developers about the importance of the patch (sometimes after tinkering with the idea of the PR, the core developers realize that there is no need for the patch --that is why it is important to discuss it before starting to code), agree on a possible solution, and write tests and documentation for the changes. I said extra work, but actually, this is essential work needed to ensure the project is stable and easily understandable by the users.

3. __How did you get involved in PyMC Google Summer of Code?__

	I learned about Google Summer of Code (GSoC) from Osvaldo and a collegue, [Agustina Arroyuelo](https://github.com/agustinaarroyuelo). They worked in 2018 on the project ["Module for Approximate Bayesian Computation"](https://summerofcode.withgoogle.com/archive/2018/projects/5594656209371136). Agustina told me it was a great experience, and that motivated me to apply for the next year. In early 2019, Osvaldo and I started writing the proposal for the project ["Bayesian Additive Regression Trees in PyMC3"](https://summerofcode.withgoogle.com/archive/2019/projects/5713417321578496). While the proposal was being reviewed, I kept working on the project to improve my knowledge of the code-base and to get to know the rest of the core contributors. Fortunately, the project got accepted and we started working. Overall GSoC was a great experience and I will recommend it to anyone that wants to contribute to a particular project and can allocate some time for it.

4. __How did you learn of the Data Umbrella LATAM sprint? Through any specific person?__

	I found out about the Data Umbrella LATAM sprint 2021 through Twitter. I'm not an active social media user, but I do check Twitter once in a while. A month before the sprint I read a tweet from [Data Umbrella](https://twitter.com/DataUmbrella) in my feed inviting people to apply to the scikit-learn LATAM sprint. Since I wanted to get back to contributing to open source, I quickly applied.

5. __What was your sprint experience and how was the experience with your pair programming partner and core devs?__

	The sprint was amazing, in all its stages: pre-sprint, sprint, and post-sprint. I got the chance to meet, talk and discuss with awesome people. It was also a great experience to boost my understanding of the project since some of the project members were actively answering questions. Not only that, but the core developers were also giving programming tips, and reviewing every PR. This gave fluency to the sprint. At the same time, this was the first time I pair-programmed with somebody remotely. Thankfully all went right and we had no technical problems. Throughout the sprint, me and my pair programming partner, [Tomas Moreyra](https://github.com/tomasmoreyra), managed to make two PRs. We were pretty hyped.

6. __Any specific challenges and benefits to being in South America?__

	I would say that the biggest barrier to participating in open source is the language. Although most of the South American data science community understands English, the proficiency level varies a lot. Most can read with no problem, but there are some members of the community that is not comfortable writing or speaking in English. That represents a challenge when you have to discuss a topic. Some people don't mind having grammatical errors and can quickly answer any question people ask them. The problem is that the message might not be understood. On the other hand, people who check their messages several times to make sure the grammar is correct, lose a lot of time. The problem is that not everyone has the time to do that. Thus, they shy away from contributing.

7. __How did you first get involved in scikit-learn?__

	I first started contributing to scikit-learn a couple of weeks before the Data Umbrella LATAM sprint. Those were easy fixes in the code, but they allowed me to learn how to contribute to the project. After that, I participated in two Data Umbrella sprints focused on scikit-learn. During that period I made many documentation contributions. Given the experience gained with those PRs, [Guillaume Lemaitre](https://github.com/glemaitre) encouraged me to work on more technical issues related to the code-base. Motivated by this, I started working in [exposing the attribute `n_iter_` from BaseLibSVM](https://github.com/scikit-learn/scikit-learn/pull/21408). While working on this, the scikit-learn team (suggested by [Julien Jerphanion](https://github.com/jjerphan/)) invited me to be part of the triage team of scikit-learn to keep contributing. I happily accepted :).

8. __Any advice or tips you have for people starting in computer science or data science fields?__

	Only not to be scared to ask questions. Thoughtful questions. It had happened to me that I was afraid to ask a question because I thought people would laugh at my "easy" questions. Don't be. Your focus should be on improving your skills and understanding the topics you are being taught. It's ok to ask the same questions twice or more times if you still don't understand something. Nevertheless, you should always raise questions respectfully.

9. __What are your favorite resources, books, courses, conferences, etc?__

	It depends on the kind of topic and the depth one wants to acquire. If it is research-related, I'd probably read papers. Nowadays, most papers are published first in [arxiv](https://arxiv.org/), so we have free access to a lot of the state of the art research. But, the amount of papers that come out every day is enormous. To keep up with it, I'd recommend [arxiv-sanity](https://arxiv-sanity-lite.com/). If you want to get started on a topic, I would look for an introductory blog, for example, [Distill](https://distill.pub/) which explains hard topics with a lot of illustrations to make it a little bit easier. For daily technology news, I use [Lobsters](https://lobste.rs/).

	More personally, I really liked the book "Pattern Recognition and Machine Learning" by Bishop. I found it a little hard in some parts, especially some "trivial" demostrations (maybe it was a sign that I should have reviewed a little bit of math beforehand), but overall I enjoyed reading it. Maybe next year I'll read it again to try to cover the sections I didn't completely understood the first time. For courses, we now have a plethora of available resources but one I skim over and found interesting is [cs224n from Stanford](http://web.stanford.edu/class/cs224n/). Finally, one blogpost I loved was ["The Unreasonable Effectiveness of Recurrent Neural Networks"](http://karpathy.github.io/2015/05/21/rnn-effectiveness/) by Andrej Karpathy. It explains some of the theory of recurrent neural networks with code and clarifying images.

10. __What are your hobbies, outside of school, CS, and open source?__

	I love playing "futbol" (soccer in the USA, football for the rest of the English world) with friends, but I must confess that it has been a couple of years since I last ran the whole hour ^^. It doesn't help that we are going through a pandemic.

	I also like listening to music from various styles. If I had to choose a couple of records I would pick:
	- [Lateralus, Tool](https://en.wikipedia.org/wiki/Lateralus)
	- [Led Zeppelin II, Led Zeppelin](https://en.wikipedia.org/wiki/Led_Zeppelin_II)
	- [The Wall, Pink Floyd](https://en.wikipedia.org/wiki/The_Wall)
	- [Clics Modernos, Charly Garcia](https://en.wikipedia.org/wiki/Clics_modernos)
	- [Libertango, Astor Piazzolla](https://en.wikipedia.org/wiki/Libertango)

	Finally, I'm trying to read more literature, in particular books from Latin American authors. The last two books I read were ["The Seven Madmen"](https://www.goodreads.com/book/show/25403359-the-seven-madmen) and ["The Flamethrowers"](https://www.goodreads.com/book/show/40788939-the-flamethrowers) by Roberto Arlt.

11. __Other things you might want to share.__

	I would like to thank Reshama Shaikh and the whole Data Umbrella crew for the amazing work they have done. The sprints and all the other activities are tremendously helpful to the underrepresented people in data science and the open-source world.
