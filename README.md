# randomForestCI

&#x1F534; This package is deprecated. Please use the package <a href="https://github.com/swager/grf">GRF</a> instead, which has built-in support for confidence intervals. GRF is also available from <a href="https://cran.r-project.org/web/packages/grf/index.html">CRAN</a>. &#x1F534;

Confidence intervals for random forests using the infinitesimal jackknife, as developed by Efron (2014) and Wager et al. (2014).

To install this package in R, run the following commands:

```R
install.packages("devtools")
library(devtools) 
install_github("swager/randomForestCI")
```

Example usage:

```R
library(randomForestCI)

# Make some data...
n = 250
p = 100
X = matrix(rnorm(n * p), n, p)
Y = rnorm(n)
  
#  Run the method
rf = randomForest(X, Y, keep.inbag = TRUE)
ij = randomForestInfJack(rf, X, calibrate = TRUE)

plot(ij)
```

#### References
Efron, Bradley. <b>Estimation and accuracy after model selection.</b> <i>Journal of the American Statistical Association</i>, 109(507), 2014. [<a href="http://statweb.stanford.edu/~ckirby/brad/papers/2013ModelSelection.pdf">link</a>]

Wager, Stefan, Trevor Hastie, and Bradley Efron. <b>Confidence intervals for random forests: The jackknife and the infinitesimal jackknife.</b> <i>The Journal of Machine Learning Research</i>, 15(1), 2014. [<a href="http://jmlr.csail.mit.edu/papers/volume15/wager14a/wager14a.pdf">link</a>]
