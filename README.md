# DNSC6290 Responsible Machine Learning

1. Elastic net
2. Monotonic XGBoost
3. Explainable Boosting Machine
4. PiML

## Baisc Information
* __Person or organization developing model__: Patirck Hall, `jphall@gwu.edu` & Shuning Ma, `shuningma@gwu.edu`
* __Model date__: June, 2022
* __Model version__: 1.0
* __License__: Apache License 2.0
* __Model implementation code__: [DNSC6290](https://github.com/Mshuning/DNSC6290)

## Intended Use
* __Primary intended uses__: This model is an *example* probability of XGBoost model, with an *example* use case for determining whether (1) or not (0) the annual percentage rate (APR) charged for a mortgage is 150 basis points (1.5%) or more above a survey-based estimate of similar mortgages.
* __Primary intended users__: Students in GWU DNSC 6290 course.
* __Out-of-scope use cases__: Any use beyond an educational example is out-of-scope.

## Training Data
* **Data dictionary**:

| Name | Modeling Role | Measurement Level| Description|
| ---- | ------------- | ---------------- | ---------- |
|**ID**| ID | int | unique row indentifier |
| **LIMIT_BAL** | input | float | amount of previously awarded credit |
| **SEX** | demographic information | int | 1 = male; 2 = female
| **RACE** | demographic information | int | 1 = hispanic; 2 = black; 3 = white; 4 = asian |
| **EDUCATION** | demographic information | int | 1 = graduate school; 2 = university; 3 = high school; 4 = others |
| **MARRIAGE** | demographic information | int | 1 = married; 2 = single; 3 = others |
| **AGE** | demographic information | int | age in years |
| **PAY_0, PAY_2 - PAY_6** | inputs | int | history of past payment; PAY_0 = the repayment status in September, 2005; PAY_2 = the repayment status in August, 2005; ...; PAY_6 = the repayment status in April, 2005. The measurement scale for the repayment status is: -1 = pay duly; 1 = payment delay for one month; 2 = payment delay for two months; ...; 8 = payment delay for eight months; 9 = payment delay for nine months and above |
| **BILL_AMT1 - BILL_AMT6** | inputs | float | amount of bill statement; BILL_AMNT1 = amount of bill statement in September, 2005; BILL_AMT2 = amount of bill statement in August, 2005; ...; BILL_AMT6 = amount of bill statement in April, 2005 |
| **PAY_AMT1 - PAY_AMT6** | inputs | float | amount of previous payment; PAY_AMT1 = amount paid in September, 2005; PAY_AMT2 = amount paid in August, 2005; ...; PAY_AMT6 = amount paid in April, 2005 |
| **DELINQ_NEXT**| target | int | whether a customer's next payment is delinquent (late), 1 = late; 0 = on-time |

* **Source of training data**: GWU Blackboard, email `shuningma@gwu.edu` for more information
* **How training data was divided into training and validation data**: 70% training, 30% validation
* **Number of rows in training and validation data**:
  * Training rows: 112,253
  * Validation rows: 48,085

## Evaluation Data
Details on the dataset(s) used for the quantitative analyses in the card.
* Datasets
* Motivation
* Preprocessing

## Model Details
Basic information about the model.
* Person or organization developing model: Patrick Hall (jphall@gwu.edu), Shuning Ma (shuningma@gwu.edu)
* Model date
* Model version
* Model type
* Information about training algorithms, parameters, fairness constraints or other applied approaches, and features
* Paper or other resource for more information
* Citation details
* License
* Where to send questions or comments about the model

## Quantitative Analyses
* Unitary results
* Intersectional results

## Factors
Factors could include demographic or phenotypic groups, environmental conditions, technical attributes, or others listed in Section 4.3.
* Relevant factors
* Evaluation factors

## Metrics
Metrics should be chosen to reflect potential realworld impacts of the model.
* Model performance measures
* Decision thresholds
* Variation approaches

## Ethical Considerations

## Caveats and Recommendations
