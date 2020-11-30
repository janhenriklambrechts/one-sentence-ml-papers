# StyleGAN

| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| A Style-Based Generator Architecture for Generative Adversarial Networks | Tero Karras et al. | Introduces a novel generator architecture based on style transfer, leading to better quality and control of generation | [Summary](./paper-summary/GANs/StyleGAN.md) | 07/11/2016 | [Paper](https://arxiv.org/pdf/1812.04948.pdf) | CVPR 2019 | 


## Abstract 
- New generator that borrows from style transfer literature. 
- Automatically learns high-level attributes (pose, identity, ...) and allows for fine-grained control.
- Allows for stochastic variation (freckles, hair)


## Introduction
- Quality of images produced by GANs is getting better, properties of latent space interpolation is poorly understood, however. 
- Re-design the generator to "fuse in" style at each conv layer, allowing for fine-grained controll of every "fuse"
- Add stochastic noise that can model hairs, freckles etc. 
- We use an intermediate latent space instead of an input latent space, this allows for disentaglement from latent space and training data probability density.
- They propose two new metrics for "latent space disentanglement": perceptual path length and linear seperability

## Style-based generator
- Traditionally, use latent code in input layer -- this paper breaks from that design by omitting the input layer and **starting from a learned constant**
- AdaIN operation for "style fusion" is borrowed from style transfer. - Give stochastic noise through noise inputs to aid the model in making stochastic variation.
- While a lot of recent work has focused on making the discriminator better (self-attention, multiple discriminators etc. )

## Properties of the style-based generator
- Key idea of this paper: **localizing styles in the network** i.e. modifying a specific subset of the styles can be expected to modify certain aspects of the image.
- Style mixing: to improve localization they employ style mixing as regularization, randomly switch latent code at a certain step in the network -> Decorrelate styles

## Disentanglement studies
- Proposed metrics to quantify disentanglement train an encoder network to latent space -> This is not suited for StyleGAN giving the fixed input space. 
- Thus two new ways proposed:
1. Perceptual Path Length: non-linear changes are a sign of entanglement (f.e. suddenly a tv appearing in between endpoints)  -> a less curved latent space should result in perceptu-ally smoother transition than a highly curved latent space.
2. Linear Separability: If disentangled, we should be able to linearly separate latent space points. Train aux classifier on separating, calculate the score and sum over different attributes.
