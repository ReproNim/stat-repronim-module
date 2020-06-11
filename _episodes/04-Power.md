---
title: "Statistical power in neuroimaging and statistical reproducibility"
teaching: 60
exercises: 120
questions:
- "What is power"
- "Why is it important: issues with low statistical power"
- "Some tools for power within neuroimaging"
objectives:
- "After this lesson, you should  understand what statistical power is, and the issues of low statistical power "
keypoints:
- The lack of power is much more problematic that it seems at first sight
- It would usually lead to wasted resources
- If an under powered study yields some significant effects, these are likely to be overestimated
- If an under powered study yields some significant effects, these are less likely to replicate
---

## Power : definition and some exercices

First, we will be doing some work within this [jupyer notebook](https://github.com/ReproNim/module-stats/blob/gh-pages/notebooks/Power-basics.ipynb).


How to work with the notebook?
There are two cases.
1. You do not really know python, and how to install the jupyter notebook. You can still read the notebook, skipping the code sections. The notebook will introduce some definitions, and then play with different settings. But the true benefit comes if you can install the jupyter project [see here](http://jupyter.readthedocs.io/en/latest/install.html) and actually play with the code, for instance changing the sample size or effect size to understand better what statistical power is.
2. Download the notebook, and try to understand the concepts and the code. If the code is unclear, please make an issue on the repronim [github site](https://github.com/ReproNim/module-stats/tree/gh-pages/notebooks).
3. Run it interactively in your browser through [binder]().

## Some simple simulations  

> ## Exercise:
> visit this [site](http://rpsychologist.com/d3/NHST/) and set your test to
> be one tailed at the false positive risk of 0.05. Say a typical effect size in
> fMRI corresponds to a Cohen's d of 0.5.
> What is the sample size that you find?
>
> Now, relate to what we are doing in fMRI. What is the problem? Can you use this
> online tool to get the number of subjects for your experiment? If yes, give a
> typical example, if not, explain the problem.
>
{: .challenge}


## Relation with confidence intervals ?

Last, you'll need to go through this [jupyter notebook](https://github.com/ReproNim/module-stats/blob/gh-pages/notebooks/Misconceptions-Confidence-Intervals.ipynb).
