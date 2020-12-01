# Adaptive Discriminator Augmentation
| Training Generative Adversarial Networks with Limited Data | Tero Karras et al. | Proposes a adaptive discriminator augmentation mechanism that significantly stabilizes limited data regimes | [Summary](./paper-summary/GANs/AdaptiveDiscriminatorAugmentation.md) | 01/12/2020 | [Paper](https://papers.nips.cc/paper/2020/file/8d30aa96e72440759f74bd2306c1fa3d-Paper.pdf) | NeurIPS 2020 | 

## Abstract
- Problem with limited training data is discriminator overfitting
- Proposed ADA leads to stabilization of the training divergion that this overfitting induces - reducing needed images to a few thousa

## Introduction
- GANs take about 10^5 to 10^6 training images nowadays limiting their use in a lot of application scenarios
- Discriminator overfitting is the issue with limited training data, data augmentation makes for leaking these augmentations in the generated images

## Overfitting in GANs
- By definition any augmentation that is applied to the training dataset will get leaked to the generated set
- This paper: Never let the discriminator see the actual generated images but only the data augmented generated images and compare these to the data augmented training images.
- How can a generator learn this way? -> Training implicitly undoes corruptions and finds the correct distribution as long as the corruption process is represented by an invertible  transformation of probability distributions 
- What does it mean for a transformation to be invertible? -> They allow for conclusions about the equality or inequality of the underlying sets to be drawn by only oberving the augmented sets
- As long as we do data augmentation with p < 0.8, data leaking does not occur in practice!
- Not all data augmentation is useful, pixel blitting, geometric and color transforms are the most useful; best p value is inconsistent across different datasets -> Costly grid search ! -> Lets make this adaptive instead

## Adaptive Discrimination Augmentation
- Avoid manual tuning of p, instead control it dynamically based on degree of overfitting
- We adjust p adaptively every four minibatches based on some overfitting heuristics -> This adjusts the p throughout the training process
