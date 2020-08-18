# Cancer_Feature-Selection


## CancerSEEK -- New Sequencing - Feature Engineering as in study - Sequential Forward Selection (SFS)


This notebook will train  **Logistic regression**, **KNN**, **SVC**, **Random Forest**, **Gradient Boosting**, **XGBoost**, **LGBM**, **CatBoost** and **Regularized Greedy Forest (RGF)** on **Winsorized Healthy** or **Scaled Winsorized Healthy** data, depending on whether the model needs data to be scaled. The objective is to see which of the pre-processing steps works best for each of the algorithms on this dataset. Sensitivity and Specificity will be used as evaluation metrics. 

**Feature Engineering**, will be done as mentioned in [this](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5617273/) publication where a combination of mutations and proteins will be evaluated. The same combinations were likely used in the CancerSEEK study. The combinations are as follow:

- `CEA` + `HGF` + `OPN`
- `Mutations` + `CA19-9`
- `Mutations` + `CEA` + `HGF` + `OPN`
- `CA19-9` + `CEA` + `HGF` + `OPN`
- And a combination of them all, referred to as `Combination Assay`, constituting of `Mutations` + `CA19-9` + `CEA` + `HGF` + `OPN`


Based on earlier experiements in notebooks "*CancerSEEK -- New Sequencing - Testing Pre-processing steps (1)*" and "*CancerSEEK -- New Sequencing - Testing Pre-processing steps (2) - more Models*" the overall best and most consistent pre-processing step turned out to be the approach used in the publication; **Winsorizing the healthy samples**. As some of the models (parametric models) demonstrated better performance on scaled data the input data will thus be scaled to accomodate such requirements. 



The "best" set of features will be selected using **Sequential Forward Selection** from the [mlxtend](https://rasbt.github.io/mlxtend/user_guide/feature_selection/SequentialFeatureSelector/#example-8-sequential-feature-selection-and-gridsearch) library. 



#### Cancer detection through the multi-analyte blood test CancerSEEK


Referring to [this original](https://science.sciencemag.org/content/359/6378/926.long) publication and [this, with a new sequencing](https://www.pnas.org/content/early/2020/02/18/1910041117) method applied.




## Conclusions


Many different algorithms and models have been tested out. Although limited model parameter tuning was done there are some approaches that are more promising than others. XGBoost and CatBoost were all fast to train while achieving the best performance at around 74% sensitivity and 100% specificity. 


LightGBM, RGF and Gradient Boosting took all considerable more time to train while not achieving the same results. It shall be noted that the installation of LightGBM didn't allow the use of a faster implementation. When this at a later stage was achieved the training time was in par with that of XGBoost and Catboost's. Neverheless, the performance was still the same as reported in this experiment. 


Further work on this dataset should thus preferably continue with XGBoost and CatBoost. 
