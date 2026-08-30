---
title: Home
layout: home
nav_order: 1
---

# Exploring Biodiversity with Python

## A Scientific Investigation

> ## 🌿 The Challenge
>
> **Which College of Marin campus is more biodiverse?**
>
> One campus is surrounded by extensive open space.
>
> One campus lies near the edge of a tidal estuary.
>
> You have access to thousands of wildlife observations collected by citizen scientists.
>
> **Can you use the data to answer the question?**

---

## Welcome!

Ecologists often ask questions that appear deceptively simple.

- Which habitat supports the greatest biodiversity?
- How does biodiversity change through time?
- Are two communities ecologically similar?

Finding reliable answers, however, requires more than simply collecting data. Scientists must also consider **how** those data were collected, what information may be missing, and whether the observed patterns truly reflect nature.

In this investigation, you will use **Python** to analyze thousands of wildlife observations collected through **iNaturalist**, a global citizen science project. As you explore the data, you'll learn to organize information, create visualizations, and evaluate ecological patterns using the same computational tools employed by professional scientists.

Along the way, you may discover that answering one question often leads to several new ones.

---

# Learning Objectives

By the end of this investigation, you should be able to:

- Import and explore a real ecological dataset using **Pandas**
- Calculate species richness for different locations and years
- Create informative graphs using **Matplotlib**
- Compare biological communities between two sites
- Evaluate how sampling effort influences ecological conclusions
- Recognize strengths and limitations of citizen science datasets
- Use evidence to support ecological interpretations

---

# Your Scientific Toolkit

## JupyterLite

This activity runs entirely in your web browser using **JupyterLite**, so no software installation is required.

JupyterLite combines code, text, figures, and notes into a single interactive notebook, allowing you to document your investigation as you work.

---

## Python

Python is one of the world's most widely used programming languages and has become a standard tool for scientific computing, data analysis, visualization, and research.

No previous programming experience is required for this activity.

---

## Pandas

Pandas is a Python library designed for organizing and analyzing tabular data.

During this investigation you will use Pandas to:

- import datasets
- summarize observations
- calculate biodiversity metrics
- compare biological communities

---

## Matplotlib

Matplotlib is Python's primary graphing library.

You will use it to create figures that help reveal ecological patterns and communicate your findings.

---

# Getting Started

1. Open the Jupyter notebook.
2. Run each code cell in order using **Shift + Enter**.
3. Read the background information before attempting each section.
4. Record your observations and interpretations on the accompanying worksheet.
5. Remember that your goal is **not simply to write code**—your goal is to use evidence to answer ecological questions.

---

# Activity Materials

## 📓 Biodiversity Investigation Notebook

*(Notebook link goes here.)*

---

## 📝 Student Worksheet

*(Worksheet link goes here.)*

---

# Tips for Using JupyterLite

- Run a code cell using **Shift + Enter**.
- Execute notebook cells in order.
- If a graph does not appear, rerun the code cell.
- Save your completed notebook by downloading a copy to your computer.
- Refreshing your browser may reset the notebook if your work has not been saved.

---

# A Note About Scientific Inquiry

Unlike many classroom exercises, this investigation does **not** have a single "correct" answer waiting to be discovered.

Instead, your task is to analyze evidence, identify patterns, evaluate limitations, and decide what conclusions are—and are not—supported by the data.

That process is at the heart of scientific inquiry.

---

> *"Somewhere, something incredible is waiting to be known."*
>
> — Carl Sagan

# Biodiversity, Bias, and Big Data: Exploring Community Ecology with iNaturalist

These activities will introduce some typical ways that biological datasets - both experimental and observational - can be assessed, using open source statistical tools. 

## Overview

Students will learn how to use Python in a Jupyter Lite environment to perform simple statistical analyses, including means and medians, distributions, analyses of variance, and multiple comparison tests. We will assess data downloaded from the iNaturalist website, as well as the data we generate during our semester-long greenhouse experiments. 

## Technology

During these activities, you'll be introduced to a
particular set of data science technologies. It can be difficult to see how they relate to each other, so please refer to this overview for key terms and relationships. 

The technology we're using was
chosen because is not only free, but works on essentially any
computer with a modern Web browser and a keyboard - including Google
Chrome books - and needs no installation, no special permissions, and
no additional software.

**JupyterLite:** [JupyterLab](https://jupyter.org/) is an open-source web application designed for interactive computing, allowing users to combine live code, equations, visualizations, and text in a single, shareable document. The core piece of tech we'll be using is called
[JupyterLite](https://github.com/jupyterlite/jupyterlite), a version of Jupyter that runs in a web browser. It lets you use notebooks without installing software on your computer.

**Python** Jupyter is built around
[Python](https://www.python.org), a programming language commonly used for data science. We will use Python to write instructions that the computer can follow. 

**Library:** An add-on tool that gives Python extra abilities. 

**Jupyter notebook:** An interactive document where you can write code, add notes, and see results like tables or plots.

**Pandas:** A Python library used to work with data tables. [Pandas](https://pandas.pydata.org/) helps you load, view, filter, organize, and summarize data.

**matplotlib:** [matplotlib](https://matplotlib.org/) is a Python library used to make plots and graphs from data.

**GitHub:** [GitHub](https://github.com/) is a website used to create, edit, store, share, and customize collections of files, especially code and project materials. 

**Markdown:** A simple way to format text using plain characters. For example, Markdown can be used to make headings, lists, links, and bold text. [Markdown](https://www.markdownguide.org/]).

These are all tools and approaches that we and millions of other people use
on a daily basis! You will learn how to begin using them, and there is
no real stopping point to what you can do with them - they are fully powered and "deep". However,
that also means that they are not necessarily easy to use and configure!

Important things to mention:
* The only account or signup needed is GitHub, which is free to create.

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



This is a custom site that we built for you.

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


If you go to Run... Run all cells... you will get the right answer, tho!

You can also click the fast forward, which will reload and re-run everything.
We can talk more about this on Wed!




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




Copyright 2026 Wendy St. John 
