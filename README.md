
# Compressed-Rule-Ensembles
Here we present additional experiments for the article "Seeing the Trees in the Forest – Compressed Rule Ensemble Learning" that will be included in further iterations of the manuscript.


# Interpretability

To demonstrate the interrpretability of soft rules generated from CRE, we compare the rule outputs of CRE-I and RuleFit-I on the diabetes data.
![RuleCre](https://user-images.githubusercontent.com/88620679/128714592-25eb0992-20ac-4769-b20b-53872901ef5c.PNG)
![RulesPRE](https://user-images.githubusercontent.com/88620679/128714606-58a96491-e05c-4b39-8aae-27ddc40b5982.PNG)

First of all, CRE produces significantly less rules, with on average lower number of conditions, which is partly due to the penalization of extra conditions. Secondly, it is interesting to note that the only rules with 3 conditions left in the CRE model (mass & pedi & plas) also appears 7 times in the RuleFit output. This very important combination is therefore present in both models, but compressed into only 2 soft rules in the CRE-I model.

The output tells us, that an important risk transition for diabetes takes place between a BMI of 24.5 and 28.35. While it is difficult to interprete the distribution of splitpoints in each rule, most information can be captured by looking at meassures of centrality. For example, another way to interpret this rule would be to look at the median, which leads to the interpretation, that the risk transition takes place around a BMI of 26. Readily available is the information, that for the covariate mass, there is different areas where the prediction changes. Overall the number of interesting covariates and combinations thereof is much more compact in CRE-I compared to pre, making it easier to analyse and interprete the final model.

# Comparison Soft Rule from CRE with hard rule from RuleFit

To compare the soft rules from CRE with hard rules from RuleFit we included a further experiment where we set the allowed tree depth to 1. This is required, as the boundaries are hard to interprete for rules that consists of multiple conditions. We again used the diabetes dataset for this experiment.
![hard_vs_soft_mass](https://user-images.githubusercontent.com/88620679/128841299-06785bcf-ccb4-4fb2-a401-b25ec705adf8.png)

# Influence of the tree generating process, using Random Forest to generate the trees:
In the following shown is CRE-I-RF which uses the CRE-I settings but random forests to generate the decision rules:

![rf_CRE](https://user-images.githubusercontent.com/88620679/128840356-a27ae7d0-1216-46be-a8b0-2372e2de01c7.png)

The results are interesting: While losing some accuracy when using Random Forests to generate the decision trees, the models get more condensed and compact with smaller model sizes on average. However the stability decreases, which might be a result of the bootstrapping in Random Forests. 

# Further experiments with the compression parameter k:

The following plot shows the influence of the compression parameter kmax on the AUC (red line) and the model size (blue line) on the diabetes dataset:


![k_diabetes](https://user-images.githubusercontent.com/88620679/128712259-824b9021-3dc3-40c9-8e88-f987409e8d24.png)

The best tradeoff between model size and accuracy is in this case for kmax=3 or even smaller if simpler solutions are preferable. The stability remains relatively constant around 0.75 for all values tried.

![Ionosphere_k](https://user-images.githubusercontent.com/88620679/128718570-57f3c086-e0c3-42dd-a5a1-29f91721ec77.png)
 
 A similar picture goes for the Ionosphere dataset. As long as kmax is not chosen too small, the model is relatively robust towards the choice of kmax. Generally, smaller values of kmax lead to smaller model sizes. 
 
 Interesting further work goes towards multi-objective optimization and chosing values kmax that are optimal for accuracy, model size and stability. 
