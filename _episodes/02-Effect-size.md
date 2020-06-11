---
title: "Effect size and variation of effect sizes in brain imaging"
teaching: 120
exercises: 180
questions:
- "Variance explained"
- "What is an effect size, statistical versus biological or medical relevance"
- "Why effect sizes vary: sampling, models, processing parameters, population, effect of unknown parameters"
- "Other measures of effect size"
objectives:
- "After this lesson, you should have a good knowledge of what is an effect size, and why it is important to estimate, report and assess. "
keypoints:
- "Effect sizes come in many forms"
- "Significance is not relevance"
- "Difference between the raw effect size and the cohen's d effect size"
- "How can the effect size vary?  Why is it important to know about this?"
- Effect sizes are under reported, not well understood, and are crucial for our scientific understanding. Let's fix this.

---

### Effect sizes: first basics.  

Here, we start with an explanation of the effect size using a t-test. First, have a look at the [wikipedia](https://en.wikipedia.org/wiki/Effect_size) page on effect size. Please read carefully the Overview section.    

Effect sizes come with many flavors, Wikipedia also lists a series of type of effect size, such as correlation, variance explained, difference of means, etc. When normalized, they are suppose to capture in some sense the difficulty of detecting such an effect. When not normalized, they can give us a sense of the underlying biology. For instance, you would in general not believe that the volumes of the front lobes of a population diagnosed with autism are on average twice bigger than a control population, but a few cubic mm would be believable (although not necessarily true).

$$\sqrt{\frac{a}{b}}$$

Is the overview clear to you? Just to give you a concrete example if it is not, say we want to test the difference of the means of two populations, for instance the brain activity in the visual cortex for the normal versus patient population. We *sample* 30 normals and 30 patients, and we compute *estimated* means of the two populations using our *samples* of 30 + 30 participants. Let's measure the BOLD response in the visual cortex for all participants. The average of the 30 participants in the control group (CG) is 5%. The average of the 30 participants in the patient group (PG) is 8%. The standard deviation of the data (not of the average that we just referred to) in the CG is 1%  and the standard deviation of the CG is 2%.

Now, let's say we are studying the activity of the visual cortex in the CG. You want to know if this is different from zero. The *estimated* (or sampled) effect size for the CG is 5%. The **normalized** effect size will be divided by the **standard deviation of the data**, so $$\frac{5}{1} = 5$$ for CG, and $$\frac{8}{2}=4$$ for the PG, while the corresponding t-tests will be $$t=\frac{5}{\frac{1}{\sqrt{30-1}}}$$ and $$t=\frac{8}{\frac{2}{\sqrt{30-1}}}$$. The true effect size (the one Wikipedia would write in greek letter) would be the value of the BOLD responses for the **whole populations** of control and patients.

How would _you_ define the *estimated* effect size of the difference of the two population? The "raw" / "not normalized" effect size would simply be (8-5)%. To define the **normalized** we need to estimate the variability of the data, and this can be done using the pooled standard deviation (something close to the average of the two standard deviations weighted by the group sizes). See "Cohen's d" in the "Difference family: Effect sizes based on differences between means" section of  [wikipedia](https://en.wikipedia.org/wiki/Effect_size).  See also the use of the [Welch's](https://en.wikipedia.org/wiki/Welch%27s_t-test) and its estimation of the statistics degrees of freedom, which could provide another way to define the normalized effect size.

As you see now, "effect size" is not necessarily a simple topic. It requires to stand back and think of what is most appropriate to report, and often, you will need to report several values.

Using a normalized effect size is that it makes comparisons possible across samples with different standard deviation, but takes us away from the original data. See more on this in some further episodes.

This [article](http://staff.bath.ac.uk/pssiw/stats2/page2/page14/page14.html) is a good introduction to the subject, please read it and make sure everything is now familiar.



<!-- **Questions:**
	- Is the coefficient of correlation an effect size ?
	- Can I always compare normalized effect sizes?
-->

---

> ## Questions
>     - Is the coefficient of correlation an effect size ?
>     - Can I always compare normalized effect sizes?
>
{: .challenge}

### Variance explained, using the example of the general linear model

There are many good introductions to the GLM. Here, we propose that you use the pages from this course. The course takes you through the very basics of the GLM and shows you some implementation with python.  

Assignment: Read [this web page](https://matthew-brett.github.io/teaching/glm_intro.html). Use a terminal and python to go through the code and understand what is being done. If you do not know about python, you can go through the same page with R or Matlab, it will not take long to translate it. However, we recommend that you learn enough python to be able to follow. If you need a python introduction, please follow the [beginners course](https://www.python.org/about/gettingstarted/) of Python.

Now that you have a first  understanding of the GLM, make sure you follow easily [this page](https://bic-berkeley.github.io/psych-214-fall-2016/mean_test_example.html) that walk you through an other example.

The next step is to understand the notion of variance explained. With your new (or refreshed) knowledge of the GLM, you can now go to [this page](https://bic-berkeley.github.io/psych-214-fall-2016/hypothesis_tests.html) that explains the t and F tests. When you have gone through this page, understand what the R2 in multiple regression is. Again, [wikipedia](https://en.wikipedia.org/wiki/Coefficient_of_determination) is a great resource, and you should now read and understand the parts up to section "Interpretation".

Coming back to the effect size, we now can understand the Cohen's f2 effect size in [wikipedia](https://en.wikipedia.org/wiki/Effect_size).


> ## Exercise
>     - Is the R2 a "normalized effect size" ?
>     - If you have an experiment with three samples of different populations, and some other covariables. Can you write what would be the R2 for the part of the model that corresponds to the difference of the means of the three groups? Can you generalize the wikipedia page on R2 to account for the case of an F test ? See how this is explained in a non-simple linear model in [wikipedia](https://en.wikipedia.org/wiki/Coefficient_of_determination).
>			- If I am computing an effect size from the general model with neuroimaging data, should it be a standardized one? Why?
>
{: .challenge}



---

###  Effect size: statistical versus biological or medical relevance

In this section, we want to stress the difference between a significant effect and an important one.

See for instance this [paper](http://onlinelibrary.wiley.com/doi/10.1111/j.1469-185X.2007.00027.x/full)

In particular, read the section "Effect size and confidence interval".

Please read it till paragraph "(2) Covariates, multiple regression, GLM and effect size calculations": this paper sumarize a lot of the information that we need to work efficiently. This should take you around one to two hours. Try then to answer the following

> ## Questions
>     - What was the meaning of "effect size" in the Wikipedia page?
>     - Can you point to some neuroimaging work that make obvious what is the effect size of the results?
>			- The authors refer to three type of effect sizes on page 595 in the section "How to obtain and interpret effect sizes". Can you think of a possibly missing effect size?
>			- Why are the authors advocating for non-normalized effect (eg top of p 597, right column)?
{: .challenge}


---

###  The variation of effect sizes

What can influence effect sizes beyond their "true" variation ? While fundamental, effect sizes may vary because of a number of factors, and we need to understand these factors to get a reasonable interpretation.   

####	    Variation with sampling, or variation because we are using a slightly different population

First, we have to remember that the effect size is simply a "statistic", i.e. a function of the data. This means that with a different sampling of the data (say, 50 new participants) we will get a new effect size.


> ## Exercise:
>
>  Go back to the [Nakagawa and Cuthill 2007 work](http://onlinelibrary.wiley.com/doi/10.1111/j.1469-185X.2007.00027.x/full, "Effect size, confidence intervals, p-values") and observe figure 2. What do you see in terms of the effect size for the same p value but different sample sizes ?
>
> > ## Answer
> >
> > What you observed is a classic effect of the effect size: despite the fact that it should be about the same for different resampling of the population, it changes with the sample size if the p-value is fixed. Why? Because with a smaller sampling, the effect needs to be higher to reach the same significance. The issue that we will come back to in this course is that because only 'significant' results are reported, large effect size can be obtained and reported because of small sampling and significant results.
> >
> {: .solution}
{: .challenge}


In short, be aware that effect size may be "sample size" dependent. One interesting paper to read about this is the [Lefebvre, Beggiato, Bourgeron and Toro](http://biorxiv.org/content/early/2014/02/15/002691) study on the corpus callosum size between normal controls and ASD (Autism Spectrum Disorder). This paper shows how small sample size may influence meta analysis and gives actual effect sizes.

#### Variation of effect size with a different model

Let's say you are interested in the size of the hippocampus and its  difference between males and females. Say that on average the males heads are larger than the females head, to look at the gender effect we would need to correct for all other effects that may affect the size of the hippocampus. The problem here is that we don't know which factors affect this variable. Using the PING datasets, we looked at this recently, and found that including some phenotypic data made a large difference on the the effect size of gender.

First, many datasets would not have an extensive phenotyping, and so we may see in the literature results that may be influenced by the fact that covariables were simply not availalbe. Second we actually don't know if there are not any other variable that we should have measured and that may influence this gender effect.


> ## Exercise:
>
> Read the last part of the [Nakagawa and Cuthill 2007 paper](http://onlinelibrary.wiley.com/doi/10.1111/j.1469-185X.2007.00027.x/full), "Effect size, confidence intervals, p-values") from "(2) Covariates, multiple regression, GLM and effect size calculations".
> - In this paper, we see that the effect size estimates for a given variable will vary according to what other predictor variables are in the model.
How will this effect size varies if the other predictor variable introduced is correlated to the predictor we want to compute the effect size of ? and anti correlated ? what if we do not include a correlated (or anti correlated) regressors ?
> - Can you understand the principle of equation 10? Remember than the t value is constructed by the ratio of  of the non normalized effect size and an estimation of the variance of this effect size. Compare (10) to what you would get with a simple GLM t test equation where the design matrix encode simply groups with two dummy variables that have $$n_1$$ and $$n_2$$ "ones" on the first and second column respectively.
>
{: .challenge}


#### Variation of effect size with workflow / pre-processing or over analysis choices parameters

The variation of the workflow parameters will influence effect size. In fact, it is crucial to see what parameters of the workflow influence the effect size and statistical significance, since this will speak about the robustness of the results. See for instance,

> [Carp, J. (2012). On the Plurality of (Methodological) Worlds: Estimating the Analytic Flexibility of fMRI Experiments. Frontiers in Neuroscience 6.](https://www.frontiersin.org/articles/10.3389/fnins.2012.00149/full)

See also Glatard and colleagues:

>  [Glatard, T., Lewis, L.B., Ferreira da Silva, R., Adalat, R., Beck, N., Lepage, C., Rioux, P., Rousseau, M.-E., Sherif, T., Deelman, E., et al. (2015). Reproducibility of neuroimaging analyses across operating systems. Frontiers in Neuroinformatics 9.](https://www.frontiersin.org/articles/10.3389/fninf.2015.00012/full)

### Other measures of effect sizes

#### 	Can "prediction rate" be used ?

When the problem can be stated in a "prediction" framework, the prediction rate on test data (data that have not been used to construct the prediction model) is a good "effect size". It is interpretable, prediction is really what we want to have in science, and it will in general be related to the more traditional effect sizes.

### 	Can mutual information be used ?

- What is mutual information ? Why would it be a good measure of the effect size ?

Please read the wikipedia [article](https://en.wikipedia.org/wiki/Mutual_information) on this.  

> ## Question:
>
> - Why would mutual information be an acceptable and possibly interesting effect size? 
> - Would the problem of other unknown predictor be alleviated by this measure?
{: .challenge}




Some formula are interesting:
$$
\frac{\text{Explained  variance  by  the  predictors of interest}}{\text{Residual error variance}}
$$

### Effect size calculation

[This site](https://www.psychometrica.de/effect_size.html) provides with a number of online calculations of effect sizes. Beware that the site begins with "Statistical significance means that a result may not be the cause of random variations within the data". This is a true statement, it _may not_ be caused by random variation of the data (sampling) but _it also may_ (the rate should be the risk of error of type I).
