---
permalink: /research/
title: "Research"
--- 

This page provides a **brief** summary of my PhD and Masters research project. Ping me if you want to learn more about it! 

## PhD Thesis

The [ATLAS](https://atlas.cern/) experiment is one of two general purpose detectors around the LHC ring. The detector has a cylindrical shape around the collision point and is made up of several layers that are designed to detect different kinds of sub-atomic particles. The ATLAS detector in tandem with the other general purpose detector (CMS), were in fact used to [discover the Higgs boson in 2012](https://home.cern/news/press-release/cern/cern-experiments-observe-particle-consistent-long-sought-higgs-boson), a particle that has been theorised to exist since the 1960s.  

![](/assets/images/nonresonanttriangle.png)

For my thesis I decided to focus on the search for events where a pair of Higgs Bosons (dihiggs) decay into four bottom quarks $HH \rightarrow b\bar{b}b\bar{b}$. This is where the feynman diagram above can help understand the system. The search has strong theoretical motivations as it can directly connect with the Standard Model of particle physics. This is because the search can be used to constrain the shape of the Higgs' potential. It is for this reason that the dihiggs search can be used to test for new physics beyond the Standard Model. Unfortunatelly, the theoretical predictions indicate that a dihiggs event is quite rare and is overshadowed by a background that is 6 orders of magnitude more frequent. Making this search a "needle-in-a-haystack" type of problem. 

To carry out this search the full Run-2 dataset was used, which took 4 years to collect. The dataset is then heavily processed by using triggers to select out events with the fingerprints that we are interested in. The events that remain are then reconstructed to see if they fit the structure of the dihiggs decaying into four bottom quarks. Part of the reconstruction process uses a BDT to correctly pair which bottom quarks came from which higgs particle. The background is modelled by using a neural network that learns from data outside of the signal region of interest. Ultimately, the search is carried out by using a statistical test to see if the observed number of events is consistent with the expected number of events. The figure below shows the results of the statistical analysis as a function of $\kappa_{\lambda}$, which is a parameter of the standard model. The search enables us to exclude values of $\kappa_{\lambda}$ that are outside of -6 and +15. 

A full copy of my thesis can be found in [CERN's document server](https://cds.cern.ch/record/2812193?ln=en). 


<img src="/assets/images/kappa_lambda_unblinded.png" alt="drawing" width="600">

## Masters Thesis 

I jumped into the deep learning training during my masters' at UCL, where I got the chance to work on a project using data from the ATLAS detector. The aim of this project was to develop a classifier that could distinguish between W bosons (signal) and QCD (backgrounds). An intuitive way to reconstruct these events is to use the energy deposited in the calorimeters and then turn this into an image. An example of what the QCD image (left) and the W image (right) after pre-processing look like is shown below.

<img src="/assets/images/jetimages.png" alt="drawing">

As images were used a set of different Convolutional Neural Networks (CNN) were tested. The classification performance of the CNNs was compared to a more traditional cut-based method. Below are the Receiver Operating Characteristic (ROC) curves for architectures. In general the CNNs outperform the cut-based method, with the best performing network being the VGG19 architecture with Batch Normalization and Parametric RELU activation functions.

![](/assets/images/ROC.png)

The above examples were obtained by using a **fully-supervised** approach. This means that for each image we know the true label (signal or background). There are however some cases in particle physics were we don't have the true label, but what we do have is a relative fraction of signal to background events in a sample. This type of problem is coined a **weakly-supervised** approach, which I implemented using the image based approach. The ROC curve below shows the performance of the CNNs when trained with a weakly-suppervised classifier with varying purities of signal to background in the samples. 

![](/assets/images/Weak1.png)



