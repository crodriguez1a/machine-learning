# Machine Learning Engineer Nanodegree
## Capstone Proposal
Carlos Rodriguez
June 22nd, 2019

## Proposal

### Domain Background

Today, unearthing a rare audio archive can be as simple as accessing a popular video sharing platform from a device that fits in your pocket. Alternatively, the fidelity of these aging recordings seemingly remains frozen in the time in which they were captured. Often, important (and even critical) portions of these recordings are unintelligible and are lost to history.

The goal of this capstone is to experiment with using [imputation](https://en.wikipedia.org/wiki/Imputation_(statistics)) algorithms to restore portions of audio content that were recorded poorly or were lost due to degradation.

### Problem Statement

Restoring or repairing audio is challenging for many reasons. There are some inherent challenges with working audio including but not limited to:

- Isolation of the desired source signal
- Identifying and removing noise
- Partial or complete loss of data during recording or due to degradation

Restoring lost audio data is particularly problematic because the audio is generally not missing from the signal, but unintelligible for the listener. This solution would treat unintelligible audio as anomalous and explicitly encode some data points as missing data (null values). An imputation algorithm would then replace the missing data a plausible replacement similar to its neighbors.

### Datasets and Inputs

The solution will be applied to two crude recordings that have distinguishable audio loss. Additionally, each selection has significant background noise, distortion, and some crosstalk. The content in the audio is of orations that were originally recorded in 1963 and ~1985 respectively.  

In both cases, the audio was extracted from YouTube videos using a tool that converts video to an audio-only format. For each, only small distinct sample will be used as an input.

*Speech given by James Baldwin*
  - ["Free and Brave" a speech by James Baldwin 1963](https://www.youtube.com/watch?v=EMYgOfcgMaI)

*Interview given by Hector Lavoe*
  - [HECTOR LAVOE - AUDIO RAREZA 2.wmv](https://www.youtube.com/watch?v=ICvmLoBPX4o&t=40s)

The goal of using two inputs is to validate that the technique can work generally across audio signals with similar characteristics.


### Solution Statement

This solution treats unintelligible audio as anomalous and explicitly encodes the data point as missing data (null value). An imputation algorithm will then replace the missing data point inserting a plausible value that is similar to its neighbors.

Noise and unwanted signal sources are cleaned as part of pre-processing. Any desired source audio that audibly diminished during pre-processing is also replaced.

### Benchmark Model

As a benchmark, the outputs will be compared to a high-fidelity digital recording. The benchmark, when analyzed, should not present any noise or anomalies which is ultimately the goal of the solution.   

### Evaluation Metrics

To evaluate, the solution will measure the mean Silhouette Coefficient (silhouette score). The output data should reflect an optimal value for `n_clusters` that is relatively small.  Since a silhouette analysis can be ambivalent in deciding between 2 and 4 clusters, the solution should also evaluate the size of the individual clusters.

Larger sized clusters should represent the desired source audio, while smaller clusters should represent naturally occurring noise and/or other less significant source audio.

### Project Design
[//]: # (_(approx. 1 page)_)



In this final section, summarize a theoretical workflow for approaching a solution given the problem. Provide thorough discussion for what strategies you may consider employing, what analysis of the data might be required before being used, or which algorithms will be considered for your implementation. The workflow and discussion that you provide should align with the qualities of the previous sections. Additionally, you are encouraged to include small visualizations, pseudocode, or diagrams to aid in describing the project design, but it is not required. The discussion should clearly outline your intended workflow of the capstone project.


**Sources**

- https://scikit-learn.org/stable/auto_examples/cluster/plot_kmeans_silhouette_analysis.html

- https://towardsdatascience.com/the-use-of-knn-for-missing-values-cf33d935c637

- https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4959387/
-----------

**Before submitting your proposal, ask yourself. . .**

- Does the proposal you have written follow a well-organized structure similar to that of the project template?
- Is each section (particularly **Solution Statement** and **Project Design**) written in a clear, concise and specific fashion? Are there any ambiguous terms or phrases that need clarification?
- Would the intended audience of your project be able to understand your proposal?
- Have you properly proofread your proposal to assure there are minimal grammatical and spelling mistakes?
- Are all the resources used for this project correctly cited and referenced?
