# Mechanism-of-Action-MoA---DeepNN
## What is the Mechanism of Action (MoA) of a drug? And why is it important?
In the past, scientists derived drugs from natural products or were inspired by traditional remedies. Very common drugs, such as paracetamol, known in the US as acetaminophen, were put into clinical use decades before the biological mechanisms driving their pharmacological activities were understood. Today, with the advent of more powerful technologies, drug discovery has changed from the serendipitous approaches of the past to a more targeted model based on an understanding of the underlying biological mechanism of a disease. In this new framework, scientists seek to identify a protein target associated with a disease and develop a molecule that can modulate that protein target. As a shorthand to describe the biological activity of a given molecule, scientists assign a label referred to as mechanism-of-action or MoA for short.

## What is the dataset?
The data is based on a new technology that measures simultaneously (within the same samples) human cells’ responses to drugs in a pool of 100 different cell types (thus solving the problem of identifying ex-ante, which cell types are better suited for a given drug). In addition, you will have access to MoA annotations for more than 5,000 drugs in this dataset.

## Model
We are using a Deep NN model with two dropouts, two batch normalization.
And we're using **Optuna** to fine tune the hyperparameter value. 

**Observations:**
* 2774 drugs out of 3700 drugs have 6 rows that correspond to 2 doses and 3 treatment times. 
* Only 64 drugs have 12 samples, I was expecting more drugs to be profiled twice.
* Only 3 drugs have 18 sample, the drugs were profiled 3 times.
***
### Conclusion of EDA:
* Train and Test Set share Quite same Distribution.
* Cell Features are highly correlation among themselves (can be used to create new features).
* Data is quite skewed , so some statistical features can be also be created.

The Cross Validation strategy i have used for submission is Multi-label stratified Kfold. 
* All Targets are highly correlative can be used for transfer learning.
* About 71 Non-scoredtargets don't have mechanism of action so can be dropped while pre-training.
***
