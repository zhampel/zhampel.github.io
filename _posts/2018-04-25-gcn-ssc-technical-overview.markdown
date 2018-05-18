---
title:  Overview of Semi-Supervised Classification with GCNs @ ML6
mathjax: true
---

A variety of data sets are comprised of samples that share some sort of relationships amongst each other.
However, it's quite possible that all the samples are not fully labelled.
One can consider an example such as a social network such as Facebook.
The network, or the friend connections, is known but perhaps only a fraction of the users publicly display
their political stance, or their favorite movie, or their ages.
In a non-fully labelled data set, so long as the connectivity between samples is well-defined,
we can think of how to estimate unlabelled samples by training a model in one of two ways:

- train on just the labelled set, smoothing the with the connectivity
- train on the entire set, embedding the connectivity in the model 

For both methods, this is considered a semi-supervised paradigm, since we don't have all sample labels.
As Kipf & Welling show in this cool [paper](https://arxiv.org/abs/1609.02907),
by embedding the connective structure within the machine learning algorithm itself,
one can get amazing results classifying the unlabelled part of the data set.
They make a series expansion of a convolutional filter, effectively embedding the graph structure
in a linear fashion.
This allows them to probe \\(n\\) levels of connectivity by stacking \\(n\\) filters when building
a neural network like model.
Furthermore, this structure permits fast, parallelizable training that outperforms other semi-supervised algorithms.

I recently gave a technical talk at ML6 in Ghent, covering the details of Kipf & Welling's [paper](https://arxiv.org/abs/1609.02907).
The slides for the talk can be found [here](https://zhampel.github.io/gcn-ssc-technical-overview/).
