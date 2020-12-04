## Fast AutoAugment
| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Fast AutoAugment | Sungbin Lim et al. | Density matching can speed up AutoAugment search time while achieving comparable performance  | [Summary](./paper-summary/data-augmentation/FastAutoAugment.md) | 25/05/2019 | [Paper](https://arxiv.org/pdf/1905.00397v2.pdf) | NeurIPS 2019 | 


## Abstract 
- AutoAugment takes thousands of GPU hours for small datasets
- Fast AutoAugment uses density matching to speed this up incredibly


## Introduction
- Fast AutoAugment does not take any repeated training of child models, searching for augmentation policies that maximize the match between distribution of augmentend split and distribution of another, unaugmented split.

## Related Work
- Previous DA approaches 1) Hand-designed 2) Generative Models 3) Optimal combinations of predefined transformations

## Fast AutoAugment
- Search space is O operations with probability p and magnitude \lambda
- S is the set of subpolicies with subpolicy \tau \in S (that consists of N\_t consecutive operations with probability p)
- For exploration split the **train dataset** in K folds, each k fold consists of two subsets D\_M and D\_A. 
- We train the model parameter \theta on each D\_M in parallel. After training \theta, the algorithm evaluates  B bundles of augmentation policies of D\_A without training \theta. The top-N policies obtained from each K-fold are appended to the augmentation list T\ast.
- We want our data augmentation to bridge the train/validation gap, as such intuitively we can select the best data augmentation as one that that matches the density of D\_train and D\_valid
- How to select the the top policy? -> compare the categorical cross-entropy loss of the Augmented validation images, use this to train a Bayesian method that samples optimal augmentation
