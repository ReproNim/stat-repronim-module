---
title: "Statistical basis for neuroimaging analyses: the basics"
teaching: "~ 60"
exercises: "~ 60"
questions:
- "Sampling, notion of estimation: estimates of mean and variances"
- "Distributions, relation to frequency, PDF, CDF, SF, ISF "
- "Hypothesis testing: the basics H0 versus H1"
- "Confidence intervals "
- "Notion of model comparison: BIC/Akaike"
- "Notion of bayesian statistics "
objectives:
- "After this lesson, you should have the statistical basis for understanding this course. You will know what sampling is, the fundamentals of statistical testing, etc.  "
keypoints:
- "Be familiar with the concept of sampling"
- Know what we call a distribution, a p-value, a confidence interval
- Have some knowledge of Bayesian statistics and model comparison
- This is in line with our overall goal of making science (including scientific training) more open.

---


## Introduction: Why do I need to know all this?

In our experience, you will not be able to think clearly about how "solid" the result you obtain without a sufficient background in statistics. Sometimes, you will think that this is taking you "too far". We truly do not think so, and if you bear with us long enough we hope that you will find this rewarding, and useful.

## Sampling

In this unit, we would like you to fully understand the concept of a sample as a subset of a population.

It is critical that you master that concept, as it is at heart of most scientific studies.
-sample vs population
-generalizability
-notion of sufficient sample

