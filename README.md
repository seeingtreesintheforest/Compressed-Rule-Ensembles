# Compressed-Rule-Ensembles
Here we present additional experiments for th article "Seeing the Trees in the Forest – Compressed Rule Ensemble Learning"

# Influence of the tree generating process, using Random Forest to generate the trees:
In the following shown is CRE-I-RF which uses the CRE-I settings but random forests to generate the decision rules:

![RF-Experiment](https://user-images.githubusercontent.com/88620679/128699574-b8ff757d-9df4-4b7e-84d9-cd4faa3aa45b.png)

The results are interesting: While losing some accuracy, the models get more condensed and compact with significantly smaller model sizes on average.

# Further experiments with the compression parameter k:

The following plot shows the influence of the compression parameter k on the AUC (red line) and the model size (blue line) on the diabetes dataset:


![k_diabetes](https://user-images.githubusercontent.com/88620679/128712259-824b9021-3dc3-40c9-8e88-f987409e8d24.png)

The best tradeoff between model size and accuracy is in this case for k=3 or even smaller if simpler solutions are preferable. The stability remains relatively constant around 0.75 for all values tried.
