# Awesome Deep Learning Papers 📰

Feel free to browse my collection of summaries of various Deep Learning Topics.
Main difference with other repos that have summaries of DL papers is that my README includes
**one sentence summaries** of every paper discussed. I have found this incredibly helpful
to remember a paper or assess if the paper is worth reading (again).

Ordered by topic 🗂️:
 
- GANs 🖼️
- Style Transfer 🎨
- Data Augmentation ✨
- Robustness 🛡️
- Deploying ML ☁️ 
- Continual Learning / Tranfer Learning ♻️
- Dynamic Inference 🐙
- Vision Architectures 🔍
- Deep Reinforcement Learning 🤖
## GANs 🖼️

| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Training Generative Adversarial Networks with Limited Data | Tero Karras et al. | Proposes a adaptive discriminator augmentation mechanism that significantly stabilizes limited data regimes | [Summary](./paper-summary/GANs/AdaptiveDiscriminatorAugmentation.md) | 01/12/2020 | [Paper](https://papers.nips.cc/paper/2020/file/8d30aa96e72440759f74bd2306c1fa3d-Paper.pdf) | NeurIPS 2020 | 
| Few-short Image Generation with Elastic Weight Consolidation | Yijun Li et al. | Proposes an algorithm that generates high-quality samples of different target domains | [Summary](./paper-summary/GANs/ElasticWeightConsolidation.md) | 01/12/2020 | [Paper](https://papers.nips.cc/paper/2020/file/b6d767d2f8ed5d21a44b0e5886680cb9-Paper.pdf) | NeurIPS 2020 | 
| A Style-Based Generator Architecture for Generative Adversarial Networks | Tero Karras et al. | Introduces a novel generator architecture based on style transfer, leading to better quality and control of generation | [Summary](./paper-summary/GANs/StyleGAN.md) | 07/11/2016 | [Paper](https://arxiv.org/pdf/1812.04948.pdf) | CVPR 2019 | 
| Unsupervised Representation Learning with Deep Convolutional Generative Adversarial Networks | Alec Radford et al. | When we add some architectural constraints to GANs they provide good image representation that can be used for supervised learning. | [Summary](./paper-summary/GANs/DCGAN.md) | 07/11/2016 | [Paper](https://arxiv.org/pdf/1511.06434.pdf) | ICLR 2016 |  

## Style Transfer 🎨

| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Adaptive Style Transfer in Real-Time with Adaptive Instance Normalization | Xun Huang et al. | Introduces an AdaIN layer that allows for arbitraty style transfer in real-time | [Summary](./paper-summary/style-transfer/AdaIN.md) | 30/07/2017 | [Paper](https://arxiv.org/pdf/1703.06868.pdf) | ICCV 2017 | 
| Image Style Transfer Using Convolutional Neural Networks | Leon Gatys et al. | Introduces an algorithm that can separate and  recombine style of an image and image content  | [Summary](./paper-summary/style-transfer/ImageStyleTransfer.md) | 07/11/2016 | [Paper](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf) | CVPR 2016 | 


## Data Augmentation ✨

| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Fast AutoAugment | Sungbin Lim et al. | Density matching can speed up AutoAugment search time while achieving comparable performance  | [Summary](./paper-summary/data-augmentation/FastAutoAugment.md) | 25/05/2019 | [Paper](https://arxiv.org/pdf/1905.00397v2.pdf) | NeurIPS 2019 | 
| RandAugment: Practical Automated Data Augmentation with a Reduced Search Space | Ekin D. Cubuk, Barret Zoph et al. | Searching for a single distortion magnitude can do as well or improve previous automated augmentation strategies  | [Summary](./paper-summary/data-augmentation/RandAugment.md) | 11/04/2019 | [Paper](https://proceedings.neurips.cc/paper/2020/file/d85b63ef0ccb114d0a3bb7b7d808028f-Paper.pdf) | NeurIPS 2020 | 
| AutoAugment: Learning Augmentation Strategies from Data | Ekin D. Cubuk et al. | Meta-learning data augmentation for new SOTA on classification | [Summary](./paper-summary/data-augmentation/AutoAugment.md) | 11/04/2019 | [Paper](https://arxiv.org/pdf/1805.09501.pdf) | ArXiv | 

## Robustness 🛡️

| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Improving Robustness Without Sacrificing Accuracy with Patch Gaussian Augmentation | Raphel Gontijo Lopes et al. | Combining Cutout and Gaussian noise in a single data augmentation scheme improves robustness while not incurring accuracy drop.  | [Summary](./paper-summary/robustness/PatchGaussian.md) | 06/06/2019 | [Paper](https://arxiv.org/pdf/1906.02611.pdf) | ICML 2019 Workshop | 
| Benchmarking Neural Network Robustness to Common Corruptions and Perturbations | Dan Hendrycks et al. | Establishes a benchmark for image classifier robustness to common corruptions.  | [Summary](./paper-summary/robustness/BenchmarkingRobustness.md) | 25/05/2019 | [Paper](https://arxiv.org/pdf/1903.12261.pdf) | ICLR 2019 | 

## Deploying ML ☁️
 
| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Machine Learning: The High-Interest Credit Card of Technical Debt | D. Sculley et al. | Highlights risk factors and design patterns to be avoided in building ML systems  | [Summary](./paper-summary/deploying-ml/MLTechnicalDebt.md) | 18/11/2014 | [Paper](https://storage.googleapis.com/pub-tools-public-publication-data/pdf/43146.pdf) | NeurIPS 2014 Workshop | 
| Challenges in Deploying ML: A Survey of Case Studies | Andrei Paleyes et al. | A survey of deploying ML solutions for different use cases  | [Summary](./paper-summary/deploying-ml/ChallengesInDeployingML.md) | 18/11/2020 | [Paper](https://arxiv.org/pdf/2011.09926.pdf) | NeurIPS 2020 Workshop | 

## Continual Learning / Transfer Learning ♻️

| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Mutual Alignment Transfer Learning | Markus Wulfmeister et al. | Demonstrates that auxilary rewards can bridge the gap between simulation and real-world robots | [Summary](./paper-summary/continual-learning/MATL.md) | 26/09/2017 | [Paper](https://arxiv.org/pdf/1707.07907.pdf)| CoRL 2017 | 
| NetTailor: Tuning the Architecture, Not just the Weights | Pedro Morgado et al. | Tuning the architecture, not just the weights | [Summary](./paper-summary/continual-learning/NetTailor.md) | 29/06/2019 | [Paper](http://www.svcl.ucsd.edu/~morgado/nettailor/nettailor.pdf)| CVPR 2019 | 
| Progressive Neural Networks | Andrei A. Rusu, Neil C. Rabinowitz et al. | Grow lateral connections to features learned by frozen weights | [Summary](./paper-summary/continual-learning/ProgressiveNetworks.md) | 01/01/2016 | [Paper](https://arxiv.org/pdf/1606.04671.pdf) | Arxiv | 
| Compacting, Picking and Growing for Unforgetting Continual Learning | Steven C.Y. Hung et al. | Leveraging Pruning and Progressive Networks Expansion can deal with catastrophic forgetting while retaining model compactness. | [Summary](./paper-summary/continual-learning/CompactingPickingGrowing.md) | 18/06/2019 | [Paper](https://proceedings.neurips.cc/paper/2019/file/3b220b436e5f3d917a1e649a0dc0281c-Paper.pdf) | NeurIPS 2019 | 
| PathNet: Evolution Channels Gradient Descent in Super Neural Networks | Chrisantha Fernando et al. | Genetic Algorithm that replicates and mutates earlier paths for faster transfer learning | [Summary](./paper-summary/deep-rl/pathnet.md) | 19/11/2019 | [Paper](https://arxiv.org/pdf/1701.08734.pdf)| ArXiv | 
| Contextual Transformation Networks for Online Continual Learning | Quang Pham et al. | Online Continual Learning method to model task-specific features for fixed architecture methods | [Summary](./paper-summary/continual-learning/CTN.md) | 25/01/2021 | [Paper](https://openreview.net/pdf?id=zx_uX-BO7CH)| ICLR 2021 | 
| Overcoming catastrophic forgetting in neural networks | James Kirkpatrick et al. | Slowing down learning on weights important for earlier tasks overcomes catastrophic forgetting | [Summary](./paper-summary/continual-learning/OvercomingForgetting.md) | 25/01/2017 | [Paper](https://arxiv.org/pdf/1612.00796.pdf)| Arxiv | 
| Continual Learning with Hypernetworks | Johannes von Oswald et al. | To overcome gigantic network growth for new tasks, we build task-conditioned hypernetworks | [Summary](./paper-summary/continual-learning/CLwithHN.md) | 12/02/2020 | [Paper](https://arxiv.org/pdf/1906.00695.pdf)| ICLR 2020 | 

## Dynamic Inference 🐙

| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Universally Slimmable Networks and Improved Training Techniques | Jiahui Yu et al. | Makes Slimmable networks able to run at arbitrary widths | [Summary](./paper-summary/dynamic-inference/UniversalSlimmable.md) | [Paper](ihttps://arxiv.org/abs/1903.05134) | ICCV 2019 |
| Anytime Inference with Distilled Hierarchical Neural Ensembles | Andria Ruiz et al. | Dynamically allocating multiple models in the ensemble and training them with distillation provides good dynamic inference | [Summary](./paper-summary/dynamic-inference/HNE.md) | 14/12/2020 | [Paper](https://arxiv.org/pdf/2003.01474.pdf)| AAAI 2020 | 

## Vision Architectures 🔍

| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| RepVGG: Making VGG-style ConvNets Great Again | Xiaohan Ding et al. | Decoupling of training-time and inference-time architecture can lead to inference speedup of 83% over ResNet-50 while reaching 80+% on ImageNet | [Summary](./paper-summary/vision-architectures/RepVGG.md) | 11/01/2021 | [Paper](https://arxiv.org/pdf/2101.03697v1.pdf)| ArXiv | 

## Deep Reinforcement Learning 🤖

| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model  | Tree search and learned model can master unknown and complex environments | [Summary](./paper-summary/deep-rl/muzero.md) | 19/11/2019 | [Paper](https://arxiv.org/abs/1911.08265)| ArXiv | 


