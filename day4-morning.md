---
title: Day 4 morning - Odds and Ends.
layout: home
nav_order: 6
---

## Live coding some stats functions

Visit
[ctb.github.io/2026-bcp-101-stats](https://ctb.github.io/2026-bcp-101-stats/)
and let's work through defining and running some Python functions.

(You can just watch, or you can follow along ;))

## Finding lessons online

I found [this paper](https://arxiv.org/html/2405.16675v1), "Using
Jupyter Notebooks to foster computational skills and professional
practice in an introductory physics lab course", which led me to
[this code repository](https://github.com/etufino/Jupyter-Notebooks-in-Lab-Course-Uni-Potsdam), which contains some interesting notebooks:

- [simulation of projectile motion](https://github.com/etufino/Jupyter-Notebooks-in-Lab-Course-Uni-Potsdam/blob/main/Application_Examples/Projectile_Motion/MyFirstSimulation_projectile_motion_EN.ipynb)
- [random numbers and histograms](https://github.com/etufino/Jupyter-Notebooks-in-Lab-Course-Uni-Potsdam/blob/main/Application_Examples/Random%20Numbers%20and%20Histograms/Random_Numbers_and_Histograms_EN.ipynb)
- [plotting Co2 data](https://github.com/etufino/Jupyter-Notebooks-in-Lab-Course-Uni-Potsdam/blob/main/Application_Examples/ExamplePlotting_CO2_Data_EN.ipynb)
- [Measuring the illuminance of a light bulb as a function of distance source-detector](https://github.com/etufino/Jupyter-Notebooks-in-Lab-Course-Uni-Potsdam/blob/main/Application_Examples/Example_of_fit_Illuminance_of_a_light_bulb_with_Pandas_EN.ipynb)
- [Introducing the moving average](https://github.com/etufino/Jupyter-Notebooks-in-Lab-Course-Uni-Potsdam/blob/main/Application_Examples/Sunspots_and_moving_average/Example_of_moving_average_applied_to_sunspots_number_EN.ipynb)

I've copied many of these over to the `physics/` directory in 
[ctb.github.io/2026-bcp-101-stats](https://ctb.github.io/2026-bcp-101-stats/); let's try running them!

## Other Teaching strategies

A good workshop - [Carpentries Instructor Training](https://carpentries.github.io/instructor-training/01-welcome.html).

- Pre-filled notebook (maybe with faded examples)
  - note: can make read-only, forcing a copy
- HackMD + copy/paste
  - live update;
  - an independent and easily accessible record of lesson;

## Alternatives to JupyterLite: discuss & demo

- Google Colab
  - more power than locally run jupyterlite;
  - can install a wide range of software;
  - unreliable over long term;
- mybinder
  - unreliable over long term;
  - supports RStudio;
- local install of JupyterLab; JupyterHub
  - difficult for some to install;
  - does not work on Chromebooks;
  - considerably more powreful than jupyerlite;
  - can install a wide range of software;

# How can we support you?

Some of the things we hope to work with you on:

- designing and setting up your own lessons;
- trying things out with us as a "foil";
- digesting custom data sets and helping figure out how to deploy them in a JupyterLite environment;
- helping you figure out what packages to use and how to install them;
- helping with technical problems and debugging;
