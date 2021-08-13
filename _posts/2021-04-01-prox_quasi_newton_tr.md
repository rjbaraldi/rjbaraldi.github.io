---
title: "A Proximal Quasi-Newton Trust-Region Method for Nonsmooth Regularized Optimization"
excerpt: "We present a trust-region algorithm that computes the descent direction with a proximal gradient-like step. "
header:
  image: assets/images/trnc/tr-nonsmooth-figure6.jpg
  teaser: assets/images/trnc/tr-nonsmooth-figure6.jpg
sidebar:
  - title: "Journal"
    image: /assets/images/doe.png
    image_alt: "logo"
    text: "SIAM Optimization"
gallery:
  - url: assets/images/trnc/tr-nonsmooth-figure6.jpg
    image_path: assets/images/trnc/tr-nonsmooth-figure6.jpg
    alt: "Data Fit with TR-PG"
  - url: assets/images/trnc/tr-nonsmooth-figure7.jpg
    image_path: assets/images/trnc/tr-nonsmooth-figure7.jpg
    alt: "Objective Descent with TR-PG"
  - url: assets/images/trnc/tr-nonsmooth-figure8.jpg
    image_path: assets/images/trnc/tr-nonsmooth-figure8.jpg
    alt: "Data fit with R2"
  - url: assets/images/trnc/tr-nonsmooth-figure9.jpg
    image_path: assets/images/trnc/tr-nonsmooth-figure9.jpg
    alt: "Objective Descent with R2"

---



This was a project that I developed with Aleksander Aravkin and Dominique Orban.
We attempt to tackle a very generic set of regularized problems *f+h*, where both may be nonconvex, and *h* may be nonsmooth.
It is currently under review for SIAM Optimization, and ArXiv copy can be found [here](https://arxiv.org/abs/2103.15993). I presented at the DOE CSGF Program Review and [SIOPT]({{ rjbaraldi.github.io }}/assets/websitefiles/siopt_pres.jpg) virtually in July 2021.

We develop a trust-region method for minimizing the sum of a smooth term *f* and a nonsmooth term *h*), both of which can be nonconvex. Each iteration of our method minimizes a possibly nonconvex model of *f+h* in a trust region. The model coincides with *f+h*  in value and subdifferential at the center. We establish global convergence to a first-order stationary point when *f* satisfies a smoothness condition that holds, in particular, when it has Lipschitz-continuous gradient, and *h* is proper and lower semi-continuous. The model of *h* is required to be proper, lower-semi-continuous and prox-bounded. Under these weak assumptions, we establish a worst-case *O(1/ϵ^2)* iteration complexity bound that matches the best known complexity bound of standard trust-region methods for smooth optimization. We detail a special instance, named TR-PG, in which we use a limited-memory quasi-Newton model of *f* and compute a step with the proximal gradient method, resulting in a practical proximal quasi-Newton method. We establish similar convergence properties and complexity bound for a quadratic regularization variant, named R2, and provide an interpretation as a proximal gradient method with adaptive step size for nonconvex problems. R2 may also be used to compute steps inside the trust-region method, resulting in an implementation named TR-R2. We describe our Julia implementations and report numerical results on inverse problems from sparse optimization and signal processing. Both TR-PG and TR-R2 exhibit promising performance and compare favorably with two linesearch proximal quasi-Newton methods based on convex models.

{% include gallery caption="Probably the most important final results, where we enforce an l0-norm constraint on a system of ODEs." %}