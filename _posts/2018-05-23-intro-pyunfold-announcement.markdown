---
title:  PyUnfold - The Iterative Unfolding Package
mathjax: true
---

## Introduction
Scientists of all disciplines make observations that are subject to the finite
resolutions and biases of their detectors.
In the case that the **response** of a experimental apparatus does not have
an analytic form or is invertible, but can be approximated by simulation for example,
the desired true distribution that causes measurable effects in the detector
can be *unfolded*.

This falls under the general field of linear inverse problems, where given a measured
distribution \\( n(E) \\) of effects \\(E\\), and a known response matrix \\(\mathbf{R}\\),
the goal is to find an estimate \\( \mathbf{M} \approx \mathbf{R^{-1}} \\) so that we can
find an estimate of the true distribution \\(\phi(C)\\) of causes \\(C\\).
I.e.,

$$
\begin{align}
  n(E) &= \mathbf{R} \ \phi(C) \\
  \phi(C) &= \mathbf{M} \ n(E)
\end{align}
$$

## PyUnfold
Recently, a colleague James Bourbeau and I released a package written in Python called 
[PyUnfold](https://jrbourbeau.github.io/pyunfold/index.html)
that performs this deconvolution using a method widely used in experimental high-energy physics.
The package has been published in the Journal of Open Source Software: 
[![DOI](http://joss.theoj.org/papers/10.21105/joss.00741/status.svg)](https://doi.org/10.21105/joss.00741),
also available on [Zenodo](https://zenodo.org/record/1258211).




## Features
The novel features implemented in PyUnfold include:
- it's written in Python, using Numpy, Scipy, & Pandas
- ability to input custom priors
- convergence based on test statistic criterion
- tunable regularization via spline fitting
- unfolding in different cause groups, i.e. multidimensional deconvolution

Basically, if you have a measured effects (data) distribution and can estimate 
the response matrix connecting causes to effects you can use PyUnfold to run an
iterative deconvolution!


I recently gave an introductory talk about PyUnfold at the IIHE at ULB/VUB in Brussels.
The slides can be found [here](https://zhampel.github.io/intro-pyunfold-iihe/).


## Success Stories
PyUnfold has been successfully used in several contexts, including:
- Cosmic-ray energy spectrum measurement made by the `HAWC observatory <https://www.hawc-observatory.org/>`_ [1]_.
- Cosmic-ray composition analysis using the `IceCube South Pole Neutrino Observatory <https://icecube.wisc.edu/>`_.


.. [1] Alfaro, R. and others. 2017. "All-particle cosmic ray energy spectrum measured by the HAWC experiment from 10 to 500 TeV." *Phys. Rev. D* 96 (12):122001. `<https://doi.org/10.1103/PhysRevD.96.122001>`_.
