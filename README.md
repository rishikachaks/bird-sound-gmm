# Bird Sound Gaussian Mixture Model Project
DSA Final Project - Dakota &amp; Rishika

### Introduction

A Gaussian Mixture Model (GMM) is a probabilistic model that assumes data points are generated from a mixture of several Gaussian (normal) distributions with unknown parameters. A Gaussian Mixture Model assumes that the data is generated from a mixture of K Gaussian distributions, each representing a cluster. Every Gaussian has its own mean μk​, covariance Σk​ and mixing weight πk​.

Below is the total likelihood of observing xn under all Gaussians:

![GMM Probability Equation](/gmm_equation.png)

****where:****

- zn​ is a latent variable indicating which Gaussian the point belongs to.
- πk​ is the mixing probability of the k-th Gaussian.
- N(xn ∣ μk, Σk) is the Gaussian distribution with mean μk​ and covariance Σk.

This represents how well the mixture as a whole explains the data point.

GMMs are trained using the Expectation-Maximization Algorithm, an iterative algorithm used to assign unknown parameters in probabilistic models. The algorithm works in two steps:

****E-step (Expectation)****: Compute the responsibility of each cluster for every data point using current parameter values.

****M-step (Maximization):**** Update
- Means μk
- Covariances Σk
- Mixing coefficients πk

The process continues until the model's log-likelihood stabilizes.

In GMM, each cluster is a Gaussian defined by:

- ****Mean (μ):**** Center of the cluster.
- ****Covariance (Σ):**** Controls the shape, orientation and spread of the cluster.

The covariance matrix of a Gaussian distribution determines the directions and lengths of the axes of its density contours, all of which are ellipsoids.

These four types of mixture models can be illustrated in full generality using the two-dimensional case. In each of these contour plots of the mixture density, two components are located at (0,0) and (4,5) with weights 3/5 and 2/5 respectively. The different weights will cause the _sets_ of contours to look slightly different even when the covariance matrices are the same, but the overall shapes of individual contours will still be similar for identical matrices.

![Covariance Models for GMM](/gmm_covariance.png)

- **Full** means the components may independently adopt any position and shape.
- **Tied** means they have the same shape, but that shape may be anything.
- **Diagonal** means the contour axes are oriented along the coordinate axes, but otherwise the eccentricities may vary between components.
- **Spherical** is a "diagonal" situation with circular contours (spherical in higher dimensions, whence the name).

### Gaussian Mixture Model vs. K-means Clustering

While K-means clustering forms groups by minimizing the distance between data points and a central point, mixture models such as Gaussian Mixture Models (GMMs) define clusters using probability distributions that can take on elliptical shapes based on their parameters. Because of this flexibility, GMMs are better suited for datasets that are not easily separable and require more complex cluster boundaries. They also support soft clustering, assigning each point a probability of belonging to multiple clusters rather than a single hard assignment.

In contrast, K-means is a much simpler and more computationally efficient method. It performs well on low-dimensional data with clearly defined, spherical clusters. However, K-means is highly sensitive to outliers and performs poorly when clusters are non-spherical or vary in size and density.

![KNN vs GMM](/knn_vs_gmm.png)

Since we are working with MFCC spectrograms for bird sounds, the feature space contains over 30 coefficients, making the data high-dimensional. In this setting, K-means becomes less effective due to its reliance on simple, spherical cluster boundaries. Additionally, because we want a model that can accommodate varying cluster shapes for more accurate predictions, a Gaussian Mixture Model is better suited for this task.

### Where GMM is Useful

Gaussian Mixture Models (GMMs) are used widely across industries as they can uncover underlying patterns in data through clustering, detecting anomalies, segmenting images into meaningful patterns for applications such as medical imaging, and perform density estimation to model complex probability distributions for generative tasks.

GMMs offer several advantages. They can represent flexible, non-spherical, and overlapping cluster shapes, and they produce soft, probabilistic cluster memberships rather than hard labels. They also handle missing data effectively and rely on interpretable parameters—each Gaussian component has a clear mean, covariance, and weight that together describe its contribution to the mixture.

#### Use-Cases

- Marketing, medicine, genetics (clustering)
- Fraud detection, medical error detection (anomaly detection)
- Medical and remote sensing imagery (image segmentation)
- Generative modeling (density estimation)







