---
title: "P-values and their issues"
teaching: "~ 60"
exercises: "~ 60"
questions:
- "What is a p-value?"
- "What should I be aware of when I see a 'significant' p-value?"
objectives:
- "After this lesson, you should know what is a p-value and interpret it appropriately. You will know about the caveats of p-values."
keypoints:
- "A p-value does not give you an idea of the importance of the result"
- "A p-value should always be complemented by other information (effect size, confidence interval)"
---

## Introduction: are p-values entirely evil?

As often, any headline with a question mark is answered with a "no". But p-values have been seriously mis-used by scientists, especially in the life science and medical fields, such that they require specific attention, hence this lesson.

## P-value

### Starting with a little challenge!

> ## Can you answer these questions? Even if yes, you may want to read the p-value section
>
> Which of the following statements is/are true?
>  - A p-value is telling me that my alternative hypothesis is likely (H1 is probably true)
>  - A p-value is telling me that my null hypothesis is unlikely (H0 is probably false)
>  - A p-value is telling me that my null hypothesis is less likely than my alternative hypothesis
>  - A small p-value tells me that my data are improbable under the null hypothesis
>  - The effect size is more important to know than the p-value in the sense that it has more biological interpretation
>  - A p-value is more important for science because one cannot publish without a p-value, but one can publish without reporting an effect size
{: .challenge}

If the distribution of a statistic is assumed (by assuming the distribution of the original data) it can be used to compute a p-value. For instance, if you assume that the distribution of the sum of the $$Y$$s is normal and has zero mean, and if we estimate the dispersion (the variance), we have a distribution under the hypothesis that the sum of the values has zero mean. We can then compare the *observed* statistic with its distribution under this (null) hypothesis.

