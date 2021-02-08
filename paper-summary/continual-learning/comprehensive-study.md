| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| A Comprehensive Study of Class Incremental Learning Algorithms for Visual Tasks | Eden Belouadah et al. | Provides an evaluation framework for Incremental Learning Algos across visual tasks | [Summary](./paper-summary/continual-learning/comprehensive-study.md) | 15/12/2020 | [Paper](https://arxiv.org/pdf/2011.01844.pdf)| Neural Networks | 

### Abstract
- catastrophic forgetting = the tendency of neural networks to underfit past data when new ones are ingested. 
- Previous solutions:
1. increasing deep model capacity to accomodate new knowledge
2. fix deep model size and introduce mechanism for compromise between stability and plasticity of the model
- In general solutions in 1) get compared thoroughly but solutions in 2) do not. This piece focuses on the latter:
1. Defining six desirable properties of IL and analyze them according to these properties
2. Introduce a unified formalization of class-incremental learning problem
3. Propose a common evaluation framework across datasets, dataset size, size of memory and number of incremental states
4. investigate herding of past exemplars
5. provide experimental evidence that it is possible to obtain competitive performance without KD 
6. make an open-source repository

### Introduction
-
