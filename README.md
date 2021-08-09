# Compressed-Rule-Ensembles
Here we present additional experiments for th article "Seeing the Trees in the Forest – Compressed Rule Ensemble Learning"

# Interpretability

To demonstrate the interrpretability of soft rules generated from CRE, we compare the rule outputs of CRE-I and RuleFit-I on the diabetes data.

                            rule                                                       description coefficient
1                         linear                                                      linear: plas    2.560285
2                      var6rg1 1                                              mass < [24.25;28.35]   -0.654322
3                      var2rg1 1                                               plas < [87.5;114.5]   -0.480767
4                      var6rg2 1                                              mass < [28.65;32.25]   -0.429136
5                         linear                                                      linear: preg    0.425648
6  var2rg4 1_var6rg4 1_var7rg3 1 mass < [37.75;43.1] & pedi < [0.579;0.765] & plas < [150.5;178.5]   -0.405401
7                      var8rg1 1                                                 age < [22.5;33.5]   -0.346784
8                      var2rg2 1                                                plas < [115.5;133]   -0.345316
9            var8rg1 0_var8rg3 1                            age < [47.5;59.5] & age >= [22.5;33.5]    0.253563
10           var2rg4 1_var8rg1 1                          age < [22.5;33.5] & plas < [150.5;178.5]   -0.138577
11           var2rg4 1_var8rg2 1                          age < [34.5;45.5] & plas < [150.5;178.5]   -0.075010
12 var2rg3 1_var6rg4 1_var7rg4 1   mass < [37.75;43.1] & pedi < [0.776;0.952] & plas < [133.5;149]   -0.065921
13           var1rg2 1_var2rg4 1                           plas < [150.5;178.5] & preg < [4.5;9.5]   -0.053161
14                     var7rg2 1                                               pedi < [0.377;0.57]   -0.043723
15                     var7rg1 1                                               pedi < [0.16;0.376]   -0.032775
16           var2rg2 1_var7rg3 1                         pedi < [0.579;0.765] & plas < [115.5;133]   -0.015111
17           var1rg2 1_var2rg2 1                             plas < [115.5;133] & preg < [4.5;9.5]   -0.010311
18           var2rg4 1_var7rg2 1                        pedi < [0.377;0.57] & plas < [150.5;178.5]   -0.004382
19                     var2rg4 1                                              plas < [150.5;178.5]   -0.002466

# Influence of the tree generating process, using Random Forest to generate the trees:
In the following shown is CRE-I-RF which uses the CRE-I settings but random forests to generate the decision rules:

![RF-Experiment](https://user-images.githubusercontent.com/88620679/128699574-b8ff757d-9df4-4b7e-84d9-cd4faa3aa45b.png)

The results are interesting: While losing some accuracy, the models get more condensed and compact with significantly smaller model sizes on average.

# Further experiments with the compression parameter k:

The following plot shows the influence of the compression parameter k on the AUC (red line) and the model size (blue line) on the diabetes dataset:


![k_diabetes](https://user-images.githubusercontent.com/88620679/128712259-824b9021-3dc3-40c9-8e88-f987409e8d24.png)

The best tradeoff between model size and accuracy is in this case for k=3 or even smaller if simpler solutions are preferable. The stability remains relatively constant around 0.75 for all values tried.
