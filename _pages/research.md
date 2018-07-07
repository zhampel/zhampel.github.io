---
layout: single
title: Research
permalink: /research/
author_profile: true
type: pages
scope:
    path: ""
    type: pages
toc: true
toc_label: "Research"
header:
  overlay_image: /assets/images/sunset-gsl.jpg
  caption: "&#169; Z. Hampel-Arias"
mathjax: true
---

## Cosmic-Rays

### Introduction
Cosmic rays are charged particles that are born in the some most violent environments in our Universe. 
The cosmic rays that arrive at Earth are primarly composed of protons and alpha particles, with elements up to iron nuclei 
(and some heavier elements in trace amounts) in the mix.
By studying the energy spectrum, arrival distribution, and composition of these particles, we can learn more about
the origins of cosmic rays and the environments in which they travel to reach us.
Ultimately, it is by understanding these smallest consituents of matter that we can get a better picture of the largest structures in our Universe.

![shower-image](/assets/images/extensive_air_shower.png){:height="45%" width="45%"}{: .align-left}
{: .text-left}
Primary cosmic ray particles with energies above 100 GeV incident at the top of 
the Earth's atmosphere produce extensive air showers, characterized by a 
wide but thin disk of secondary particles (left) that travels at nearly the speed of light.
The nature of the primary particle determines how the shower will evolve,
allowing us to estimate its identity and energy with detectors on the ground. 
This is done using the relative timing and measured signals of the detector elements
(blue boxes) as the air shower passes over the detector.

Image credit: Z. Hampel-Arias

### Research with HAWC
![hawc-image](/assets/images/HAWC_Photo.jpg){:height="50%" width="50%"}{: .align-right}
{: .text-left}
My PhD research focused on making cosmic rays measurements with the [HAWC Observatory](https://www.hawc-observatory.org/),
an air-shower experiment located near Puebla, Mexico on the slopes of Pico de Orizaba (right).
HAWC comprises a total of 300 large water tanks, each being 7 meter high and 4 meter wide,
and having four sensitive light collectors from which we make our measurements on cosmic-ray showers.

{: .text-right}
Photo credit: Z. Hampel-Arias


{: .text-left}
#### Energy Spectrum
In the energy range at which HAWC is sensitive to cosmic rays, the best measurements by other 
experiments are subject to either diminishing statistics or large systematic uncertainties.
By limiting our data to only the best events, we were able to measure the cosmic ray spectrum,
showing structure that had not been previously verified.
This was done by harnessing the statistical technique discussed below as well as a validation 
of our methods using cosmic-rays blocked by the Moon, i.e. the Moon shadow.

![moon-shadow-image](/assets/images/moon_shadow_illustration.png){:height="35%" width="35%"}{: .align-left}
{: .text-left}
Since the Earth's magnetic field bends cosmic-ray trajectories, the observed Moon shadow shifts 
with energy, allowing us to verify our energy and angular estimates.
This [cool animation](https://youtu.be/0FDwW1mo2Vk) shows this 
energy-depenent bending as low-energy protons interact with the geomagnetic field.
In the video, some particles get stuck in the field, tracing out its shape as large arcs.
Indeed, it's these low energy particles that cause the [aurorae](https://en.wikipedia.org/wiki/Aurora)!
HAWC measures particles with much higher energy, but the same physics applies.
The visualization was generated using my charged particle propagation tool found 
[here](https://github.com/zhampel/cr-geomag-prop).

{: .text-left}
Image credit: [WIPAC](https://hawc.wipac.wisc.edu/hawc/science)

The results of this study were published as an Editor's Suggestion in 
*[Phys. Rev. D](https://journals.aps.org/prd/abstract/10.1103/PhysRevD.96.122001)*. 
also available on the [arXiv](https://arxiv.org/abs/1710.00890).
We also harnessed the Moon shadow technique to measure the anti-proton to proton ratio, recently published 
in *[Phys. Rev. D](https://journals.aps.org/prd/abstract/10.1103/PhysRevD.97.102005)*,
found here on the [arXiv](https://arxiv.org/abs/1802.08913).

#### Anisotropy
Whereas the energy spectrum provides clues about the nature of particle accelerators, the arrival
distribution of cosmic rays gives us an idea of where these particles are coming from.
In addition to probing cosmic ray source distributions, as with the Moon shadow, we also get a glimpse
into the intervening magnetic field structure of interstellar space.
In collaboration with my HAWC colleagues, we recently submitted our study of the cosmic ray anisotropy
at TeV energies to the Astrophysical Journal, found [here](https://arxiv.org/abs/1805.01847) on the arXiv. 




{: .text-left}


## Statistical Deconvolution

### Introduction
In order to measure the cosmic ray energy spectrum, I used a deconvolution method called unfolding.
Since not all showers reach the ground or trigger our detector, and the fact that our HAWC is, sadly,
not perfect, we can take into account these measurement inefficiencies and biases to *unfold* an 
estimate of the true spectrum.
Basically, we build what's called a response function which connects the probability of a true **cause**
that we want to estimate to produce a **effect** we can measure.
This method is great for experimental situations where a perfect analytic form of this function is not
known or easy to construct.
Instead we build a matrix from simulation that allows us to do the unfolding.
This method falls under the category of inverse problems, where for sets of causes \\(c_{\mu}\\) and effects \\(e_j\\),
and a constructed response matrix \\(\mathbf{R}\\), we want to find \\(\mathbf{M} \approx \mathbf{R}^{-1}\\) such that

$$
\mathbf{e} = \mathbf{R} \, \mathbf{c} \\
\mathbf{c} = \mathbf{M} \, \mathbf{e}
$$

D'Agostini in his 1995 [paper](https://www.sciencedirect.com/science/article/pii/016890029500274X)
developed a method that starts from Bayes' Theorem to obtain an approximate form for \\(\mathbf{R}^{-1}\\).
This iterative unfolding procedure is widely-used in the high-energy physics community (HEP) and 
has some advantages over other matrix inversion methods, for example in cases where no inverse actually exists.

### PyUnfold
![pyunfold-image](/assets/images/pyunfold.png){:height="20%" width="20%"}{: .align-right}
{: .text-left}
The code I designed for the HAWC cosmic ray measurement has been generalized for use beyond the HEP community 
by myself and another astrophysicist (with some updates from D'Agostini's original version),
and is now packaged as [PyUnfold](https://jrbourbeau.github.io/pyunfold/index.html).
The project was recently accepted in the Journal of Open Source Software
[![DOI](http://joss.theoj.org/papers/10.21105/joss.00741/status.svg)](https://doi.org/10.21105/joss.00741)
also available on [Zenodo](https://zenodo.org/record/1258211).
