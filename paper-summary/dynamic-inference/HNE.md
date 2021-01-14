## Hierarchical Neural Ensembles

| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Anytime Inference with Distilled Hierarchical Neural Ensembles | Andria Ruiz et al. | Dynamically allocating multiple models in the ensemble and training them with distillation provides good dynamic inference | [Summary](./paper-summary/dynamic-inference/HNE.md) | 14/12/2020 | [Paper](https://arxiv.org/pdf/2003.01474.pdf)| AAAI 2020 | 

### Abstract
- Dynamically stopping the prediction result earlier to limit computation
- Proposes Hierarchical Neural Ensembles, embedding multiple models into one - making an ensemble (aking to Shrivastava paper)
- They target any-time inference (inference time gets decided while predicting, not beforehand) 
- Distillation can improve these ensembles, akin to slimmable neural networks

### Related Work
- **Efficient Networks:** 1) design efficient blocks; 2) NAS; 3) Pruning; 4) Reduce channels; 5) Skip layers
- **Anytime Inference:** 1) intermediate classifiers / early exits
- **Network Ensembles:** 1) Sharing layers is common because inference cost goes up drastically - this work is the first that leverages binary tree structure for any-time inference

### Experiments
- Good results, but beatable really

