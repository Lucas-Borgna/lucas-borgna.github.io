---
permalink: /projects/
title: "Projects"
---

This page describes some side projects I've worked on during my research. 

## Continuous Integration pipeline for firmware projects.

I'm very passionate about adhering to good coding practices and using the latests and greatest tools in software development.
Anyone who comes from a software development background will be **shocked** at the lack of good coding practices in firmware projects. From experience, there are still projects where the final output file used to run in the FPGAs has a file name like `R3V10_FinalFinal.zip`. This reduces the maintaintability and operability of firmware projects quite significantly and ultimately increases the development hours, which are very expensive. During one of my firmware projects in ATLAS, I decided to take all the good coding practices learned in software development and translate into the firmware world. 

The first step to do this was to make sure my project was on git, which is not very trivial as you need to be careful about the files that are included in the repo (i.e no binaries). The second and more ambitious step was to produce a Continuous Integration pipeline that would mainly simulate and test every commit into the firmware project. Again, this is something that is trivial in the software world, but in the firmware world this required more of a custom setup. There is two issues here, the first being that the pipeline would need to have the Xilinx tools available. The second issue is that the harware requirements to actually synthesize the firmware can be gargantuan (some target FPGAs might require 64GB of RAM for a single build). To solve both these issues I used a CERN openstack VM as this would allow me to customize my pipeline "runner" so that I could include the correct Xilinx tools and licenses. The VM also has a large amount of resources available and can be varied depending on the demands of the project. The image below shows a result of the pipeline execution on a commit.

![](/assets/images/FirmwareCI.png)

The first two steps build the environment and creates the project so that the firmware can be compiled. The next step is to run a simulation on the project. Simulations are essentially used as the unit-tests of the firmware world (in fact I would kind of say that they are the same thing). In this example, the simulations are run and automatically compared to a reference result so that any divergences are instantly caught. If these stages pass then the pipeline will proceed to synthesize the firmware and write the bitstream for the target FPGA. This bitstream then gets deployed to a storage server so that the user can then put in the target chip. There were many technical intricacies in realizing this pipeline, but many colleagues in the larger firmware project were able to borrow elements from this and implement them into their own projects. 


## Semi-supervised Topic Modelling

As part of my first year PhD training we undertook a group-project from an industry partner faculty AI (then called ASI). The scope of the project was to develop a topic modelling app that can be guided by the user giving some keywords into the topic, hence the **semi**-supervised approach. To do this we utilized the `SeededLDA` algorithm, which is a modified version of the `LDA` algorithm for topic discovery based around the user-specified keywords. Below is an example of how this can affect the results. The [20 newsgroups dataset](https://scikit-learn.org/0.19/datasets/twenty_newsgroups.html) was used as an input for this algorithm. The table below shows what the regular `LDA` gives for the two topic (space and medicine). 


| **Topic Number**       | **Unsupervised Topic Results**                                                                      |
| ---------------------- | --------------------------------------------------------------------------------------------------- |
| **Topic 1 (space)**    | space, health, nasa, 10, research, use, 1993, new, university, information, center, cancer, medical |
| **Topic 2 (medicine)** | cs, people, like, don, just, pitt, know, science, msg, gordon, thinks, banks, geb                   |

We can use the following keywords for each topic for the SeededLDA algorithm

| **Topic Number** | **Seed words**                   |
| ---------------- | -------------------------------- |
| **Topic 1:**     | launch, earth, orbit, shuttle    |
| **Topic 2:**     | disease, health, medical, doctor |


The table below shows the reults of the SeededLDA algorithm, which clearly shows a better separation and modelling of the two topics.

| **Topic Number** | **Seeded Topic Results**                                                                           |
| ---------------- | -------------------------------------------------------------------------------------------------- |
| **Topic 1**      | earth, orbit, launch, shuttle, cs, pitt, science, space, don, gordon, banks, geb, nasa             |
| **Topic 2**      | medical, health, disease, doctor, msg, food, university, people, use, patients, know, like, cancer |


The algorithm, which was originally written in C++, was wrapped around a python interface that allowed us to use plotly-dash for the web interface. The image below is an example of what the interface looked like.

![](/assets/images/TopicModelling.png)

The graph on the left is a scatter plot comparing how every document is distributed between two of the selected projects. As this is an interactive web app, the user is able to select any specific document. Then the pie chart on the right shows how the topics are distributed within the selected document.


