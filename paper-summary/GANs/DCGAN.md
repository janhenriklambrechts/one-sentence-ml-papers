# DCGAN
| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Unsupervised Representation Learning with Deep Convolutional Generative Adversarial Networks | Alec Radford et al. | When we add some architectural constraints to GANs they provide good image representation that can be used for supervised learning. | ./paper-summary/GANs/DCGAN.md | 07/11/2016 | [Paper](https://arxiv.org/pdf/1511.06434.pdf) | ICLR 2016 |  

## Abstract
- **Goal**: Bridge the gap between success of CNNs for supervised learning and unsupervised learning. 
- **How**: Introduce some architectural constraints to GANs, show that trained generators can be effectively used as pretrained backbones for supervised learning tasks.

## Introduction
- The fact that GANs dont have a heuristic cost function makes them attractive for general feature learning
- However, GANs have been known to produce nonsensical output and be difficult to train.
- Therefore, we propose some constraints on architecture of Convolutional GANs, making them stable to train in most settings.
- Additionally, they show that generators have interesting vector arithetic properties that allow for easy manipulation of many semantic qualities of generated samples. 

## Related Work
- Other methods of unsupervised learning include: Clustering, Auto-Encoders, Ladder structures, deep belief networks
- Generative models can be broken down into *parametric* (variational sampling, iterative forward diffusion, RNN, Deconv) and *non-parametric* (database matching)

## Approach & Model Arch
- Three key properties for stable training:
1. Replace pooling functions by strided convolutions (Generator & Discriminator)
2. Eliminating fully connected layers
3. Batch Normalization Training (especially critical for Deep Generators; makes sure samples do not collapse to a single point)
4. (use ReLU in Generator, Leaky ReLU in Discriminator)

## Empirical Validation
- Performs worse on CIFAR-10 than previous approaches but strikingly performs better on SVHN with the same architecture in supervised manner.

## Investigating and Visualizing the Internals of the Networks
- Choose 9 random points in the latent space and interpolate bteween them, this actually works! Slow transformation from one scene to the other.
- Take sample from left looking face and right looking face, interpolate in between them works as well!

