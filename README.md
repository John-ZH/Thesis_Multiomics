# Thesis_Multiomics
Source code and output for the thesis "Feature Selection for Multi-omics Data" , for MSc Statistics &amp; Data Science at Leiden University.

## Directory Contents

* data: Data used for multi-omics feature selection
  - \data\raw: Raw data files from the Adrenocortical carcinoma dataset
  * \data\derived: Processed data files from the Adrenocortical carcinoma dataset
  * \data\out_models: Models built from the data for each method.
* \data\sel_features: List of variables selected for each method. Coefficients/Weights are included if possible.
  - \data\sel_features\gene_converted: Gene list converted from to variables selected for each method. Used for pathway analysis.
* \data\out_pathway: Pathway analysis results for each method. Not included in the github repository due to large file size. 

* 00: Code for processing raw ACC data.

* 01: __(Code for Supervised Methods)__
  - 01a: Code for applying logistical regression `Glmnet`.
  * 01b: Code for applying `Squeezy` and `Xtune`.
    - 01b: Code for applying `Squeezy` and `Xtune` on unstandardized (raw) data. *Only used for checking issues with Squeezy and Xtune.*
  * 01c: Code for applying `Globaltest`.
  * 01d: Code for applying Cox regression `Glmnet`.
* 02: __(Code for Factor Analysis)__
  - 02a: Code for applying FABIA.
  * 02b: Code for applying MFA using `FactoMineR`.
  * 02c: Code for applying MOFA using `MOFA2`.
    - 02c2: Code to check if `MOFA2` results are affected by the random seed set. *`MOFA2` results are unaffected by `set.seed()` in R.*
  * 02d: Visual comparison between FABIA and MOFA results.
  * 02e: Ensemble methods using `Superbiclust`
 * 03: Code for applying Gaussian Graphical Models (GGM) using `rags2ridges`.
   - 03b: Code to return all optimal Lambdas for `rags2ridges`. *Split from the main GGM .Rmd file to save rending time.*
   * 03c: Code to return all optimal Lambdas for `rags2ridges`, with a maximum lambda set to 1000. *This is to demonstrate that setting `lambdaMax` too large would cause some optimization to fail.*
 * 04: Code for displaying selected features in a nice(r) format.
 * 05: __(Code for Pathway Analysis)__
   - 05a: Code for pathway analysis of features selected by logistic regression `Glmnet`.
   * 05b: Code for pathway analysis of features selected by `Squeezy`. (`Xtune` returns no features)
   * 05c: Code for pathway analysis of features selected by `Globaltest`.
   * 05d: Code for pathway analysis of features selected by Cox regression `Glmnet`, using `lambda.1se`.
     - ~~05d2: Code for pathway analysis of features selected by Cox regression `Glmnet`, using `lambda.min`.~~ Deprecated in favor of 05d.
   * 05e1: Code for pathway analysis of features selected by FABIA using `thres_L`.
     - ~~05e: Code for pathway analysis of features selected by FABIA using top 5% threashold .~~ Deprecated in favor of 05e1.
   * 05f: Code for pathway analysis of features selected by MFA.
   * 05g1: Code for pathway analysis of features selected by MOFA using `thres_L`.
     - ~~05g: Code for pathway analysis of features selected by MOFA using top 5% threashold .~~ Deprecated in favor of 05g1.
   * 05h: Code for pathway analysis of features selected by FABIA ensembles.
   * 05i: Code for pathway analysis of features selected by ensemble between FABIA and MOFA.
   * 05j: Code for pathway analysis of features of interest in the FABIA-MOFA plots.
   * 05k: Code for pathway analysis of features selected by GGM.
   * 05z: Code for pathway analysis of all features selected by each method. __(Also contains the pathway analysis for all gene variables in the ACC dataset as a reference.)__
