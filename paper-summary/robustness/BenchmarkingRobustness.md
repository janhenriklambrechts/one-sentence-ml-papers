## Benchmarking Robustness

| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Benchmarking Neural Network Robustness to Common Corruptions and Perturbations | Dan Hendrycks et al. | Establishes a benchmark for image classifier robustness to common corruptions.  | [Summary](./paper-summary/robustness/BenchmarkingRobustness.md) | 25/05/2019 | [Paper](https://arxiv.org/pdf/1903.12261.pdf) | ICLR 2019 | 

## Abstract 
- Introducing an ImageNet Dataset with Corruptions (ImageNet-C) and Perturbations (ImageNet-P)
- All classifiers are relatively as (non-) robust versus corruptions
- Bypassed adversarial defense can still be robust versus pertubations

## Introduction
- Robustness is critical for deep learning in safety-critical applications
- 75 common corruptions should serve as a rigorous benchmark and reduce cherrypicking in robustness publications
- Non-adversarially generated perturbations can succesfully attack a lot of network
- Adversarial robustness and common corruptions are at least somewhat tied as methods that can do well on the first seem to do well on the second benchmark as well

## Corruptions, Perturbations and Adversarial Perturbations
- Often real-world vision systems have to deal with low quality or corrupted inputs, as such they should be resistant to those outputs- Corruption Robustness: Classifiers average case performance on corruptions C
- Adversarial Robustness: Worst-case performance on small additive classifier tailored perturbations
- Perturbation Robustness: Average case performance on small classifier-agnostic perturbations

## ImageNet-C and ImageNet-P
- Networks should never be trained on these datasets
- Common corruptions: corruptions that occur with low light, bit errors etc.
- CE= Corruption Error / AlexNet Corruption Error -> Notice that good classifiers that are not robust can get way better CE than bad calssifiers that are very robust
- Relative CE: Difference in Error corrupt - clean / AlexNet difference in corrupt - clean

## Experiments
- Larger feature aggregating networks achieve robustness gains that substantially outpace their accuracy gains
