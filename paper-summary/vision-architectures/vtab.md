| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| A Large-scale Study of Representation Learning with the Visual Task Adaptation Benchmark | Xiaohua Zhai et al. | A unified evaluation for general visual representations by combining a bunch of vision tasks into one | [Summary](./paper-summary/vision-architectures/vtab.md) | 21/02/2020 | [Paper](https://arxiv.org/pdf/1910.04867.pdf)| ArXiv | 

### Abstract
- Representation learning has come a long way but we do not reallyhave a standardized benchmark to get some score for representations. We basically only have ImageNet in vision
- Popular protocols are often very constrained (linear classification), limited in diversity (ImageNet, CIFAR, Pascal-VOC) or only weakly correlated to representation quality (ELBO, reconstruction error).
- VTAB idea: Good representations are those that adapt well to **diverse**, **unseen** tasks with **few examples**.

### Introduction 
- Improving sample efficiency has been approached from many angles including few-shot learning, transfer learning, domain adaptation an representation learning.
- Representation learning can happen supervised, unsupervised etc. and all of these have their separate benchmarks - NLP on the other hand has GLUE as a proper benchmark
- Good benchmarks have 1. minimal constraints to creativity, 2. focus on practical considerations, 3. challenging tasks
- This paper defines a good representation as one that that can be used to solve many **previously unseen** tasks with the **fewest possible labels**. -> VTAB inclused medical imaging, scene understanding and sensorimotor control tasks
 - **Key contributions:** 
 1. Supervised ImageNet pretraining yields excellent representations for natural image classification tasks and specialized tasks (medical imaging f.e.) 
 2. Self-supervised learning is less effective than supervised overall but improves structured understanding
 3. Combining supervision and self-supervision is effective
 4. Discriminative representations appear more effective than generative
 5. GANs do better on data similar to their pretraining source but worse on other tasks
 6. Evaluation using a linear classifier leads to poorer transfer and different conclusions.

### Benchmark
- Object detection, scene classification, pathology detection, counting, localization and 3D Geometry
- 3 main groups: **Natural**: abstract, fine-grained and normal; **Specialized**: medical and remote sensing; **Structured**: object counting, 3d depth prediction, etc.

### Results
- All self-supervised representations outperform from-scratch training
- Self-supervision can almost (but not quite) replace 90% of ImageNet labels (gap between supervised trainin on 10% of labels + self-supervised training and 100% labels is small). 
- ImageNet pretrained representation are indeed effective for natural tasks and highly-specialized tasks - yet for structured understanding supervised representations can be poorer than non-supervised ones.
