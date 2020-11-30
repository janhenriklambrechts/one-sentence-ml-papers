# Image Style Transfer

| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Image Style Transfer Using Convolutional Neural Networks | Leon Gatys et al. | Introduces an algorithm that can separate and  recombine style of an image and image content  | [Summary](./paper-summary/style-transfer/ImageStyleTransfer.md) | 07/11/2016 | [Paper](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf) | CVPR 2016 | 


## Abstract
- Semantic content of an image in different styles has proven to be hard because we dont have methods that capture semantic information. 
- CNN representations do encode this, however, allowing us to produce new images that combine content of one photograph with style of another.

## Introduction
- Style transfer can be considered a problem of texture transfer, for texture synthesis there is a wide literature on resampling pixels of a given source texture. 
- Both texture and semantics can be encoded in a single NN, making this solvable by a single NN.

## Deep Image Representations
- **Content Representation**: By changing a random white-noise image gradually with a L2 loss between its feature representations and a target image we can get the white noise to generate the same feature representations as the target image at layer L. Later layers are style-invariant but encode content.  
- **Style Representation**: Gram matrix encodes feature correlations of multiple layers which encodes texture info but not global arrangement.- Now we have a representation of **style** and **content**, as such we can change a random white noise image with an L2 loss for both style and content

## Result
- Using content representation of earlier layers yields a sort of texture blend between source and target texture, using later ones provides proper separation
