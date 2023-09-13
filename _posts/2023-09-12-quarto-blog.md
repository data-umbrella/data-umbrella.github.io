---
layout: post
title:  Reproducible Publications with Python and Quarto 
description: A tutorial by Thomas Mock of Posit.
date:   2023-09-12 15:01:35 +0300
image:  '/images/blogs/quarto-transcript.png'
tags:   [python]
---

## Intro
Quarto is an open-source scientific and technical publishing system that builds on standard markdown with features essential for scientific communication. The system has support for reproducible embedded computations, equations, citations, crossrefs, figure panels, callouts, advanced layouts, and more. In this talk we'll explore the use of Quarto with Python, describing both integration with IPython/Jupyter and the Quarto VS Code extension. Users can author Jupyter notebooks or documents as plain text markdowns with code in Python, R, Julia or Observable. Quarto includes the ability to publish high-quality articles, reports, presentations, websites, blogs, and books in HTML, PDF, MS Word, ePub, Reveal.js and more.


## Video
<p>
<iframe src="https://www.youtube.com/embed/TnVgHE9LAiw" loading="lazy" frameborder="0" allowfullscreen></iframe>
</p>

## Resources
- [Slides](https://thomasmock.quarto.pub/python-umbrella/#/)

## Connect with the Speaker, Thomas Mock
- Twitter: [@thomas_mock](https://twitter.com/thomas_mock)
- GitHub: [@jthomasmock](https://github.com/jthomasmock)

## Transcript

#### Reshama 00:02 
Hey, everybody! Welcome to Data Umbrella’s Webinar!

I am unfortunately unable to share my video today because it's been over 85 degrees Fahrenheit in New York and that impacts my internet access at times, so no video today, sorry about that. I'm going to do a brief introduction and then Thomas is going to do his presentation. And anytime during the talk you can ask questions, but we'll answer the questions. Thomas will answer the questions at the end of the talk. 

This is being recorded and will be placed on the Data Umbrella YouTube. Data Umbrella - if you're unfamiliar, we are a community for underrepresented persons in data science and we are a nonprofit organization. This is our team who makes it all happen behind the scenes. We're dedicated to providing harassment free experience for everyone and we thank you for helping to make this a welcoming, friendly community for all. 

There are various ways to support Data Umbrella. The first and foremost is to follow our code of conduct. We'd love it if you could share Data Umbrella events with people in your network and let them know about it. And we have some open source initiatives as well. We have Video Time students where we do timestamps of all of our videos and that helps users find our content. 

We have a website which is not on Quarto, I'm sad to say it is using JavaScript, but maybe we'll change that. We also have a Sprint website for PyMC and scikit-learn and our blog and our events board is as well open source. 
Another way you can support Data Umbrella is to donate to our nonprofit. We're an open collective and if your company uses Benevity for company match donations, that's an option as well. This is just a sampling of some of our videos on our YouTube. We have a playlist for career advice and we have other playlists for data visualization, data Science for beginners, and a lot of open source. We focus a lot of open source and data science. 

We also have a monthly newsletter which is at dataumbrella.substack.com. It's really just once a month if we have the resources to do it. So we won't send you any spam or sell your email address. Actually, I'm going to skip over this one. If you want to scan in the QR code, this gives you all of our most used links. Our Meetup Group is the place to find out about upcoming events. YouTube is our videos, our newsletter GitHub is our open source projects and so on. 

We use big marker for this platform, so at the very top you'll see CC which stands for Closed Captioning or Live Transcripts. So feel free to if you'd like to see Live transcript, pick the language of your choice. I do hear that English is the most accurate, but you can try the other languages if you like. 

We have a feedback form which I'm going to share in the chat. But if you have any suggestions for future event topics, if you have any technical issues you want to communicate, if you would like to speak at an event, let us know. Our upcoming events on July 25th we're having Machine Learning visualization using Yellow Brick, which is an open source library. And on August 8th Mitzi will be presenting on tracking the COVID-19 Challenge accounting for Missing Information. 

Today's talk is reproducible publications with Python and Quarto. Tom is a product manager at Posit. I actually can't read the rest because it's covered, but for the work I'll let Thomas introduce IDE products. He was formerly a product manager in the Quarto team. And you can find Thomas Mock on GitHub at ‘jthomasmock’ or Twitter ‘thomas_mock’. And with that I am going to hand over the mic and screen share to Thomas.

#### Thomas Mock 04:14 
Thank you so much Reshama for the introduction and for having me here today. Can you confirm you see my screen okay?

#### Reshama 04:21 
Yes.

#### Thomas Mock 04:22 
Great. I'm going to share my slides in the chat so you can get them there. And then the URL is also here on the screen at Thomasmock.quarto.pub/python-umbrella. As Reshama mentioned, I'm a product manager here at Posit. I manage the Posit workbench in RStudio IDE and Platform. So definitely a lot of love for the data science community and using IDES to do better reproducible data science. 

So as far as Quarto, this presentation will be about 35 slides or slow and really focused on a broad overview with some deep dives on specific topics, but really doing this kind of overview of what Quarto can do and how it might be interesting for you. Feel free to ask questions in the chat and I'll get to those at the end of today's presentation.

First thing I always want to mention is people may have not heard the name Posit, but you might have heard of the name RStudio. So RStudio is a public benefit corp and we recently became Posit as another company name as a rebrand. And we are still a public benefit corp. We mainly went through this rebrand so that people are aware that while we still are investing in tools for R and tools like RStudio, that for a long time we've also supported languages like Python. 

So that's why part of why I'm giving this presentation today is talking about how Quarto is this multilingual tool for R, for Python, for Julia, for JavaScript and for future data science languages as they come up. 

#### As far as what is Quarto? 05:55 

Number one. If you've ever heard of things like our markdown, Quarto could be thought of as like the next generation of our markdown. But again, this language agnostic idea, if you were to ask the Quarto team, they would say something like Quarto is an open source scientific and technical publishing system that builds on standard markdown with features essential for scientific communication. 

So importantly, this includes things like computation, so you can use data science languages like Python, R, 
Julia, or even Observable JavaScript directly inside the notebook document itself. You can also write or mark up or mark down the kind of structure via Pandoc flavored markdown with a lot of enhancements that are provided through Quarto. And then you can create all sorts of different outputs. So from a single source you can create a document, a presentation like today that I'm giving that was created in Quarto entire websites, blogs, books, even manuscripts that you can submit to journals. 

Overall, it's a literate programming system in this tradition of things like Org-Mode or Weave.jl, R Markdown, [iPyPublish], Jupyter Book, et cetera, where there's lots of different kind of frameworks, and we're trying to add to this community and combine a few different things where you have multiple languages available for them. 

#### Origins of Quarto 07:13

As far as the origins of where Quarto came from, it is an open source project sponsored by Posit Again, formerly known as RStudio Public Benefit Corp. So if you're trying to figure out where we came from, that's our history when we were founded over a decade ago. We have over ten years of experience with the R Markdown Open Source framework, which is a similar system to Quarto, but that was very R specific. Overall, though, this decade of experience with it convinced us that a lot of the core ideas were sound and could be applied to other languages. 

We realized that, of course, the number of languages and computational runtimes that are used for science are very broad. And it's not just R, it's not just Python, it's not just Julia or JavaScript, it's some combination across all these different ecosystems. So Quarto is really this ground up reimagining of our Markdown modernized and made, multilingual and multi-engine so that you can use whatever language you want with it and have a consistent framework that is used across all of them. 

Quarto absolutely gets inspiration from our Markdown as well as the Jupyter ecosystem. It can actually work directly with plain text documents like our Markdown, but we call them Quarto documents, as well as Jupyter notebooks in the IPython notebook structure itself. This overall goal, though, for Quarto is this computational document. So a document that includes the source code that creates it, as well as having a notebook format and a plain text flavor. We're really big fans of plain text, but there's lots of people who want to use, say, a Jupyter notebook or an IPython notebook as their entry point into Quarto, and that's absolutely supported as well. 

And importantly, you want to be able to use quarto to extend further, to make it either more reproducible or better automate and have things like parameterization and programmatic automation and generation of your reports or documents that you're creating. When we think of moving beyond just a computational document, though, we want to have support for things like scientific markdown. Of course, you get started in something like Word. And if you're trying to create these technical documents, you hit this really big learning curve and it's hard to do all of the things you want there, or it requires a lot of fiddling. 

So you're like, okay, well, maybe I'll switch to LaTeX. And it's like you start using LaTeX and you're like, wow, this is really hard to get started with. Really powerful, but maybe it's hard to collaborate with others on. And then you realize that even for something like Markdown, it's relatively easy to get started, but there's some unsupported syntax that you're trying to do more with it. It's not available. 

So Quarto is trying to get the best of all these worlds, of as easy to use as Word, as powerful as things like Law, Tech and Markdown, but in a cohesive format that you can use across with computation as well. 

And then lastly, there's a goal of this single source publishing. So at the most basic, Quarto can be used to create manuscripts and scientific communication. But you can also take a Quarto document and create again, a presentation, a website, a blog, all sorts of different things. And you can use that to have reproducibility across your publishing pipeline, as well as creating useful outputs beyond just a PDF or just an HTML, but really all these different formats all at once if you desire. 

As far as what Quarto looks like and getting into some of the meat of it, here's a simple example using some Python code and a basic Quarto Markdown Document or a doc QMD. On the right, before we jump into the code, we can see a Matplotlib output. So this is what the rendered document would look like in HTML. It's got a nice title, it's got a hyperlink to the figure there, and it actually hides the code behind an expandable section where you can show the code or hide the code. 

The Quarto document is actually made up of a few different components though. So you have the front matter, which is YAML Markup, and this allows you to define things like the title, the format you want to create, whether it's HTML or PDF or other kind of syntax you want to use, and then the specific language or engine you want to use. So here I'm using Python 3, and I'm using that via Jupyter as a Jupyter kernel to power the document itself. 
Once you've defined that, you can then start writing your markdown, but it's enhanced markdown. So of course you can do bold, you can do hyperlinks, you can do italics and headers and things like that. But you also see here we have at fig-polar, and that's actually what defines the hyperlink to this image that's created with Matplotlib afterwards. 

So beyond the markdown, we also have support for computation via Python R, other languages, and you can write your exact Python code as you'd expect, create a graphic, but then have it referenced robustly by the rest of the document, and you have a figure caption, and you have it referenced in the text. And you can move across your document as you're writing and actually incorporate all the different components. 

But importantly, you have those three structures, the YAML front matter, to define what is the document. I'm creating the markdown to actually write your text or your prose, and then code chunks that actually execute code like Python or R. 

Now, that simple example was only HTML, but again, the goal here is that you could actually create many different formats. So Quarto, as a command line tool, can actually take something from your terminal and you could say, take this example, my hello world QMD, and render it to HTML or PDF or Docx or EPUB or PowerPoint, or a presentation like today with Reveal JS, so that same source could be used to create all these different formats. 
Of course, you can build for a very specific one, like if I'm building a website, I can optimize for a website, or if I'm building a PDF, I can optimize for a PDF. But ultimately, Quarto can convert to any of these different formats by using Pandoc under the hood, which is this document converter system. 

As far as what's supported with Quarto, it's a lot of different things. So this is relevant to what used to be possible with our markdown and what's possible with Quarto today. So all these different formats like reports, HTML, PDF, Word, different types of presentations, whether it's Microsoft Office and PowerPoint or Reveal, JavaScript style or LaTeX style, more complex manuscripts or scientific documents, entire websites, books, blogs, almost all the books we actually publish here at Quarto are actually made with Quarto books moving forward. So you can actually do robust publishing of entire books, both in print and on a website that goes along with them. So a lot of different formats you can create. 

Now, let's loop back, though, in terms of like, okay, so what is Quarto? It's all these different things. It's an open source scientific and technical publishing system. It's built on Pandoc. Ultimately, Quarto, at the most basic is this language agnostic command line tool or command line interface. So from my command line on my MacBook or my terminal here, I can do something like Quarto -- Help and say, what can I do with Quarto after I've installed it? 

It'll say something like, hey, you're on this version one four. And there's a number of different commands. And I've abbreviated the output here. But there's three core ideas. I can render a document, so take a source document and render it to some type of output. I can preview a document which renders and then maintains a background web server to host the content. So I can make changes save and in real time. 

See, those changes affect my presentation or my report, or I could even publish the document. And I can publish it to Quarto Pub, which is a free site that we maintain. Or you can publish to things like Netlify or even GitHub pages directly from the Quarto interface itself. So it's not just the rendering, it's not just the live interface and previewing, but even the ability to publish to external systems. We've even added things like Publishing to Confluence for enterprise usage or Publishing to Posit Connect for some of our enterprise customers, as an example.

As far as the basic workflow you write your document, you might use something like a plain text Quarto markdown document, and you could take something and do Quarto render python.qmd, and it will take whatever is defined in your YAML front manner and convert it to that format. You can also convert it over to a PDF, or you can say, oh, for this one off, I want to send it to a different format. 

And importantly, while I've talked a lot about plain text and .qmds, you can also take your existing unchanged IPython notebooks and render them as well and render them with Quarto. Importantly, there's another option here, because Jupyter notebooks can actually store computation within the JSON structure behind the scenes, you can either take the existing render, basically the existing code for this notebook, and render it with Quarto, or you can re execute it linearly from top to bottom. 

Importantly, Quarto markdown documents are linear and they execute top to bottom cell one, cell two, cell three, all the way down. With a Jupyter notebook, you might actually have executed them out of order, and you want to store that as is and just use Quarto to convert it to a different format, like a presentation or a blog post, for example. 

And then also the difference between render and preview for this example is Preview executes it. It writes the output to disk, but it also maintains this web server. So like, let's say when I was developing this presentation, I had Quarto preview running. So every time I made a change and click Save, I can see my results in real time and then be like, oh, oops, I messed up on this part. I need to make my bullet points a bit different or my code didn't execute as I expected.  So there are these different options for both Quarto and for Jupyter notebooks. 

As far as executing code, Quarto uses knitter as the engine for R, but for Python, Quarto natively executes Python code with Jupyter kernels such as IPython, although you could define what other type of kernels you want to use. So the indicated or whatever the default Python kernel that is found or bound automatically is used whenever Python code chunks are present. And you can even define a specific kernel via the YAML header. 
So for this one, I'm using Jupyter. I'm explicitly saying, hey, use a Jupyter kernel and use this Python three kernel that has these specific packages that are alongside with it and again, because Quarto is a command line tool, you can even use it from within, say, a virtual environment that you've created to isolate your project specific libraries for that document. 

IPython then goes through and executes all the Python code, transmits it to the output plain text, the graphics, the markdown, HTML, whatever output is necessary, and then Quarto bundles it all up into an output document or whatever resource you're creating. And then for these interactive sessions where you're kind of stepping through your code interactively, like, say, in Visual Studio Code or RStudio, Quarto actually keeps the Jupyter kernel resident in the background as a daemon to mitigate the startup time. 

So basically you don't have to start up a whole new kernel. You can keep the kernel fresh as you're making changes to your document. Importantly though, I do want to differentiate some of the design decisions that were made for Jupyter notebooks versus Quarto. Although both are fully compatible with Quarto as a tool, there are some differences in how they approach reproducibility or storing computation. 

So Jupyter natively approaches kind of storing the source code, the output file, and any caching in this single document. So the IPython notebook format is actually a JSON structure behind the scenes, and again, it stores some of the source code alongside the outputs that source code created. Jupyter cache builds on top of Jupyter to provide transient caching of specific cell outputs for a document. And if anything is changed in that, then it's saying, oh, we need to re execute the whole document. So that's available as well on top of Jupyter and its storing of outputs across the whole document.

Quarto uses another technique called freeze. So this allows for a multi file approach. Quarto thinks of it as a source code, being you have a plain text Quarto markdown document or you have a Jupyter notebook, and those are just your source code. We're not necessarily thinking about storing the computation inside of that, but just that it is the source code to generate your output. And you might have complete output files, something like an HTML or PDF that that is your separate output file. 

And then your computation is stored as a computation structure, as pure JSON that allows you to permanently save and reuse these outputs across entire projects. Where someone might be using Jupyter, someone might be using Quarto, someone might even be using our markdown, and all of them can work together to publish a book or a website together. 

So there's a couple different options there for all sorts of different things. Importantly, again, when we go through this, the Quarto markdown structure is a plain text file. So you have your metadata saying, what format do I want to create? What is my engine? Whether it's R knitr or Python in Jupyter or Julia in Jupyter or JavaScript document, my code chunks. In this case, I'm using dplyr with R and I'm using polars in Python to do some group by summaries of the empty cars data set. 

And then I have text or markdown that defines how I structure my document. I can add an image, I can add alt text for that image, along with headings and bold and italics text. So there's a lot of different things here with writing this in a way where it's still human readable even as it is now. But then we'll talk a little bit later about the visual output you can create in real time in editors such as RStudio and Visual Studio code. 

But importantly, Quarto doesn't have to be plain text. And if you're a Jupyter notebook super fan and you like using JupyterLab, you can actually use Quarto directly with that. So you can write in a Jupyter notebook, you can add a little bit of the front matter via YAML in the header as a raw code document, and then you can use from the terminal Quarto render to convert your Jupyter notebook into these beautiful outputs such as PDFs or HTML. 
We've even released a Quarto extension for both JupyterLab and for Visual Studio code that allow you to go even further beyond the basics and actually add on to the command line interface to provide editor specific tooling that I'll show here in a little bit. 

So for the rendering pipeline, you can think of two options here I can have a plain text workflow where I use Quarto and I write all of my stuff in plain text. It still uses Jupyter kernels to execute things like Python. It converts this into an intermediary format and then eventually turns it into things like PDF or Word or websites. 
But if I know and love Jupyter, I can just stay inside a notebook workflow. So I can use Jupyter natively, whether a classic Jupyter notebook or Jupyter lab, and then use Quarto to render it out and use the existing stored computation from within Jupyter. So there's multiple options here, especially when you're collaborating across folks. They might have differing opinions about what kind of structure they want to use. 

So you might ask, okay, well, I actually really like Jupyter notebooks. Can I keep using them? Like, what do I do with my existing notebooks? Keep using them, like you get to choose whether to use that stored computation or again re execute with Quarto the document in a linear fashion. Importantly, you know, for some folks, you might be interactively exploring with a Jupyter notebook and execute code cell three, then code one, then two, then five, then four. You're kind of playing around with it out of order and you need to store that computation to make sure it actually looks right. 

Alternatively, it might be more reproducible to execute it fully linearly, top to bottom, to make sure that if you executed it fresh, it would actually work in a programmatic fashion as opposed to interactive. So you do have this option of forcing execution or again reusing the stored computation from within the notebook from before. 
And importantly, let's say that you might be collaborating or you want to swap. Quarto actually helps you convert from a plain text Quarto document into a Jupyter notebook and back and forth. And you can actually store both copies on disk at the same time by defining what the output you're wanting to create is. But again, I just want to really emphasize you don't have to use the plain text if you don't like it, and you don't have to use Jupyter notebooks if you'd prefer to use plain text. But Jupyter is a core part of the ecosystem, even with Quarto. 

So what this really means is you get to choose and use the comfort of your own workspace, whether that's something like JupyterLab, something like Visual Studio code with the Quarto extension that allows you to use either plain text notebooks or Jupyter notebooks within Visual Studio code. And you can even use it within our studio, whether you're writing R code or Python code. Both of those can be done within our studio as well. 

So we've really tried to invest across ecosystems and across different editors and not just limit it to something like our studio, but provide these multi editor experiences across many different productive tools. We've even invested specifically for Visual Studio code with the Quarto extension to actually enhance the Quarto experience, make it similar to also what's possible with our studio. 

So there's a lot of metadata you can define within, say, like the YAML header, and it might be difficult to remember all of what's possible. So in our studio and Visual Studio code, you actually get rich auto completion of the options that are available. So you don't have to remember everything. You start with format, then you say HTML, then you say, well, what's today's date? And you can define the date within that structure. 

And even within code chunks, you can actually define and have auto completion of the options for code chunks. So you can say, well, I want this code cell to execute this one. I'm just showing off code and I don't want it to execute because it's pseudocode, for example. So I can have evaluation on or off or show the code or not show the code. And all these different options that are possible have auto completion in both our studio and Visual Studio code. And more than that, the quarter extensions for both JupyterLab and for Visual Studio code allow for real time rendering. 

So within JupyterLab, when you actually execute the YAML, it'll show you the proper heading as like a heading one, it says, the author was me. And then it keeps the formatting for the options there and then the code. And for Visual Studio code, we also have the Visual Editor that allows you to have a word processing like experience, where you can switch between plain text markdown and the actual rendered output in the actual editor itself. Even before rendering it out to a final document. 

So you can do things like bold add bullet points, format, insert pictures and tables, all sorts of things to make you more productive. And of course, in our studio, we have a similar experience with being able to switch between source mode and this visual mode where you have all this word processing that's available. 

I do see a couple of questions in the chat about scientific outputs. I'll get to some of those at the end, but you might notice that there's some opportunities here to include things like LaTeX or computational formula inside of the document and seeing those rendered in real time as well through the visual editor in Visual Studio code, as well as JupyterLab in our studio. 

One of the questions I saw in the chat, and I'll repeat it, know what are about the options of switching between formats. Like if I'm saying I'm outputting to Word and HTML, like HTML is really beautiful and really rich, but PDFs or Word is actually much more constrained in what you can create. 

So this example I have a Boston terrier named Howard. I love my dog. So I have a quick example here of one of the Wikipedia articles about Boston terriers that I've converted over to a Quarto document. So of course I can take this article I've written, I can convert it over to HTML and get a beautiful HTML output, but I can also take the exact same document and convert it to PDF. And it also looks like a really good PDF. I can further optimize for either of those formats, but I can actually create these really beautiful outputs from this exact same source code. 

So here's the output of my Boston terrier article that is copied verbatim from Wikipedia in HTML. I've got nice hover text, I've got citations, I've got a scrollable table of contents, graphics in the sidebar and descriptions of those alternative text, all these great things. I really love this article. 
But then someone says, hey, I'm offline. I need to actually print out the PDF or take a look at it. Can you render a PDF for me as well? From the exact same source code, I can create a PDF version that still has the citations and the rich text and the structure of the document using the same source code. So from the exact same document, you can output to different formats and have a really, really nice output. 

So this is something really motivating for me because I like generating HTML. I don't love creating PDFs, but some people need them or have to use them. So Quarto can make it easy to render to different outputs, all from the same thing. There's even a format called Quarto Manuscripts that I'll kind of share some of that at the very end on the Quarto website because it's brand new, but it allows you to keep the source documents as well as a PDF as well as an HTML, and even this kind of Jax format where you can take the entire bundle of reproducibility and submit it to a journal. 

So that whole pipeline is where we're trying to get to of like you don't just have the PDF that's on the scientific publication or in the journal, but you can also maintain a really nice HTML output that goes along with your kind of PDFs or your Word documents that are going out. 

Again when you're writing this syntax, I'll give you a couple of examples of how we share formatting and syntax across both markdown and code. But let's say I wanted to create two images side by side with a quick kind of what is this? So I can take Pandoc dive here, let me zoom in a little bit, and I can say, hey, for these two elephants that are historically known and written about, lay them out with two columns and put them side by side. And I take these images on disk, and I can create this kind of two column layout of the images. 

But that same syntax also applies to dynamically created graphics in Python or R. So here I'm using the plot nine library in Python, which is almost one to one with ggplot from R. And importantly, I create two separate graphics, plot one and plot two. I use the same layout-number of columns equals two, and it actually puts them side by side and it actually injects the figure captions appropriately. So this is a scatter plot, this is a box plot. Even though these were generated on the fly, I'm able to mark them up in a scientific format way or in a reporting way on the fly. So you can share the syntax across all the different structures that you're doing. 

And ultimately what we're trying to do here is provide as much built in markdown centric format agnostic syntax as possible, as we've shown a little bit in the previous slides. Like we don't want you to have to go off and create all this custom stuff. We want to bake all that in, batteries included. So Quarto bundles, bootstrap, as these really rich CSS themes for HTML, I respect SAS variables for even more robust styling dynamically across all the HTML formats. So documents, websites, books, slides. 

It also includes LaTeX templates for specific journals, where again, you don't have to figure out how to write raw LaTeX, you can just take the Quarto markdown, use this specific template from this journal from LaTeX, and it will generate the correct PDF output for you, even if you didn't know what LaTeX was. So you can again create these different multi formats for specific journals, and we've already had lots of people using those templates and adding to the templates over time for their specific journals. 

And again, Quarto also respects Microsoft Office templates. So things like Docx or PowerPoint, where you can use a corporate theme allowing you to style the document robustly without having to inject weird XML inside the document. Although you can kind of generate intermediary markdown or LaTeX or XML outputs that you can then play with more in downstream formats. 

Ultimately you shouldn't have to escape out to writing raw LaTeX, HTML using Ginger templates or anything like that.  You can rely purely on the Quarto markdown syntax, but if you really, really want to optimize for a single format, you can use a template or you can even include your raw content to further style it and optimize for one specific format if that's the way you want to go about it. 

And we've even included the ability to extend quarto with open source extensions from the community and from us as well. So you might have things like short codes where you can inject like social media short links, or you can add moticons or other different things like that. You can apply filters that change the styling of specific items. So you can make your code chunk, say, hey, I'm referencing this file on disk, make it look like I'm actually reading from a file and then printing the code. 

Or you can even define your entirely new format. So for my company, I want to create a presentation format using Reveal JS, and I want to make it where every time I use those slides that it looks appropriate for my organization. So there's a lot of ability to further enhance Quarto and then share those open source extensions with the community. 

I want to close out with two things and then we'll get into questions. But I also want to call out that Quarto with HTML fully supports interactivity. So you can use Python packages or R packages to embed interactive graphics like Plotly and actually have those be fully interactive in both presentations as well as in websites or blogs. 

But even more than that, we actually embed a version of JavaScript called Observable JavaScript that allows you to define net new interactivity on the fly. So here I have something that looks pretty similar to something like a shiny application or even like a streamlit application where you have like a graphic and then there's a little slider bar here. And in real time I can modify the filtering step I want to do and show different things in my graphic and have it update in real time.

This also applies to tables where I can affect the table as well as a graphic in real time through these different components. This is done through, of course, IPython widgets or Jupyter widgets, as well as this ability to do it directly through JavaScript. So these on the fly widgets I want to talk about maybe something simple like this, where I say, oh, it's 34 degrees Celsius. What does that actually mean for me? Because I'm weird and American and I use Fahrenheit. 

So I know Reshama is saying it's about 85 degrees Celsius in New York, which is about 30 degrees Celsius in the rest of the modern world. Or I can say, well in Texas it's about 102, which is 39 degrees Celsius. So in real time I can have my document editable by the end user without having them to write R Python code on top of it. Now, this actually is pretty simple to do. I can use a OJS or Observable JavaScript chunk and then define an input range so zero to 100 step with a unit of one, the default was 34. And then say that it shows degrees Celsius, which is this HTML code. 

And then I can say for the output in the body of my document output, the temperature and the Fahrenheit and have those update in real time depending upon the temp that is changing up here. So just really want to call out that if you see something that you want to do that's custom beyond what's available in Jupyter widget, you can build these widgets on the fly and actually embed them into the body of your document and not just be stuck within a code chunk. So, really, really cool additional feature!

Very last thing I'll talk about and we'll get into some summaries. But while you can create this one source and create many different formats, you can also take one source and create many different outputs. So from the same document I might show results for New York and for Texas, so a report for Reshama and a report for me, or I can run a report for 2022 versus 2023. Or I might just rerun a single analysis with different parameters for different assumptions that I'm doing for my analyses. And I can do these parameterized outputs in both Python and R. 

So for Jupyter, I use a paper mill style tag system where I can define specific tags as these parameters and do things like alpha or ratio that are then available at the top level environment. So they're actually defined for the rest of it, but I can define them via Quarto and change them at the rendering process later on. And then for R you can define them in the YAML header and they're actually stuck within a params list object, so they're not pulled out into the top level environment. 

But again, importantly, in both Python and R, there's these rich support for parameterization of your documents. What this looks like in practice is at the Quarto render step, you might say Quarto render my notebook with these parameters and I can change the alpha value or the ratio value for my graphic or for my machine learning pipeline in real time just by rerendering the exact same document. Or for more complex pipelines, I can actually use an external YAML file that defines many different parameters all at once. 

So you can imagine I have a lot of different things that are changing across a long document and I can actually generate many different versions of the same report from the same source code with different outcomes based upon changing these whole host of parameters. 

So this was a really broad overview of what Quarto can do for you. Hopefully some of that is motivating. And I know there's some questions in the chat we'll get to here in a little bit. The last thing I want to call out is for publishing, you can also publish Quarto documents and Quarto outputs to a number of different places. 
So Quarto Pub is a free resource that we provide. You can sign up for it at Quarto Pub and you can publish like a blog or different HTML outputs there. But we also have support for publishing directly to things like GitHub pages or to posit connect one of our commercial products or to Netlify for more robust presentations. 

Ultimately, I just want to say that Quarto being an open source product, is crafted with a lot of love and care and we really thank the community and all the different contributors and open source projects that help build this out. So thank you to everyone for allowing us to kind of aggregate all these different wonderful things. And if you do have feedback, you can always go to GitHub.com/quarto-devquarto-cli, and you can submit issues or feature requests there and commit or contribute to the open source project. 

As far as some resources, I think in general Quarto.org is the best resource that's actually all of the kind of public documentation and you can go there to learn even more and get started with installing it inside your system and working with it. 

There are some videos that are linked to webinar style.  If you go to Thomasmock.quarto.pub/pythonumbrella for the actual URL, you'll actually be able to see and I'll drop that into the chat. Again, you can see these resources and interact with this to click on the links. 

With all that, I do want to answer a few of the questions, so I'm going to read those out loud and then answer them as best I can. So a question from Mani, thank you for this one. 
Can Quarto documents be shared like overleaf documents and related to that, can users import article templates, specific journals into Quarto? 

So you can use the specific journal templates. So if I go to the Quarto website, I go to guide, go to all formats, trying to think of where scholarly writing, there's a whole section on using scholarly writing or publishing for specific journals specifically like to publish to trying to think of which one. This is for the Journal of Psycho Ceramics, which is that's an interesting one, that's exciting about silly String theory. It shows an example of that. 

And if I go to journal so journal Articles talks about some of the supported formats. So ACM, PLOS ASA, Elsevier a lot of different ones, and if you don't see one that you'd like, you can actually open an issue. And we can work on adding that template working with the Downstream Journal themselves, because often they create a LaTeX template that we then bundle and make work with Quarto so that you can again not have to write all this LaTeX to generate a PDF, but rather just deliver a Quarto document or a bundle. 
I also want to call out that this is relatively new, but I think Manuscript, I think it's here. There's a new manuscript option that again is the bundling of the entire project together where you might have HTML output, some Jupyter notebooks, some Quarto documents and a PDF that generates an entire website and that entire bundle can be shipped off to a journal. 

So some of that might actually be in the release notes for the pre-release because it's a brand new. So Quarto Manuscripts if I go to get started more pre-release, there's a Quarto Manuscripts page that again includes the other formats where you're generating word PDF as well as this mecha bundle that's kind of the aggregation of all the resources. And then you have the source notebooks that actually generated this manuscript and you can link out to external resources like a GitHub repository that has the live source code there as well.  So again, we're really working towards this future of robust scientific publishing via Quarto. 

#### A great question from Wasani, which is: Is it Git friendly?

And I think that's an important aspect of plain text versus Jupyter is at the basic level, plain text operates really, really well with source control like Git. Jupyter notebooks and the JSON can be a bit trickier to work with source code, but there are some extensions that allow you to use source code like Git and GitHub with Jupyter notebooks. But at a basic level, the way I like to think about it is plain text will work for sure, like you can make line by line changes without changing the entire structure.  So it's a really robust option, especially when you're collaborating via source control. 

#### Question from Jordy is: Has Quarto already been used in published scientific work?

There are some gallery examples. So on Quarto.org under Gallery you can see there's a lot of different things for articles and reports. I think some of these include some presentations and other scientific articles, but this would be a good resource for seeing how you might get started. And there's even community resources. I want to say there's a lot of blogs and places here, some books that we have published or working on publishing via Quarto in Python and R. 

So there's a lot of resources here to see how others have approached using Quarto for really, rreally robust outputs and entire books that are used for classes, for physical publication. Even some of the books I have on my shelf written that way. 

#### A question from Corey: Any general suggestions for outputting to docx? 

HTML provides such a rich output, but the word output can be more difficult to achieve. So importantly, I talked a little bit about that when I was showing the PDF versus the HTML output. But with the guide you can actually see documents and then Microsoft Word and Word templates by referencing this external reference doc that defines all of your styles. You can again use that to define all of the XML that's specific for Word. And you don't have to think about XML, but you're really creating like a Word template that Quarto then knows how to respect. 
And similarly for HTML, your source document in Quarto could be the same for HTML and for Word, but they could look vastly different because you're using a different way of theming it or reference template. 

#### Another question from Zhang Yoon:
Thank you for the presentation. Could you provide any tips on how Quarto can help a user who heavily uses the Quarto environment on a supercomputer? Can Quarto have the ability to see the output on the command line? 

I think there actually is a markdown format where you can always print the raw output as like a cat function to print it at the terminal as opposed to writing it out to a text file. But importantly, there are some tools for things like Slurm or other high performance computing environments where you could write things that are in Visual Studio code or workbench like that's one of the things we do with Posit workbench is integrate with Slurm and Kubernetes and you can actually author directly in RStudio or JupyterLab or Visual Studio code, then executes the document remotely in the high performance computing cluster and brings it back. 

#### A question from Liz: About GitHub actions and using those with Quarto. 
So you can use GitHub actions or other continuous integrations with Quarto. So I'm just using the search here on the website to move around quickly. But you can publish to something like GitHub and then use Quarto render within a GitHub action to actually re execute the code, or in some examples, use the stored frozen computation. But build a website. You could imagine my collaborators are building a Jupyter notebook; I'm using a Quarto document. We hand off the code in the middle and we don't want to re execute it because it was executed locally, but we just want to build it into a website like this. 

And that's an example where continuous integration allows for local execution or for actually re executing it all the way inside, continuous integration. So there's a couple of different options depending upon do you want to re execute R in Python or do you want to execute locally and just render remotely? So a couple options there. 

#### Question from Rohail: 
Which is, is it possible to have a website where we have Quarto documents representing the posts, but I was wondering if it's possible to have individual environments attached to each blog post with RN, Anaconda or other virtual environments?

So yes, you can have there's a virtual environment section on Porto that allows you to talk about folder specific libraries. You can imagine that for a blog, what you actually have is a structure of the project root, and then within each blog post you have a specific folder for that blog post. So you can actually define a project specific library via something like RN or virtual end or even cond, I believe, at the project or folder specific level. That then allows you to have reproducible individual blog posts. 

To take a step back, though, you don't have to use that. And you could use Managing Execution via Freeze that allows you to again store the computation locally. And even when you're rebuilding your entire blog, you don't have to re execute code from four years ago, but you can just execute the most recent document. 
This is what I use for my personal blog. So if I were to go to the mockup blog for my one, I've got a lot of blog posts, and if I go to the oldest one from 2018, every time I publish a new blog post, I don't want to re execute this code from five years ago. I can just reuse that frozen computation and then it aggregates that into the overall blog itself. 

So even when I'm adding to this and doing more stuff and more blogging, I'm not having to potentially break my website or have to figure out how to manage old code. I just store the output from those in the past. I think that was all the questions. We've got about ten minutes remaining, so if you do have other Q and A, feel free to throw that into the question and answer. I'll check out the chat real quick. Thank you for suggesting read the Q/A. I moved over to there, but yeah, let me know if you have other questions. 

And again, I think the best resource is number one. My slides are publicly available and they'll be up forever, and then Quarto.org has a whole host of documentation for all the languages that are supported out of the box. So Python, R, Julia, Observable JavaScript, and if you go to the guide or Getting Started, you can say, hey, I want to download the CLI and install it for my specific operating system. 

And then you say, well, what is the editor I want to use? Maybe I want to use a text editor in the command line. I can use that. Maybe I'm a Jupyter user or studio, Visual Studio code. If I click into that, it actually walks through creating a basic document, Getting Started, How Computations Work, installing Packages and Libraries, and the whole process of working with that. So a nice, friendly, getting started page. 

Then the guide goes into as much detail as you could ever imagine on all the different options, or as you saw me using the search bar up here, if I'm thinking of something like GitHub Actions, I can see oh, there's a lot of different opportunities for GitHub Actions for publishing and I can go read about that specific topic without having to navigate the file directory. 

I think that's the bulk of it. But again, I'm around for a few more minutes and I'm going to just hang out and kind of talk for a little bit more. So if you have other questions, please ask them in Q/A. And thank you so much for the time today. The gallery as well is a real good resource for looking at examples of what others have done and especially around like I want to create HTML or PDF or these different presentations, you can get some kind of exposure to how others have approached it. 

This was a really fun one I did with the Apache Arrow project around using it for really big data sets, for example, and I'll show up some pictures of Boston Terriers because that's always a good call and I love Boston Terriers. So you can find examples of different presentations from the Quarto.org website itself.
And even for some of the personal blogs or professional blogs like the nbdev project from Fast.AI, they've standardized around Jupyter notebooks for a long time, but they've recently started using Quarto to build websites and some of the documentation hosted via Quarto. So even the broader open source community is building on and around some of the use of open source products like Quarto in conjunction with Jupyter and GitHub and other applications. 

So, for example, their blog here is a Quarto blog. You can see all the different options around it. They have a nice article about using nbdev with Jupyter with Quarto, which again is impactful for using Jupyter with version control. They've actually done a lot of work on making that better and able to safely check Jupyter notebooks into version control. Or you could use the Quarto Plain text markdown documents as well. 

All right, I don't see any other questions. I'm going to pause for a little second, get a drink of water, but if others have questions, feel free to ask them in the chat. I'll go back to Quarto.org, the last thing I'll call out is with the Quarto blog. So again, Quarto.org blog, we talk about a little bit more about new things as they come out. And so you can see embedding or multi format publishing some of the exciting things as they come out summarized as opposed to reference documentation. 

And importantly, especially if you're developing shiny applications with Python, there's even support for Shinylive, which is a WASM or WebAssembly implementation of Shiny in Python that can be embedded into Quarto documents, where you can actually have interactive applications hosted directly inside your documents. So this will load for a second and I can have again these real time ability to modify components and develop Shiny applications that are then hosted within a Quarto document or a Quarto website. 

So some really, really cool things that they're working on. I really like keeping up with them through the Quarto blog as well as just checking in on the Getting Started release notes. You can always see the pre-release and they have some information they're doing around support for other formats. 

Or again, I think the Quarto manuscripts is something that's really, really cool. It's in pre-release for one four, but this really robust bundle of assets for robust publishing and that it's supported across the major editors so JupyterLab Visual Studio Code and RStudio and across document types, so Jupyter Notebooks as well as Quarto documents really kind of building upon this scientific publishing and communication aspect. 
I think Reshama is having a little bit of Internet trouble, so I just messaged her, but I think, oh, here we go. 
How can I use Quarto to write scientific papers? 

So there's a nice section on the guide if you go to authoring here and then scholarly writing, it talks a little bit about using things like bibliographies or references and how you can embed those in the text and have things like hover text for specific articles in the HTML or even in the PDF output having the nice hyperlink to those. 
It talks a little bit about cross references where you might define a figure in maybe the first few pages, and then you can reference that figure much later in the document and have it actually link back to the original figure, as well as things like writing LaTeX for formula or theorems and proofs and having those robust to mathematical syntax inside the document itself. 

For some of the books and other more complex things some of that also plays in, but especially for those types of like actually doing scientific writing. The scholarly writing section is really great. It's a good start. I will go back and there's even some information around citations, and you can have reference to your affiliation where you're coming from, URL to your site and have the citation example where you have, like, a bibliography example for the article you just wrote, as well as other more complicated kind of structures where you're using Google Scholar or different citation options. 

#### Wrap Up
All right, well, so much. Thank you so much for the time today. It looks like Reshama asked me to just close this out and she's going to use that to close out today. But we're all wrapped up. Feel free to reach out to me. I'm on Twitter, I guess a little bit, although mostly on Fosstodon or on Threads at this point as we kind of figure out where the data community is moving to and kind of standardizing around. But feel free to reach out anytime and make sure to check out the Quarto.org documentation. 

Thanks so much to Data Umbrella for having me today and for y'all for attending. I'll see you next time. Thank you so much. I'm going to close this out and concludes exit the webinar. And thank you and have a great week!
