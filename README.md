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
- **Software used to implement the model**:  h2o, interpret, jupyter, matplotlib, numpy, pandas, scikit-learn, seaborn, xgboost
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
    - 'max_bins': 512,
    - 'max_interaction_bins': 32,
    - 'interactions': 10,
    - 'outer_bags': 8,
    - 'inner_bags': 4,
    - 'learning_rate': 0.05,
    - 'validation_size': 0.5,
    - 'min_samples_leaf': 5,
    - 'max_leaves': 5,
    - 'early_stopping_rounds': 100.0,
    - 'n_jobs': 4,
    - 'random_state': 12345
    - 'mono_constraints': (1, 1, 1, -1, 0, -1, 0, 1, 0, 1)

## Quantitative Analyses
* **Metrics used to evaluate your final model**: AUC & AIR
* **State the final values of the metrics for all data: training, validation, and test data**:

  | Partition | AUC | 
  | -------------|--------| 
  | Training | 0.7905 | 
  | Validation | 0.7920 | 
  | Evaluation | 0.8294 | 

  | Compare v. Control | AIR | 
  | ----------------------------|-------| 
  | Asian people vs. White people | 1.146 |  
  | Black people vs. White people | 0.805 | 
  | Females vs. Males | 0.949 | 

* **Provide any plots related to your data or final model -- be sure to label the plots!**:
   * **[Global feature importance](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%202/assignment_2.ipynb)**:
     ![image](https://raw.githubusercontent.com/Mshuning/DNSC6290/main/Image/global%20feature%20importance.png)
   * **[Local feature importance](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%202/assignment_2.ipynb)**:
   * **[Partial dependence](https://github.com/Mshuning/DNSC6290/blob/main/Assignment%202/assignment_2.ipynb)**:

## Ethical Considerations
* **Describe potential negative impacts of using your model**
  * **Math or software problems**: The importance of PAY_0 is too high, which is a bad result in real world. It tells everthing and makes the whole model even useless. 
  * **Real-world risks: who, what, when or how**: The Adverse impact ratio of Black-to-White and Hispanic-to-White are not very well. When using this model to give credit line increase to people, less black and hispanic people will be given credit line increase compared to white people with similar conditions. 
* **Describe potential uncertainties relating to the impacts of using your model**
  * **Math or software problems**: Can easily attcked by hackers changing PAY_0 to determine results they want. 
  * **Real-world risks: who, what, when or how**: May exposed to  well-known risks such as DDOS or man-in-the-middle attacks, and packages it depends on could potentially be hacked to conceal an attack payload. 
* **Describe any unexpected or results**: Although this model was tested and remediated for bias, there is much more to bias than models and data, and this model should be monitored for bias issues moving forward.
