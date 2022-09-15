---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: single
author_profile: true
title: "About me"
---

I am Research Associate at Imperial College working in the High Energy Physics Department, where I focus on accelerating reconstruction algorithms for the [CMS](https://cms.cern/) experiments. I recently completed my PhD in Particle Physics and Data Intensive Sciences in the [ATLAS](https://atlas.cern/) experiment at CERN, with the University College London. The work in my PhD allowed me to hone my skills in statistical analysis, machine learning and software development. 


## PhD Thesis

The [ATLAS](https://atlas.cern/) experiment is one of two general purpose detectors around the LHC ring. The detector has a cylindrical shape around the collision point and is made up of several layers that are designed to detect different kinds of sub-atomic particles. The ATLAS detector in tandem with the other general purpose detector (CMS), were in fact used to [discover the Higgs boson in 2012](https://home.cern/news/press-release/cern/cern-experiments-observe-particle-consistent-long-sought-higgs-boson), a particle that has been theorised to exist since the 1960s.  

![](/assets/images/nonresonanttriangle.png)

For my thesis I decided to focus on the search for events where a pair of Higgs Bosons (dihiggs) decay into four bottom quarks $HH \rightarrow b\bar{b}b\bar{b}$. This is where the feynman diagram above can help understand the system. The search has strong theoretical motivations as it can directly connect with the Standard Model of particle physics. This is because the search can be used to constrain the shape of the Higgs' potential. It is for this reason that the dihiggs search can be used to test for new physics beyond the Standard Model. Unfortunatelly, the theoretical predictions indicate that a dihiggs event is quite rare and is overshadowed by a background that is 6 orders of magnitude more frequent. Making this search a "needle-in-a-haystack" type of problem. 

To carry out this search the full Run-2 dataset was used, which took 4 years to collect. The dataset is then heavily processed by using triggers to select out events with the fingerprints that we are interested in. The events that remain are then reconstructed to see if they fit the structure of the dihiggs decaying into four bottom quarks. Part of the reconstruction process uses a BDT to correctly pair which bottom quarks came from which higgs particle. The background is modelled by using a neural network that learns from data outside of the signal region of interest. Ultimately, the search is carried out by using a statistical test to see if the observed number of events is consistent with the expected number of events. The figure below shows the results of the statistical analysis as a function of $\kappa_{\lambda}$, which is a parameter of the standard model. The search enables us to exclude values of $\kappa_{\lambda}$ that are outside of -6 and +15. 

A full copy of my thesis can be found in [CERN's document server](https://cds.cern.ch/record/2812193?ln=en). 

<!-- ![](/assets/images/limits-graviton-5-TeV.png){width=45%}
![](/assets/images/limits-scalar-5-TeV.png){width=45%} -->
<!-- <img src="/assets/images/limits-graviton-5-TeV.png" alt="drawing" width="300">
<img src="/assets/images/limits-scalar-5-TeV.png" alt="drawing" width="300"> -->

<img src="/assets/images/kappa_lambda_unblinded.png" alt="drawing" width="600">

<!-- ![kappa_lambda](/assets/images/kappa_lambda_unblinded.png) -->



<!-- My PhD thesis is available on the [UCL Discovery website](https://discovery.ucl.ac.uk/id/eprint/10093101/1/10093101.pdf). The thesis is also available on [arXiv](https://arxiv.org/abs/2007.10086).
\ -->




<!--  I am passionate about the use of data science in particle physics, and I am always looking for new opportunities to apply my skills to new problems. -->