"Informally, a p-value is the *probability* under a specified statistical model that a statistical summary of the data (e.g., the sample mean difference between two compared groups) would be equal to or more extreme than its observed value." It requires that we know the distribution of the statistic (the "statistical summary") under a certain hypothesis.
[ASA Statement on Statistical Significance and P-Values](http://amstat.tandfonline.com/doi/full/10.1080/00031305.2016.1154108)

Again, [wikipedia](https://en.wikipedia.org/wiki/P-value) is a great resource. You can also read the short blog from [realClearScience](http://www.realclearscience.com/blog/2016/11/07/httpwwwrealclearsciencecomblog20161107httpwwwrealclearsciencecomblog20161102httpwwwrealclearsciencecomblog201610the_biggest_myth_about_the_p-value.html) to make sure you have the main idea right.

The key concepts and *limitations* are:

1. P-values can indicate how incompatible the data are with a specified statistical model.

2. P-values do not measure the probability that the studied hypothesis is true, or the probability that the data were produced by random chance alone.

3. Scientific conclusions and business or policy decisions should not be based only on whether a p-value passes a specific threshold.

4. Proper inference requires full reporting and transparency. P-values and related analyses should not be reported selectively.

5. A p-value, or statistical significance, does not measure the size of an effect or the importance of a result.

6. By itself, a p-value does not provide a good measure of evidence regarding a model or hypothesis.

Other resource:

This [paper](https://doi.org/10.1053/j.seminhematol.2008.04.003) by Steven Goodman (unfortunately seems to be under pay wall, please email us if you don't have access) tells you about the mis-conceptions of p-values.



### Exercise on p-values

For this exercise, you need to be able to generate some values from a normal
distribution and perform a test on the mean of these values. You can use
python, R, or octave/matlab for this. An example in python with the solutions
to the exercise is given [here](https://github.com/ReproNim/module-stats/blob/gh-pages/notebooks/P-value-exercise.ipynb).

* Generate some N sample normal data from a Gaussian distribution (mean=0,
  sigma=1, N=30)  - Let's think of this as our sampling noise. We are
  interested in the mean of our samples.

* Test if the mean is significantly greater than zero with a type I error rate
  of 5%. If it is, what was the chance of this happening?  If it is not
  "significant", repeat the sampling and test again until you find something
  significant. How many times did you need to sample again? What would you have
  expected?

* Now, say we have some signal. Simulate the case where the mean of our
  sampling distribution is $$\frac{1.64}{\sqrt{30}}$$ and the sigma is one in one
  case, and the mean is $$\frac{.164}{\sqrt{30}}$$ and the sigma is .1 in another case.
  How many times is the test significant in both cases if you do 100 simulations? what would you expect?

* You should find that roughly, the number of times these two tests are
  "significant" is about the same, because the signal to noise ratio is the
  same. But there is a fundamental difference: if the mean was representing a
  biological value, what is the fundamental difference?

### Multiple Comparison problem:

One of the best way to understand the problem is to look at the [xkcd view of it](https://xkcd.com/882/). The cartoon is great not only because it exposes the issue, but because it also exposes the *consequence* of the issue in peer review publications.

Please also go through the wikipedia of [multiple comparisons](https://en.wikipedia.org/wiki/Multiple_comparisons_problem#Classification_of_multiple_hypothesis_tests).

### Exercise on multiple comparison issue:

> ## Can you answer these questions?
>
>  - You look at the correlation between the size of the nose of individuals
>    and the size of their car. You have data from 100 cities. Is it likely
>    that you will find a correlation significant in at least one city?
>  - If I do 10 statistical significance tests, to have a false positive rate
>    of 5%, I should use $$\frac{5\%}{10}$$ for each individual test
>  - If the 10 statistics tested (eg, 10 t-statistics) are positively
>    correlated, is this correction too harsh ?
{: .challenge}


## Understanding statistical power and significance testing:

These interactive visualization are helpful to understand the concepts.

- interactive visualization for Null Hypothesis Statistical Testing (NHST):
[NHST](http://rpsychologist.com/d3/NHST/)

- And for confidence intervals:
[Confidence intervals:](http://rpsychologist.com/d3/CI/)


## P-value and **base rate fallacy**: to be read, and read again

The base rate fallacy is one of the most common source of error and mis-conception.
Here is a great article about it:

[Base rate fallacy](https://www.statisticsdonewrong.com/p-value.html)

This takes as an example the number of drugs tested on individuals, or the mamography test for cancer, but easily generalize to number of voxels or ROIs tested. It introduces you to very important concepts, read carefully and make sure you understand what is the base rate fallacy.  After reading, you should know more not only Type I and Type II errors, but importantly, on what the issue of the having low prior probability for the alternative hypothesis.

> ## Can you answer these questions?
>
>  - Can you think of a situation where the base rate fallacy occurs in brain imaging?
>  - Can you propose a way to avoid the fallacy?
{: .challenge}



## Going further: what is the distribution of a p-value?

You should have now a good idea of what is a distribution, and what is the cumulative density function of a random variable.

An interesting fact is that p-values, which are random variable because they are just a function of the data, and the data are random (since you got these specific data by sampling eg subjects).

So, say you sample from a normal N(0,1) distribution, what is the distribution of a p-value for a test T (for instance the test T is simply a z-score for a sample of N(0,1) variables). We show that this distribution is uniform, where all values are equally probable (loosely speaking).
Here is a visualization to play with: [rpsychologist.com/d3/pdist/](https://rpsychologist.com/d3/pdist/).

>  **Warning: this is *more advanced* material, you may want to skip it if you don't have some mathematical background**
>  
>  >  Let's take T as your random variable. Note, the definition of a [random variable](https://en.wikipedia.org/wiki/Random_variable) is not straightforward, but roughly speaking it is a function that "maps from an outcome of the events (that is, from a point in a probability space) to a mathematically convenient outcome label, usually a real number."
>  
>  We write *"equal by definition"* with the symbol $$\equiv$$. We note the random variables with capital letters and specific values taken by lower case letters. $$F_T$$ is the cumulative density function (CDF) of $$T$$, and $$F_P$$ is the CDF of $$P$$.
>  
>  We define our variable $$P$$ with:
>  $$ P \equiv F_T(T) $$ <!--- Where $$ F $$ is the CDF of $$ T $$ --->
>  
>  This means that $$ F_T(t) \equiv Pr(T \leq t) $$. We have by definition of $$P$$ and $$F_T$$:
>  
>  $$ Pr(P \leq p) = Pr(F_T(T) \leq p) $$
>  
>  If F is invertible, and for continuous random variable with strictly monotonic CDF (CDF that are never "flat") it is the case,  $$F_T$$ has an inverse $$F_T^{-1}$$, and we can apply this function on both side of the inequality without changing the inequality:
>  
>  $$ F_T(T) \leq p \equiv F_T^{-1}F_T(T) \leq F_T^{-1}(p) $$
>  
>  Hence,
>  
>  $$ Pr(P \leq p) = Pr(T \leq F^{-1}(p)) \equiv F_T(F_T^{-1}(p)) = p $$
>  
>  So,
>  
>  $$ Pr( P \leq p) \equiv F_p(p) = p $$
>  
>  Therefore, the CDF of $$P$$ is the identity function $$ CDF(x)=x $$. As the probability distribution function (PDF) is simply the derivative of the CDF (when this derivative exists) we finally have that $$ PDF(P) =  1 $$, with $$P$$ taking values between 0 and 1. This is a uniform random variable, each observed p is as likely as any other.
>  
This fact is used latter in this course on for instance to demonstrate the presence in p-hacking in the litterature. See lesson on what p-hacking is.
