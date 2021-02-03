| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Few-Shot Class Incremental Learning | Xiaoyu Tao et al. | Representing knowledge using a network can learn and preserve the topology of feature manifold formed by different classes | [Summary](./paper-summary/continual-learning/FCIL.md) | 24/04/2020 | [Paper](https://arxiv.org/pdf/2004.10956.pdf)| CVPR 2020 | 

### Abstract
- Few-Shot Class-incremental learning is a new but interesting problem
- Learn a network that learns the topology of the feature manifold formed by different classes. Stabilize  the topology but extend it to new-classes and grow and adapt it. 
- Improves upon earlier class-incremental methods

### Introduction
- Naive approach to FSCIL is to finetune model on new training set, this leads to catastrophic forgetting however or overfitting to new classes. 
- Most approaches use a task identity, this is however often not available in real life - so we have to optimize for a single task
- To mitigate forgetting, most CIL works use knowledge distillation to maintain outputs to old classes. 
-> Problem 1) *class-imbalance*: output logits are biased towards classes with a significant larger number of training samples. 2) *performance trade-off*: classes with low amount of samples need larger gradient steps  but this kills early class performance. 
- Brain-inspired work shows that memory topology is extremely important for humans. 
- TOpology-Preserving knowledge InCrementer (TOPIC) uses a neural gas network NG to model the topology of the feature space. 
- **Anchor loss**: avoiding catastrophic forgetting by preserving topology
- **Min-Max Loss**: push new class training samples towards a new correct new NG node with the same label and pulling new nodes of different labels away from each other

### Related Work
- **Class-incremental learning**: Learn a unified classifier incrementally to recognize all encountered new cases met so far. Often uses KD with old class exemplars. Also episodic memory learning a NN classifier for the new classes. Eliminate bias for class imbalance by using cosine distance metric or learning a bias correction model
- **Multi-Task Incremental Learning**: 1) rehearsal approaches 2) architectural approaches and 3) regularization approaches. 
-> 1A) one way is to store old tasks exemplars using external memory and constrain their losses during learning the new task 1B) use GAN 2A) network pruning / dynamic architectures and parameter masking. 3A) Regularization f.e. EWC 
-> All of these are targeted at disjoint tasks so not feasible for single task - MC scenario
- **Few-Shot Learning**: Adapt model to recognize unseen novel classes using very few training samples. Typically this consists of pretraining the model on the base training set to learn feature embeddings as well as weights for base classes and then for few-shot classification they sample "few-shot" classification tasks from the base dataset to learn a classifier for novel classes.  -> This approach peeks at the base dataset tho, so not useful in this scenario

### Few-Shot Incremental Learning
- Labeled training datasets D_1 ~ D_t where D_1 is set of base classes and D_i (i>1) are few-shot training set of new classes. After training on task_i we need to be able to classify classes from datasets D_1 to D_i 
- Difficulties in this setting: 1) catastrophic forgetting 2) overfitting on new dataset
- A baseline approach could be KD, however this will clearly suffer from imbalanced old/new class training data -> cosine distance can be used byt proves less effective for very few training samples. However, Few-Shot learning still takes large LR for L_CE wich can cause instability in output logits making it difficult to minimize L_DL
- What we try to do with KD is take some samples and - however, there is no guarantee that this will represent heterogenous, non-uniform data well. ->  Instead in this paper we try to preserve the topology of the feature space 
- Every vertex v is assigned with a vector that describes its location in the feature space, the edge set stores the neighbourhood-relations of the vertices (if v_k and v_j are adjacent e_kj = 1 else 0). In this mapped location space we can find clusters. 
- Now we stabilize this feature space and push new class as far away from previous ones as possible
