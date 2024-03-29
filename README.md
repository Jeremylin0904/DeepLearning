# Deep Learning Practical Assignments

This repository contains practical assignments for the KTH computer science course DD2412/FDD3412 HT23 Deep Learning, Advanced Course. The assignments cover two main topics:

1. **Interpreting and Understanding Deep Networks**:
    - [ExplanationMethods.ipynb](ExplanationMethods.ipynb)
    - [ModelBias.ipynb](ModelBias.ipynb)
    - [Memorization_practical_PartI.ipynb](Memorization_practical_PartI.ipynb)
    - [Memorization_practical_PartII.ipynb](Memorization_practical_PartII.ipynb)

2. **Under-supervised Deep Learning**:
    - [SimCLR.ipynb](SimCLR.ipynb)
    - [FixMatch.ipynb](FixMatch.ipynb)

## Interpreting and Understanding Deep Networks

### [ExplanationMethods.ipynb](ExplanationMethods.ipynb)
Deep learning models are becoming better and better at making predictions. As researchers, regulators, and users, we are also interested in asking additional questions. Namely, we would like to explain a decision in terms of the input. Where in an image is a model focusing on? What cues is the prediction based on? Does it match our expectation? Can the model be trusted?

In this practical, we will explore popular methods for explaining decisions made by image classifiers:

- Simple occlusion
- Gradient norm
- Gradient x input
- GradCAM
- Integrated gradients

With a working implementation of each method, we will compare explanations qualitatively on a few sample images.

Furthermore, we will evaluate the correctness of each method quantitatively using the deletion score.

### [ModelBias.ipynb](ModelBias.ipynb)
In this second part, we will use explanation methods to identify a faulty classifier that was trained on biased data. Specifically, each image contains an artifact whose color is related to the class of the image. A model trained with such images will likely learn to disregard the image content entirely and only focus on the artifact to make a prediction. You will use one of the explanation methods implemented in the first part to spot the issue.

Although in this example the bias was introduced artificially, it's not uncommon to see this kind of telling artifacts in real-world datasets. For example, in a dataset of X-ray scans, one might find identifiers along the edge or marks left by doctors that could hinder the learning of a model.

### [Memorization_practical_PartI.ipynb](Memorization_practical_PartI.ipynb)
The mechanisms governing hypothesis selection in deep learning are currently not fully understood.

According to traditional machine learning, a large hypothesis class (e.g., corresponding to overparameterized models) can fit several datasets of increasing complexity, which practically leads to overfitting training data and noise within. However, in practice, deep networks are able to achieve state-of-the-art performance on several benchmarks, thereby learning generalizing solutions. At the same time, weakly regularized networks can fit arbitrary labellings of the dataset, showing that stochastic optimization, coupled with overparameterization, can in principle memorize a dataset.

A paramount question is thus what factors govern learning vs. memorization, and why large, overparameterized networks don't simply memorize the training dataset?

In this assignment, we are going to explore established phenomena that set deep networks aside from traditional machine learning so that you familiarize yourself with some fundamental open questions in deep learning.

### [Memorization_practical_PartII.ipynb](Memorization_practical_PartII.ipynb)
In this part of the assignment, we will focus on reproducing an intriguing phenomenon of deep networks, known as layer criticality, first reported by Zhang et al. (2019).

The authors explore whether every layer of a discriminative deep network contributes equally to the performance of the learned classifier. Strikingly, it was observed that for some layers, the value of the corresponding parameters can be reset to initialization without severely affecting the performance of the resulting model.

In practice, starting from a trained network and the initialization checkpoint that was used for training, you will reproduce the main result of Zhang et al., for a pre-trained ResNet18 which was produced using the code from Part I of this assignment.

## Under-supervised Deep Learning

### [SimCLR.ipynb](SimCLR.ipynb)
SimCLR

In this practical exercise, you are going to implement the famous SimCLR [1] algorithm for self-supervised learning. While not that old, it is often seen as the 'classic' approach to contrastive learning and it is still used as a baseline against which newer approaches are compared. Most of the more recent algorithms are just slight alterations of this approach, so knowing how it works will pay off in the future. Due to the growing amounts of data, self-supervised learning is likely to become more and more relevant in the future.

Or as Yan LeCun and Ishan Misra put it: SSL may be helpful to unlock the dark matter of intelligence.

### [FixMatch.ipynb](FixMatch.ipynb)
FixMatch: Simplifying Semi-Supervised Learning with Consistency and Confidence

In this practical, we are going to focus on semi-supervised learning, which refers to the situation of using unlabeled data to enhance the performance of models on a classification task. The method we are focusing on is called FixMatch [1], which has simplified the process of semi-supervised learning compared to the recent state-of-the-art methods.
