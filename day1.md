---
title: Day 1 - welcome and introduction!
layout: home
nav_order: 2
---

# Welcome and introduction!

## Introductions

Everyone introduce themselves and say why they're interested in
participating in this workshop!

## Scope & Goals

- See how certain kinds of modern open-source technology can support teaching data science in high school and college
- Understand, investigate, and exercise the opportunities of the technology we’ll be introducing
- Explore ways to connect technology to the needs of teachers
- Learn from teachers what they need
- Offer technological support to teachers
- Connect teachers by interest

## Structure & Schedule

Dates: Monday, June 15, to Thursday, June 18

Morning Session: 10:00 AM - 12:00 PM (PST)

Lunch: 12:00 PM - 1:00 PM (PST)

Afternoon Session: 1:00 PM - 3:00 PM (PST)

**Monday: Introductory material and the basic technology platform we are showing you.**
We will begin with an overview of the goals for the week, introduce the dataset and examples we will be working with, and make sure everyone is comfortable accessing the course materials. We will also introduce the basic technology platform, including how to open notebooks, run code, save work, and troubleshoot common setup issues.

**Tuesday: Basics of programming, plotting, and statistics in Python.**
We will focus on core Python skills for working with data, including variables, lists, tables, and simple calculations. We will then use these skills to make plots, summarize data, and interpret basic statistics. The goal is to build enough comfort with Python to explore a dataset and ask simple quantitative questions.

**Wednesday: Connecting specific skills to a general data analysis workflow.**
We will broaden from individual coding skills to the larger process of setting up and carrying out a data analysis project. This includes organizing files, choosing useful columns, cleaning or filtering data, deciding what questions can be asked, and connecting code, plots, and interpretation into a repeatable workflow.

**Thursday: Engaging with individual and group plans.**
We will spend time developing individual or group project ideas using the tools and concepts introduced earlier in the week. Participants will identify a question, choose relevant data, outline an analysis plan, and discuss possible outputs. This session will include time for feedback, troubleshooting, and planning next steps.

## Expectations

1. Be present and engaged
    *  There won't be much in the way of assignments or exercises for you guys to go through on your own time, but we would appreciate if everyone could join on time and ready to follow along!
2. Foster a respectful environment
    * We're all coming into this with different experiences and expectations, clear and respectful communication goes a long way! 
3. Contribute and engage in a manner and extent which fits your desired outcomes
    * All of us are probably wanting different takeaways from this workshop, and as such, are anticipating to engage with the material in different ways. This is all perfectly fine, all that we ask is that you be involved however you feel will best suit your goals!
    * As we cover material, your desired outcomes may very well shift. Letting us know will help us get you to those new goals!
4. A little patience goes a long way :)
    * Working with technology can be tedious and frustrating at times, but our goal is to walk everyone through this workshop as smoothly as possible. When problems arise, know that we will both do our best to walk you through any roadblocks, as well as try to give you the knowledge to troubleshoot independently.
    
We've intentionally left lots of time for questions and collaborative
exploration, so please ask questions as you have them!

TL;DR: Show up; participate; engage!

## Technology
<img width="4000" height="2250" alt="Overview" src="https://github.com/user-attachments/assets/8cfc0956-a26a-44d7-a4b9-26596c34a670" />

Over the next three days, we're going to be introducing you to a
particular set of data science technology. It can be difficult to see how they relate to each other, so please refer to this overview for key terms and relationships. However, here's a brief summary:

**JupyterLite:** A version of Jupyter that runs in a web browser. It lets you use notebooks without installing software on your computer.

**Jupyter notebook:** An interactive document where you can write code, add notes, and see results like tables or plots.

**GitHub:** A website for storing, organizing, editing, and sharing files, especially code and project materials.

**Markdown:** A simple way to format text using plain characters. For example, Markdown can be used to make headings, lists, links, and bold text.

**Python:** A programming language that is commonly used for data science. We will use Python to write instructions that the computer can follow.

**Library:** An add-on tool that gives Python extra abilities. 

**Pandas:** A Python library used to work with data tables. It helps you load, view, filter, organize, and summarize data.

**matplotlib:** A Python library used to make plots and graphs from data.

The technology we're using was
chosen based on our own experiences as well as our workshop last year;
in particular, it is not only free, but works on essentially any
computer with a modern Web browser and a keyboard - including Google
Chrome books - and needs no installation, no special permissions, and
no additional software.

