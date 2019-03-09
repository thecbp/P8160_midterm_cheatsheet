Algorithm Implementations
================
Christian Pascual
3/9/2019

Table of Contents
=================

-   <a href="#em">EM Algorithm</a>
-   <a href="#gauss-mix">Mixed Gaussian</a>
-   Old Faithful Geyser
-   Zero Inlfated Poisson
-   Lightbulbs
-   Fisher's Genotype
-   ABO Blood Type

<h2 id="em">
EM Algorithm
</h2>
<h3 id="gauss-mix">
Mixed Gaussian
</h3>
Your population is actually a mixture of two Gaussians, and you want to estimate the best *μ*<sub>1</sub>, *σ*<sub>1</sub>, *μ*<sub>2</sub>, *σ*<sub>2</sub> to maximize the observed likelihood:

$$L\_{obs}(x) = \\prod^n\_{i=1}(1 - p)f(x\_i, \\mu\_1, \\sigma\_1) + p f(x\_i, \\mu\_2, \\sigma\_2)$$
 where each *f* is just a normal density function.

Your latent variable is *Z* ∼ *B**i**n*(1, *p*) such that if *Z* = 0, *X*<sub>*i*</sub> comes from the first normal and the second if *Z* = 1.

Thus, the complete log-likelihood is:
$$l(X,Z,\\theta)  = \\sum^n\_{i=1}\[Z\_ilog(p) + (1-Z\_i)log(1-p) +Z\_ilogf\_2 + (1-Z\_i)f\_1\]$$
