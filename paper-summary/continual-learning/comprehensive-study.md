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
- Continual learning, lifelong learning and incremental learning are names for the same problem but different settings ->  All target catastrophic forgetting 
- Continual learning and lifelong learning approaches often increase model capacity and are tested in a setting in which a new task is added in each new state of the system. 
- Incremental learning is interesting because work has shown them to improve upon continual learning approaches when tested in a common experimental setting. 
- 6 desirable properties of incremental learning: 
1. Complexity: capacity to integrate new information with a minimal change in terms of the model structure. (For a deep NN only the size of classification layer should grow, otherwise the total n of parameters will increase at large scale)
2. Memory: Not requiring past data is preferable but might give worse results
3. Accuracy: Performance on past and new classes should approach that of access to data at all times
4. Timeliness: delay between occurence of new data and integration in incremental models
5. Plasticity: Capacity to deal with new classes that are significantly different from the ones learned in the past
6. Scalability: Aptitude to learn a large number of classes (tens of thousands) and ensure usability
- Gap between replay and non-replay methods is still significant

### Related Work
- **Model Growth**: Growing a brain, Progressive NN, TreeCNN, Expert Gate, Deep Adaptation Networks. PackNet uses pruning (cannot learn learge amount of tasks because network cannot be strongly compressed without significant performance loss). Piggyback adds binary masks for individual weights (but does add extra parameters). Memory Aware Synapses identifies the most important weights in model by looking at the sensitivity of output function and penalizes changes to important weights. Self-Organizing maps are online unsupervised learning algos and can be adapted to IL. NG networks are related to SOMs. PROPRE: incremental learner based on NG and SOMs. NGPCA for robot platform. TOPICuses these NG networks and a min/max loss. TPCIL very similar to TOPIC. Addition of nodes gradually increases the complexity of the architecture. 
- **Fixed Representation**: finetuning approaches. DeeSIL applies a simple transfer learning scheme. Often not very good approaches
- **Finetuning**: often use distillation to reduce catastrophic forgetting, very similar to self distillation, teacher and student are the same network. Learning without Forgetting: leverages KD to minimize discrepancy between representations. iCaRL usees both KD and past exemplars in memory to predict with earest mean of exemplars method instead of the raw scores to not incur prediction bias from finetuning on newer classes.  Balanced fine-tuning helps a lot to improve upon iCaRL. Learning without Memorizing distillation-based approach without memory for past classes, preserving attention maps. M2KD: distillation from all previous models, also distilling intermediary maps. LUCIR: cosine normalization to balance old and new prob., less forget constraint modifies usual distillation loss for feature vectors. Inter-class separation encourages network to separate past and new class embeddings (still open to improvements from newer KD methods). PODnet adds a spatial-based distillation loss that constrains evolution of model representation. Another recent stream features modeling IL as an imbalanced learning problem. Bias Correction adds a linear layer after the prediction layer to reduce bias with help of val set. IL2M advocates vanilla finetungin as a backbone for IL.  MDFL multiply each class weith by mean norm of past class and dividing it by the mean norm of new class weights.  ScaIL is motivated by the same hypthesis.   

### IL
- score bias correction: some recent works hypothesize that IL is akin to imbalanced learning where the network is trained with enough images for the new classes but only a few for the past classes -> class imbalance layer behind the fc
- past memory management: bounded memory K, role of exemplar selection is highly debated - this paper thinks herding does work

### Conclusion
- When memory is allowed, best global result is obtained when IL is seen as imbalanced learning. - Vanilla FT backbone followed by a bias res -> class imbalance layer behind the fc
- past memory management: bounded memory K, role of exemplar selection is highly debated - this paper thinks herding does work

### Conclusion
- When memory is allowed, best global result is obtained when IL is seen as imbalanced learning. - Vanilla FT backbone followed by a bias rectification layerr
- If enough memory is available and number of incremental states is low, distillation based approaches become competitive
- If no memory allowed, fixed representation with finetuning works best - however, this only works well if task does not change over time.
