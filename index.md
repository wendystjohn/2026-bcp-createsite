---
title: Home
layout: home
nav_order: 1
---

# Statistics for Biology: Assessing Data

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
