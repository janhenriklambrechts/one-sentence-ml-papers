| Overcoming catastrophic forgetting in neural networks | James Kirkpatrick et al. | Slowing down learning on weights important for earlier tasks overcomes catastrophic forgetting | [Summary](./paper-summary/continual-learning/OvercomingForgetting.md) | 25/01/2017 | [Paper](https://arxiv.org/pdf/1612.00796.pdf)| Arxiv | 

### Introduction
- Environments change, so an AGI will need to continuously learn
- MTL does not suffer from catastrophic forgetting as data is always available
- Episodic replay is not really optimal, humans do not do this either

### Elastic Weight Consolidation
- Given the overparametrization of NNs, there should exist a set of weights that solves both A and B
- || ||2 constraint on weights refers to elastic, differing much revceives a very large punishment
- This elastic constraint should not be as big everywhere: use a Fischer information matrix to determine this elastic constraint
- Optimize || \theta_new - theta_old ||2 jointly with training objective


### Experiments
- Impressively, this works reasonably for DRL as well! 
