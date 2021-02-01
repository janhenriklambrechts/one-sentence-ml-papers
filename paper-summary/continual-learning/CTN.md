| Contextual Transformation Networks for Online Continual Learning | Quang Pham et al. | Online Continual Learning method to model task-specific features for fixed architecture methods | [Summary](./paper-summary/continual-learning/CTN.md) | 25/01/2021 | [Paper](https://openreview.net/pdf?id=zx_uX-BO7CH)| ICLR 2021 | 

### Abstract
- 1) Fixed arch methods for continual learning cannot learn task-specific features 2) dynamic architectures have separate networks for each task but are expensive to train and not scalable in practice (especially in online setting)
- CTN efficiently models task-specific features

### Introduction
- The hard part about online-learning is balancing knowledge transfer and catastrophic forgetting
- Therefore sequential tasks are a good benchmark
- 1) Use a fixed feature extractor: very prone to catastrophic forgetting 2) Dynamic inference: very prone to unbounded growth of parameters + Subnetworks design requires extensive resource usage making it not very practical
- Popular result in multi-task learning: each tasks are centered around a common vector -> Can we transform the common vector into a task-specific vector? 
- One single linear layer to map the base features to task-specific features, train a controller on these tasks

### Related Work
- Continual Learning: 1) Regularization methods 2) Episodic Memory based methods 3) dynamic architecture methods
- 1) Regularization-based methods: penalize the changes of important parameters to previous tasks using a variant of knowledge distillation or quadratic constraints
- 2) Episodic Memories: Store small amount of data from previous tasks and interleave it with data from the current task (can also be thought of as a constraint)
- 3) Dynamic Archtitectures approaches address catastrophic forgetting by having subnetworks or growing the structure over time, often need lots of resources for online learning

### Experiments
- Uses extremely small batch sizes (10) to keep total RAM usage low
- Convincingly beats earlier approaches

### Reviewer Comments
- Novelty is somewhat limited but results are just really, really good
