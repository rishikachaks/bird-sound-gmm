# Bird Sound Gaussian Mixture Model Project
DSA Final Project - Dakota &amp; Rishika

### Introduction
While K-means clustering forms groups by minimizing the distance between data points and a central point, mixture models such as Gaussian Mixture Models (GMMs) define clusters using probability distributions that can take on elliptical shapes based on their parameters. Because of this flexibility, GMMs are better suited for datasets that are not easily separable and require more complex cluster boundaries. They also support soft clustering, assigning each point a probability of belonging to multiple clusters rather than a single hard assignment.

In contrast, K-means is a much simpler and more computationally efficient method. It performs well on low-dimensional data with clearly defined, spherical clusters. However, K-means is highly sensitive to outliers and performs poorly when clusters are non-spherical or vary in size and density.

KNN vs GMM[/knn_vs_gmm.png]

Since we are working with MFCC spectrograms for bird sounds, the feature space contains over 30 coefficients, making the data high-dimensional. In this setting, K-means becomes less effective due to its reliance on simple, spherical cluster boundaries. Additionally, because we want a model that can accommodate varying cluster shapes for more accurate predictions, a Gaussian Mixture Model is better suited for this task.




