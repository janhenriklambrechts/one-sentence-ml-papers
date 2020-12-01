## Elastic Weight Consolidation

| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Few-short Image Generation with Elastic Weight Consolidation | Yijun Li et al. | Proposes an algorithm that generates high-quality samples of different target domains | [Summary](./paper-summary/GANs/ElasticWeightConsolidation.md) | 01/12/2020 | [Paper](https://papers.nips.cc/paper/2020/file/b6d767d2f8ed5d21a44b0e5886680cb9-Paper.pdf) | NeurIPS 2020 |

## Abstract
- Few-shot image generation: generating more data of a given domain with few examples
- It might be impossible to fully infer the distribution from a few examples, but maybe we can adapt a large, related source domain to this target task
- Weight adaptation regularization is proposed, which preserves the *diversity* of the source domain and the *appearance* of the target domain. 


## Introduction
- GANs need incredible amounts of images for a specific domain but this data may not be available in a lot of usecases -> F.e. art
- Challenge: Fit the weights as such that tedious manual designs are not necessary when swapping domains
- How: Elastic Weight Consolidation has been proposed which evaluates the importance of each paramter by estimating its Fisher Information relative to the likelihood
    -> Problem: in the generative setting we do not have a fixed objective. (solution: freeze the discriminator)

## Related Work
- Few-shot learning: metric learning, meta-learning, dynamical weight predictions.
- There have been some few-shot generation methods in which they finetune a pretrained generator and add aditional weights
- Style Trasnfer: Domain Translation requires a lot of data in both domains, only recently some work in the few-shot setting has been proposed

## Proposed method
- Lets first start looking at what 'good weights' look like by finetuning a model from one domain to another domain. We can see that weights in the later layers are presumably more important as they change the least.
- How do we know now exactly what weights to keep? -> Use Fisher information 
- When we add the Fisher regularization term, we can preserve the diversity of source domain instead of just mimicking the target domain directly.

## Experimental Results
- Impressive qualitative results, previous methods either deliver samples that are incomprehensible or almost mimicking the target domain. 
- Also impressive quantitative improvements

## Discussion
- When source and target domain lay far from eachother, the results become less and less realistic as is intuitive  

