
# Compressed-Rule-Ensembles
Here we present additional experiments for th article "Seeing the Trees in the Forest – Compressed Rule Ensemble Learning"

# Interpretability

To demonstrate the interrpretability of soft rules generated from CRE, we compare the rule outputs of CRE-I and RuleFit-I on the diabetes data.
![RuleCre](https://user-images.githubusercontent.com/88620679/128714592-25eb0992-20ac-4769-b20b-53872901ef5c.PNG)
![RulesPRE](https://user-images.githubusercontent.com/88620679/128714606-58a96491-e05c-4b39-8aae-27ddc40b5982.PNG)

First of all, CRE produces significantly less rules, with on average lower number of conditions, which is partly due to the penalization of extra conditions. Secondly, it is interesting to note that the only rules with 3 conditions left in the CRE model (mass & pedi & plas) also appears 7 times in the RuleFit output. This very important combination is therefore present in both models, but compressed in the CRE-I.

The output tells us, that an important risk transition for diabetes takes place between a BMI of 24.5 and 28.35.While it is difficult to interprete the distribution of splitpoints in each rule, most information can be captured by looking at meassures of centrality. For example, another way to interpret this rule would be to look at the median, which leads to the interpretation, that the risk transition takes place around a BMI of 26. 

# Influence of the tree generating process, using Random Forest to generate the trees:
In the following shown is CRE-I-RF which uses the CRE-I settings but random forests to generate the decision rules:

![RF-Experiment](https://user-images.githubusercontent.com/88620679/128699574-b8ff757d-9df4-4b7e-84d9-cd4faa3aa45b.png)

The results are interesting: While losing some accuracy, the models get more condensed and compact with significantly smaller model sizes on average.

# Further experiments with the compression parameter k:

The following plot shows the influence of the compression parameter k on the AUC (red line) and the model size (blue line) on the diabetes dataset:


![k_diabetes](https://user-images.githubusercontent.com/88620679/128712259-824b9021-3dc3-40c9-8e88-f987409e8d24.png)

The best tradeoff between model size and accuracy is in this case for k=3 or even smaller if simpler solutions are preferable. The stability remains relatively constant around 0.75 for all values tried.

![Ionosphere_k](https://user-images.githubusercontent.com/88620679/128718570-57f3c086-e0c3-42dd-a5a1-29f91721ec77.png)
