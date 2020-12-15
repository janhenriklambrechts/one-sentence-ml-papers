## Machine Learning and Technical Debt 
| Title | Authors | In One Sentence | Summary | Date | Link | Conference |
| -----  | ------ | --------------- | ------- | ---- | ---- | ---------- |
| Machine Learning: The High-Interest Credit Card of Technical Debt | D. Sculley et al. | Highlights risk factors and design patterns to be avoided in building ML systems  | [Summary](./paper-summary/deploy-ml/MLTechnicalDebt.md) | 18/11/2014 | [Paper](https://storage.googleapis.com/pub-tools-public-publication-data/pdf/43146.pdf) | NeurIPS 2014 Workshop | 

### Abstract
- Machine Learning suffers from ususal software development technical debt + added technical debt specific to ML 
- Design patters to avoid: boundary erosion, entanglement, hidden feedback loops, undeclared consumers, data dependencies, changes in the external world and system-level anti-patterns

### Introduction
- Traditional methods of paying off technical debt: refactoring, increasing coverage of unit tests, deleting dead code, reducing dependencies, tightening APIs and improving documentation
- These traditional methods do not solve ML system level complexity debt
- Using ML models as "black boxes" leads to a lot of technical debt
- Monitoring the system is hard, changes in the external world make it even harder

### Complex Models Erode Boundaries
- Traditional Software Engineering: Strong abstraction boundaries using encapsulation and modular design help create maintainable code in which it is easy to to make isolated changes and improvements
- Machine Learning: Desired behaviour cannot be implemented in software logic without being dependent on external data

- **Entanglement**: Adding or removing a feature / changing a hyperparam will change everything in an ML model: CACE Design: Changing Anything Changes Everything
- Mitigation strategy: 
    1. isolate models and serve ensembles, yet not always possible
    2. develop methods to gain deep insight into behaviour of model predictions, or slice-by-slice data
    3. use regularization that enforces that any change in prediction performance will carry a cost in the objective function
    -> Think before you deploy!
- **Hidden Feedback Loops**:  Some feedback loops are wanted, like optimizing a button. Yet there are also unwanted feedback loops: say this button optimization ML system uses a feature x\_week that tracks how many times the button is clicked over the week, if a button gets better than the distribution of the x\_week will change which will lead to a different model.
    -> Look and remove hidden feedback loops!
- **Undeclared Consumers**: ML model outputs may be used by other teams that implement hidden feedback loops themselves

### Data Dependencies Cost More than Code Dependencies
- **Unstable Data Dependencies**: Using data from other systems is dangerous as this data may degrade qualitatively over time -> Even a bigger chance of this happening as one of the inputs is an output of another ML system
    -> One solution: use a frozen version of this input signal
- **Underutilized dependencies**: Features/signal inputs that provide little incremental value (Legacy features - new feature makes older one obsolete, Bundled features, and incremental features)
- **Static analysis of Data Dependencies**: annotate features and data sources to be able to run automatic checks against them
- **Correction Cascades**: It can be tempting to use output of A if we want to learn A' for a highly related task -> this compounds so is very bad
    -> Mitigation strategy: augment a (input to A) to learn corrections directly within th e same model. At test time, test with appropriate test distributions for use cases

### System-Level Spaghetti
- People tend to write a lot of glue code to adhere to one deep learning framework
- But resulting system might take waaaay less glue code
- Pipeline jungles is a special case of glue code and unused pipelines should be cleaned up
- Config debt

### Dealing with Changes in the External World
- Learn threshold via simple evaluation on heldout validation data
-  Non-causal correlations can suddenly not correlate anynore
- In the real world, label distribution and predicted distribution should be the same and this is an excellent way to see if model is misbehaving 
- Set action limits as a sanity check
