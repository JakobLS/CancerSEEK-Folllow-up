## Conclusions


Two different set of models have been optimized 
- one on the entire feature set, `Aneuploidy`, `Mutation`, `AFP`, `CA-125`, `CA19-9`, `CEA`, `HGF`, `OPN`, `Prolactin` and `TIMP-1` 
- one on the `Aneuploidy` feature only. 

By using the entire 10 feature set the results are considerable better than when only the single `Aneuploidy` feature is used. **It correctly classifies 98% of the cancer samples** (compared with only Aneuploidy at 80%) **with 99% precision** (94%). **Specificity**, fraction of correctly classified healthy samples, **is 99% with corresponding precision at 98%**. It shall be noted that the [VotingClassifier](#VotingClassifier1) performed well as well, achieving slightly higher specificity at above 99%. 


The results on the entire feature set are promising, giving confident indications on whether a patient has cancer or not. 


Further work on this dataset should thus preferably continue with XGBoost and CatBoost. 
