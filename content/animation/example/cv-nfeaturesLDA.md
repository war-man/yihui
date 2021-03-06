---
title: cv.nfeaturesLDA()
subtitle: Cross-validation to find the optimum number of features (variables)  in LDA
date: '2017-04-04'
slug: cv-nfeaturesLDA
from_Rmd: yes
---

This function provids an illustration of the process of finding out the
optimum number of variables using k-fold cross-validation in a linear
discriminant analysis (LDA).

For a classification problem, usually we wish to use as less variables as
possible because of difficulties brought by the high dimension.

The selection procedure is like this:

- Split the whole data randomly into `\(k\)` folds:
- For the number of features `\(g = 1, 2, \cdots, g_{max}\)`, choose `\(g\)` features that have the largest discriminatory
power (measured by the F-statistic in ANOVA):
- For the fold `\(i\)` ( `\(i = 1, 2, \cdots, k\)` ):
- Train a LDA model without the `\(i\)`-th fold data, and predict with the `\(i\)`-th fold for a proportion of correct predictions `\(p_{gi}\)`;
- Average the `\(k\)` proportions to get the correct rate `\(p_g\)`;
- Determine the optimum number of features with the largest `\(p\)`.


Note that `\(g_{max}\)` is set by `ani.options('nmax')` (i.e. the
maximum number of features we want to choose).

 

```r
library(animation)
ani.options(nmax = 10)
par(mar = c(3, 3, 0.2, 0.7), mgp = c(1.5, 0.5, 0))
cv.nfeaturesLDA(pch = 19)
```

```
## Loading required namespace: MASS
```

<video controls loop autoplay><source src="https://assets.yihui.name/figures/animation/example/cv-nfeaturesLDA/demo-a.mp4?dl=1" /><p>plot of chunk demo-a</p></video>

This animation provides an illustration of the process of finding out the optimum number of variables using k-fold cross-validation in a linear discriminant analysis (LDA).
