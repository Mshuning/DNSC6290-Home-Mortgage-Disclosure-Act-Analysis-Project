# DNSC6290 Responsible Machine Learning

## Baisc Information
* __Person or organization developing model__: Patirck Hall, `jphall@gwu.edu` & Shuning Ma, `shuningma@gwu.edu`
* __Model date__: June, 2022
* __Model version__: 1.0
* __License__: [Apache License 2.0](LICENSE.md)
* __Model implementation code__: [DNSC6290](https://github.com/Mshuning/DNSC6290)

## Assignment workflows
Final selected model is **Monotonic XGBoost**, and the other models are here for comparison.
1. **Training basic interpretable models**
   - [Elastic net](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%201/assignment_1.ipynb)
   - [Monotonic XGBoost](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%201/assignment_1.ipynb)
   - [Explainable Boosting Machine](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%201/assignment_1.ipynb)
   - [PiML-EBM](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%201/assignment_1.ipynb)
   - [PiML-ReLU-DNN](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%201/assignment_1.ipynb)
   - [PiML-GAMI-Net](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%201/assignment_1.ipynb)
2. **Post-hoc explanations**
   - [Elastic net](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%202/assignment_2.ipynb)
   - [Monotonic XGBoost](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%202/assignment_2.ipynb)
   - [Explainable Boosting Machine](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%202/assignment_2.ipynb)
3. **Bias testing**
   - [Explainable Boosting Machine](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%203/assignment_3.ipynb)
   - [Monotonic XGBoost](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%203/assignment_3_2.ipynb)
4. **Red-teaming**
   - [Explainable Boosting Machine](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%204/assignment_4.ipynb)
   - [Monotonic XGBoost](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%204/assignment_4_2.ipynb)
5. **Model debugging**
   - [Explainable Boosting Machine](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%205/assignment_5.ipynb)
   - [Monotonic XGBoost](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%205/assignment_5_2.ipynb)

## Intended Use
* __Primary intended uses__: This model is an *example* probability of XGBoost model, with an *example* use case for determining whether (1) or not (0) the annual percentage rate (APR) charged for a mortgage is 150 basis points (1.5%) or more above a survey-based estimate of similar mortgages.
* __Primary intended users__: Students in GWU DNSC 6290 course.
* __Out-of-scope use cases__: Any use beyond an educational example is out-of-scope.

## Training Data
* **Data dictionary**:

| Name | Modeling Role | Measurement Level| Description|
| ---- | ------------- | ---------------- | ---------- |
|**row_id**| ID | int | unique row indentifier |
| **black** | demographic information | binary | 1 = black; 0 = non-black |
| **asian** | demographic information | binary | 1 = asian; 0 = non-asian |
| **white** | demographic information | binary | 1 = white; 0 = non-white |
| **amind** | demographic information | binary | 1 = amind; 0 = non-amind |
| **hipac** | demographic information | binary | 1 = hipac; 0 = non-hipac |
| **hispanic** | demographic information | binary | 1 = hispanic; 0 = non-hispanic |
| **non_hispanic** | demographic information | binary | 1 = non_hispanic; 0 = hispanic |
| **male** | demographic information | binary | 1 = male; 0 = female |
| **female** | demographic information | binary | 1 = female; 0 = male |
| **agegte62** | demographic information | binary | 1 = agegte62; 0 = agelt62 |
| **agelt62** | demographic information | binary | 1 = agelt62; 0 = agegte62 |
| **conforming** | inputs | binary | 1 = the mortgage conforms to normal standards; 0 = the loan is different |
| **debt_to_income_ratio_std** | inputs | float | standardized debt-to-income ratio for mortgage applicants |
| **debt_to_income_ratio_missing** | inputs | binary | 1 = missing debt_to_income_ratio_std; 0 = non-missing debt_to_income_ratio_std |
| **income_std** | inputs | float | standardized income for mortgage applicants |
| **loan_amount_std** | inputs | float | standardized amount of the mortgage for applicants |
| **intro_rate_period_std** | inputs | float | standardized introductory rate period for mortgage applicants |
| **loan_to_value_ratio_std** | inputs | float | ratio of the mortgage size to the value of the property for mortgage applicants |
| **no_intro_rate_period_std** | inputs | binary | -4.09174686250922 = a mortgage does not include an introductory rate period; 0.244394395255126 = a mortgage includes an introductory rate period |
| **property_value_std** | inputs | float | value of the mortgaged property |
| **term_360** | inputs | binary | 1 = the mortgage is a standard 360 month mortgage; 0 = the mortgage is a different type of mortgage |
| **high_priced**| target | binary | whether the annual percentage rate (APR) charged for a mortgage is (not) 150 basis points (1.5%) or more above a survey-based estimate of similar mortgages, 1 = is; 0 = not |

* **Source of training data**: [Home Mortgage Disclosure Act (HMDA) data](https://www.consumerfinance.gov/data-research/hmda/)
* **How training data was divided into training and validation data**: 70% training, 30% validation
* **Number of rows in training and validation data**:
  * Training rows: 112,253
  * Validation rows: 48,085
![image](https://raw.githubusercontent.com/Mshuning/DNSC6290/main/Image/features.png)

## Evaluation Data
* **Source of test data**: [Home Mortgage Disclosure Act (HMDA) data](https://www.consumerfinance.gov/data-research/hmda/)
* **Number of rows in test data**: 19,831
* **State any differences in columns between training and test data**: None

## Model Details
- **Final selected model**: Monotonic XGBoost
   - [Basic version](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%201/assignment_1.ipynb)
   - [Remediation of discovered discrimination version](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%203/assignment_3_2.ipynb)
   - [Red-teaming version](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%204/assignment_4_2.ipynb)
   - [Debugged version](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%205/assignment_5_2.ipynb)
* **Columns used as inputs in the final model**: 'term_360', 'conforming', 'debt_to_income_ratio_missing', 'loan_amount_std', 'loan_to_value_ratio_std', 'no_intro_rate_period_std', 'intro_rate_period_std', 'property_value_std', 'income_std', 'debt_to_income_ratio_std'
- **Column(s) used as target(s) in the final model**: 'high_priced'
- **Type of model**: [Monotonic XGBoost model](https://xgboost.readthedocs.io/en/stable/index.html)
- **Software used to implement the model**: `h2o`, `interpret`, `jupyter`, `matplotlib`, `numpy`, `pandas`, `scikit-learn`, `seaborn`, `xgboost`
- **Version of the modeling software**: 
    - h2o==3.32.1.3
    - interpret==0.2.4
    - jupyter==1.0.0 
    - matplotlib==3.3.4
    - numpy==1.19.5
    - pandas==1.1.5
    - scikit-learn==0.24.2
    - seaborn==0.11.1
    - xgboost==1.4.2
- **Hyperparameters or other settings of your model**: 
    - 'colsample_bytree': 0.3,
    - 'colsample_bylevel': 0.3,
    - 'eta': 0.05,
    - 'max_depth': 3,
    - 'reg_alpha': 0.0005,
    - 'reg_lambda': 0.0005,
    - 'subsample': 0.3,
    - 'min_child_weight': 10,
    - 'gamma': 0.2
    - 'n_jobs': 4,
    - 'random_state': 12345,
    - 'mono_constraints': (1, 1, 1, -1, 0, -1, 0, 1, 0, 1)

## Quantitative Analyses
* **Metrics used to evaluate your final model**: AUC & AIR
* **State the final values of the metrics for all data: training, validation, and test data**:

  | Partition | AUC | 
  | -------------|--------| 
  | [Training](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%205/assignment_5_2.ipynb) | 0.7894 | 
  | [Validation](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%203/assignment_3_2.ipynb) | 0.7907 | 
  | [Evaluation](https://github.com/jphall663/GWU_rml/blob/master/assignments/model_eval_2022_06_13_09_47_08.csv) | 0.8294 | 

  | Compare v. Control | AIR | 
  | ----------------------------|-------| 
  | [Asian people vs. White people](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%203/assignment_3_2.ipynb) | 1.146 |  
  | [Black people vs. White people](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%203/assignment_3_2.ipynb) | 0.805 | 
  | [Females vs. Males](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%203/assignment_3_2.ipynb) | 0.949 | 

* **Provide any plots related to your data or final model -- be sure to label the plots!**:
   * **[Global feature importance](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%202/assignment_2.ipynb)**:
     ![image](https://raw.githubusercontent.com/Mshuning/DNSC6290/main/Image/global%20feature%20importance.png)
   * **[Local feature importance](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%202/assignment_2.ipynb)**:
     ![image](https://raw.githubusercontent.com/Mshuning/DNSC6290/main/Image/local%20feature%20importance.png)
   * **[Partial dependence](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%202/assignment_2.ipynb)**:
     ![image](https://raw.githubusercontent.com/Mshuning/DNSC6290/main/Image/partial%20dependence1.png)
     ![image](https://raw.githubusercontent.com/Mshuning/DNSC6290/main/Image/partial%20dependence2.png)
     ![image](https://raw.githubusercontent.com/Mshuning/DNSC6290/main/Image/partial%20dependence3.png)
     ![image](https://raw.githubusercontent.com/Mshuning/DNSC6290/main/Image/partial%20dependence4.png)
     ![image](https://raw.githubusercontent.com/Mshuning/DNSC6290/main/Image/partial%20dependence5.png)
     ![image](https://raw.githubusercontent.com/Mshuning/DNSC6290/main/Image/partial%20dependence6.png)
     ![image](https://raw.githubusercontent.com/Mshuning/DNSC6290/main/Image/partial%20dependence7.png)
     ![image](https://raw.githubusercontent.com/Mshuning/DNSC6290/main/Image/partial%20dependence8.png)
     ![image](https://raw.githubusercontent.com/Mshuning/DNSC6290/main/Image/partial%20dependence9.png)
     ![image](https://raw.githubusercontent.com/Mshuning/DNSC6290/main/Image/partial%20dependence10.png)
   * **[Bias testing grid search results](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%203/assignment_3_2.ipynb)**:
     
     ![image](https://raw.githubusercontent.com/Mshuning/DNSC6290/main/Image/bias%20testing%20grid%20search%20results.png)
   * **[Variable importance for stolen model](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%204/assignment_4_2.ipynb)**:
     ![image](https://raw.githubusercontent.com/Mshuning/DNSC6290/main/Image/variable%20importance%20for%20stolen%20model.png)
   * **[Adversarial examples](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%204/assignment_4_2.ipynb)**:
     ![image](https://raw.githubusercontent.com/Mshuning/DNSC6290/main/Image/adversarial%20examples.png)
   * **[Global logloss residuals](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%205/assignment_4_5.ipynb)**:
     
     ![image](https://raw.githubusercontent.com/Mshuning/DNSC6290/main/Image/global%20logloss%20residuals.png)

## Ethical Considerations
* **Describe potential negative impacts of using your model**
  * **Math or software problems**: Due to compatibility issues between `h2o` and `xgboost`, the [stolen decision tree model](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%204/assignment_4_2.ipynb) generated had unusual big numbers, causing [adversial examples](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%204/assignment_4_2.ipynb) full of missing values. 
  * **Real-world risks: who, what, when or how**: The [adverse impact ratio of Black-to-White](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%203/assignment_3_2.ipynb), although > 0.8, is relatively low (0.805), which could lead to unfair difference in outcomes. When using this model to predict high-priced mortgages, for every 100,000 low priced loans to white people, there are only 80,500 low-priced loans to Black people. 
* **Describe potential uncertainties relating to the impacts of using your model**
  * **Math or software problems**: With different versions of software, some codes may need to be changed, especially for `xgboost`. 
  * **Real-world risks: who, what, when or how**: Hackers may steal the model to do model extraction attack. According to [adversial examples results in Red-teaming](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%204/assignment_4_2.ipynb), the hackers can get predictions they want by inputting missing values in multiple features. 
* **Describe any unexpected or results**: Although this model was tested and remediated for bias, there is much more to bias than models and data, and this model should be monitored for bias issues moving forward.
