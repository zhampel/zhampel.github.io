---
title:  PyUnfold - The Iterative Unfolding Package
mathjax: true
---

# Introduction
Scientists of all disciplines make observations that are subject to the finite
resolutions and biases of their detectors.
Recently


# Features
The main novel features that are included in PyUnfold include:
- it's written in Python, using Numpy, Scipy, Pandas
- ability to input custom priors
- regularization via spline fitting
- unfolding in different cause groups

Basically, if you have a measured effects (data) distribution and can estimate 
the response matrix connecting causes to effects you can use PyUnfold to run an
iterative deconvolution!

\\(\mathbf{y} = A \mathbf{x}\\)

$$
n(E) = R \ \phi(C) \\
\phi(C) = M \ n(E)
$$

The main PyUnfold website, full of usage examples can be found 
[here](https://jrbourbeau.github.io/pyunfold/index.html).

The JOSS paper can be found [here](ihttps://joss.theoj.org/papers/7ce84a37ff74be06ef28f8ea9b8831e6).

The slides for this talk can be found [here](https://zhampel.github.io/intro-ml-iihe/).