Please read the sections on this webpage:
[Basics of sampling](http://www.socialresearchmethods.net/kb/sampling.php)

The key concepts are:

1. A sample is a subset of a population: if you resample you will get a different result (different mean, different standard deviation).

2. The quality of the sample is related to the generalizability of the conclusions one can draw on the larger population of interest.

3. Say you sample 30 participants from a seemingly infinite population. Say you compute an average of some characteristics, for instance participant brain volume, $$M$$ across these 30 subjects. The *sampling distribution* of $$M$$ is the distribution you would obtain if you were to repeat de sampling of 30 participants a great number of times, for instance 10,000 times. For each sampling of 30 values, you would compute the mean of the sampling, and see what is the distribution of this mean across all 10,000 samplings. These 10,000 values should be distributed about the true (unobserved) mean of the population.


> ## Questions on sampling. --->
>
>  - If you sample two times a population, and compute the two means of these two samples, will you get necessarily two close values ?
>  - Is the difference between these two means going to be always smaller if the sample size increase to say 60?
>  - Same question as above, but in the case the sample size increase to a very large number ?
{: .challenge}

## Statistics and random variables

You may hear a statistician talk about "a statistic". For instance, $$t$$ or $$F$$ values are statistics distributed according to a Student or a Snedecor distribution. But what is a "statistic" ?
In simple words, a statistic is any function of the data. The data are generally randomly sampled, and their distribution is often modelled with known distribution. Let's imagine that you have measured something interesting on $$N$$ subject, say that the measures are the $$Y_1,Y_2, ..., Y_N$$, and you are interested in the mean of the $$Y$$. The mean is a function of the data. It is a "statistic". So would be the product of the $$Y$$s, etc. Since the $$Y$$s are random, say that they are randomly sampled from a population, and that another sampling would yield different values, the statistic is a random variable as well. For some interesting statistics, such as the average divided by the standard deviation, the distribution of the statistic is known if we assume the distribution of the original data to be known (often, a normal distribution is assumed). For example, the sum of the square of normally distributed data is distributed following a Chi2 distribution.

## Distributions

You need to understand what is a *probability distribution* (or simply *distribution*) of a random variable. Here is a [link](https://en.wikipedia.org/wiki/Probability_distribution) on what probability distributions are.
There is also this [link](http://mathworld.wolfram.com/StatisticalDistribution.html) that will tell you about statistical distributions.


Next, we need to be able to use the [Cumulative distribution function (CDF)](https://en.wikipedia.org/wiki/Cumulative_distribution_function). For a given value $$x$$, the CDF will give us the probability that the random variable will be less (or equal) than $$x$$.
The CDF is related to its Complementary cumulative distribution function (also called tail distribution, or survival function :  $$ SF(x) =  1 - CDF(x) $$.

See the [survival function](https://en.wikipedia.org/wiki/Survival_function) in wikipedia.

The cumulative density function of a random variable X is often noted $$F_X$$ or simply $$F$$ when there is no ambiguity.

> ## Questions on distribution and cumulative distribution function (CDF). --->
>
>  - Imagine that we have a normally distribution with a mean -20 and a sigma of 1. Will the CDF at 0 be flat and have a value of 0 or flat with a value of 1?
>  - Same question as above with a mean of the normal distribution equal to 20 ?
>  - If the mean of the normal distribution equal to 0, will the CDF be "flat" around 0 ? will the value be .5, .95 or .975 ?
>  - Can we talk of a CDF of a discrete random variable (for instance, taking values 1,2,3,4,5,6 like a dice)?   
>  - Can we talk of a CDF of a categorical random variable (for instance, taking values blue white red)?   
{: .challenge}


## Testing

Testing, or "statistical inference", is what you do when you are trying to make
a decision on a specific hypothesis. For instance, if I assume that the
hippocampus of taxi drivers is larger than individuals from other professions,
how do I decide that this is true? Or, in a Popperian framework, can I falsify
the hypothesis that the hippocampus of these two groups have the same size?
The answer to this question is to 1) sample the population of taxi drivers,
sample the population of people who are not taxi drivers, measure the hippocampi in the two
groups, 2) assume that the two groups are in fact drawn from one homogeneous
population and 3) see if the data observed are likely under this assumption.
If they are not, with some risk of error, then we *reject* the null hypothesis,
and accept the alternative.

This decision is generally made with a statistical test, that computes a
p-value under the "null hypothesis", and rejects this hypothesis if the p-value
is less than 5%. See our [lesson on p-values and caveats](http://www.repronim.org/module-stats/03-p-values/) further.

### Risk of errors

There are at least two risks of errors (as introduced by J. Neyman and G. Pearson): 1) Deciding that the two groups are drawn from different populations when in fact that is not the case, (type I error) and 2) deciding that the two groups are drawn from one homogeneous population while this is not the case (type II error). There are also errors of higher types see [the wikipedia article](https://en.wikipedia.org/wiki/Type_III_error) on this.


### Introduction to the multiple comparison problem

The issue occurs when many hypotheses are made. If we control for the risk of error of type I for each test, after many tests, some will be "significant" just by chance.


## Bayesian statistics

Finding the right level of introduction for this topic is not easy. We propose to start with [this blog](https://www.analyticsvidhya.com/blog/2016/06/bayesian-statistics-beginners-simple-english/) which should give you a good introduction.

There is also [this one](http://faculty.washington.edu/kenrice/BayesIntroClassEpi515.pdf). Exercises on this still need to be developed [TBD].


Bayesian statistics are *rarely* used, because researchers are often unsure on how to use them, and because they sometimes can be used to include subjective knowledge. However, they have a better theoretical ground and in many cases they should be used.

The inertia of the community to adopt the bayesian framework is clear.  One reason for this inertia is that researchers and reviewers would need some training, and the training -at the level required- is often missing. Another issue is that the computational tools are also sometimes missing.  

### Questions on Bayesian statistics and comparison with frequentist:

* Why are Bayesian statistics not very used in medical or life science journals?
* What are the key advantage of Bayesian statistics?
* What do Bayesian statistics require before you can apply them - do we have this

## Notion of model comparison: BIC/Akaike

Model comparison is **fundamental**. Here are a few links on this topic:

* [Wikipedia AIC](https://en.wikipedia.org/wiki/Akaike_information_criterion)

* [Wikipedia BIC](https://en.wikipedia.org/wiki/Bayesian_information_criterion)

* And a comparison of these two [here](https://methodology.psu.edu/AIC-vs-BIC)