The core piece of tech we'll be using is called
[JupyterLite](https://github.com/jupyterlite/jupyterlite), which is a
Web browser-based implementation of the
[JupyterLab](https://jupyter.org/) system. It is built around
[Python](https://www.python.org), which is the programming language
we'll be using. (We'll go over Python more thoroughly tomorrow.)

We'll also be using the [Pandas](https://pandas.pydata.org/) and
[matplotlib](https://matplotlib.org/) libraries in Python, to
work with data and plot data. This will be the bulk of what we do
tomorrow.  (We will also introduce various other Python packages
throughout!)

Last but not least, the other star players in our technology line up
will be [GitHub](https://github.com/) and
[Markdown](https://www.markdownguide.org/]). GitHub is a Website that
we will use to create, edit, and customize collections of files, and
Markdown is a widely used way of formatting text for display that is
supported by GitHub and JupyterLab as well as many others.

These are all tools and approaches that we and millions of other people use
on a daily basis! We can show you how to begin using them, and there is
no real stopping point for them - they are fully powered and "deep". However,
that also means that they are not necessarily easy to use and configure!

Important things to mention:
* The only account or signup needed is GitHub, which is free to create.
* The main drawbacks of JupyterLite are: limited by local compute; can't install many things; R is limited.

## Demo

Let's see an overview of what we'll cover during the next two days to show you how all of these buzzwords
work together.

After lunch, we will lead you through all of this so you can get a
top-down view of how it all fits together, and then tomorrow we will
give a more thorough introduction. On Wednesday we'll talk about how it
works underneath and where some of the challenges lie, and then show you
the approaches needed to build your own customized site.

<!-- source code: https://github.com/ngs-docs/2026-summer-bcp-101-jupyterlite-demo -->

Click on this link: [ngs-docs.github.io/2026-summer-bcp-101-jupyterlite-demo/](https://ngs-docs.github.io/2026-summer-bcp-101-jupyterlite-demo/)

Then open `quick-demo.ipynb` on the left by double-clicking on it. You can
maximize the tab by clicking on the folder icon (upper left).

Now run the notebook by clicking on the "fast forward" icon on the menu
bar, and click the red "Restart" button.

<img width="1872" height="982" alt="Screenshot 2026-06-15 at 9 27 17 AM" src="https://github.com/user-attachments/assets/a060a3d0-d7d9-42c8-a218-ebe2cb298c5e" />

# LUNCH BREAK! Restart at 1pm.

# Hands-On Introduction to Technology

## JupyterLite

JupyterLite is a Web-based, entirely in-browser interface to running Python
code, visualizing outputs, and exploring files.

Points:
* Web-based: all interactions via a Web browser.
* entirely in-browser: after retrieving initial set of files, 100% local compute; no Web server needed.
* visualizing outputs: you can see graphs and graphics in the same interface as the code you're running.

To get started, go to this Web page:

<!-- source code: https://github.com/ngs-docs/2026-summer-bcp-101-jupyterlite-demo2 -->

[ngs-docs.github.io/2026-summer-bcp-101-jupyterlite-demo2/](https://ngs-docs.github.io/2026-summer-bcp-101-jupyterlite-demo2/)

This is a custom site that we built for you. On Wed, we'll show you how
to build one for yourself.

<img width="1778" height="822" alt="Screenshot 2026-06-15 at 9 32 18 AM" src="https://github.com/user-attachments/assets/213cb5de-70d9-4bf5-9a8e-b609d3b7d705" />

### Exploring JupyterLite

You can browse files.

You can launch new notebooks.

You can launch multiple new notebooks! They will work independently of each
other.

You can't collaboratively work on the same notebook on different computers,
I'm afraid. (There are many reasons for this.)

### Python Notebooks

Start a Python notebook.

Click the little disk icon to save (or File... Save.) Give it a name.

**You can run Python code:** enter the following in a cell of your
notebook and click the "play" button to run it.

```
print('hello, world')
```

In these code cells,

* you can do basic math!
* you can load spreadsheets
* you can create plots and figures

More on this tomorrow.

The last value calculated will be displayed; try executing:
```
5+5
2+2
```
and see what is printed.

You can do:
```
print(5+5)
print(2+2)
```
if you want to see intermediate values printed.

### Manipulating Notebook Contents

You can curate your notebook cells.

* Edit, move, delete
* Copy, paste cells

### Keyboard shortcuts

Shift-ENTER is about the only one of these I usually use, but there are a lot
of useful ones.

### Running cells out of order

You can run cells out of order - for example,
```
a = 1
```
then
```
print(a * 2)
```
will give you 2.

If you add a new cell with
```
a = 3
```
(which overwrites the value of `a`) and then go run just the
`print` cell, you will see the number 6, even though if you just read
through the notebook from top to bottom that would be confusing.

If you go to Run... Run all cells... you will get the right answer, tho!

You can also click the fast forward, which will reload and re-run everything.
We can talk more about this on Wed!

Generally, we strongly suggest writing the notebooks to be run in
order, and rerunning it from scratch regularly.

### Pre-Staging Notebooks

Click on the `markdown-examples.ipynb` file. This is a pre-existing
notebook that we wrote for you. It's an example of a "pre-staged"
notebook that can be prepared ahead of time and placed in the
JupyterLite site.

### Writing Text and Explanations in Markdown

You can create text cells in notebooks that support Markdown formatting.

* Basic formatting.
* Math formatting.
* Images.

Open the `markdown-examples.ipynb` and run it. Let's go through these
examples!

### Storing, Downloading, and Uploading Notebooks and Figures

These sites are persistent, and stored locally after download -
including with any and all of your changes! So you can close the site,
and open it again later, and all the contents will still be there.
(Unless you use incognito mode in your browser, which doesn't save
anything.)

You can download notebooks and files, and also upload them. They will
stay there until you use "Clear cache" (under the Help menu).

### Installing new packages

Try putting:
```
%pip install matplotlib_venn
```
in one cell, and running it. This will find, download, and install the
[matplotlib_venn](https://pypi.org/project/matplotlib-venn/) package.

Then, in another cell, run:
```python
from matplotlib_venn import venn2
venn2(subsets = (3, 2, 1))
```

to use the new package.

### JupyterLite Gotchas.

Caching. Note that each new _site_ starts fresh! (Based on the Web site address.) And then after that changes to it are saved to each browser that you run.

You can clearing your own changes to a site with the "clear cache" button under
Help menu.

If we update the site itself, then that is harder to deal with; you'll need to
delete all the site data.  (Demo in Firefox!)

We suggest use incognito mode to test a new site out!

You can also "just" create a new site. We'll show you that on Wed :).

<!-- 
CTB Maybe save for Wed:

* github, Browser local, clearing cache (chrome, firefox, safari, ??), incognito, updating files how and when

### CTB maybe to cover:

* Teaching strategies (look at instructor training notes!)
    * questions and answers
    * pre-staged data
    * faded examples

-->
