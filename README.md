# ACTEX-PA

This document is organized into three sections:

* General Model Building Steps
* Specific Types of Models
* Unsupervised Learning

## 8.1 General Model Building Steps

### 8.1.1 Problem Definition

* __Three main categories of predictive analytics modeling problems:__
  * __Descriptive__: Focuses on what happened in the past and aims to "describe" or interpret observed trends by identifying relationships between variables.
  * __Predictive__: Focuses on what will happen in the future and making accurate "predictions".
  * __Prescriptive__: Focuses on the effects of different "prescribed" decisions and answers the "what if?" and "what is the best course of action" questions.

* __Characteristics of predictive modeling problems:__
  * __Issue__: There is a clearly identified and defined business issue to be addressed.
  * __Questions__: The issue can be addressed with a few well-defined questions.
  * __Data__: Good and useful data are available for answering the questions above.
  * __Outcomes__: The predictions will likely drive actions or increase understanding.
  * __Better Solution__: Predictive analytics likely produces a solution better than any existing approach.
  * __Update__: We can continue to monitor and update the models when new data becomes available.

* __How to produce a meaningful problem definition?__
  * __General Strategy__: Get to the root cause of the business issue and make it specific enough to be solvable.
  * __Specific Strategies__: 
   * _(Hypotheses):_ Use prior knowledge of the business problem to ask questions and develop testable hypotheses.
   * _(KPIs):_ Select appropriate key performance indicators to provide a quantitative basis for measuring success.
    
* __Constraints__
  * The availability of easily accessible and high quality data.
  * The imlementation issues, e.g., the presence of necessary IT infrastructure and technology to fit complex models efficiently, the cost and effort required to maintain the selected model.


## 8.1.2 Data Collection

### __Data Design__

* __Revelance__: Need to ensure that the data is unbiased, i.e., representative of the environment where the model will operate.
  * __Population__: Important for the data source to be a good proxy of the true population of interest.
  * __Time frame__: Advisable to choose the time period which best reflects the business environment of interest. In general, recent history is better than distant history.

* __Sampling__: The process of taking a subset of observations from the data source to generate our dataset.
  * __Random Sampling__: Randomly draw observations from the underlying population without replacement. Each record is equally likely to be sampled.
  * __Stratefied Sampling__: Divide the underlying population into a number of non-overlapping "strata" non-randomly, and randomly sample a set number of observaions from each stratum.
  <br/><br/>
  _A special case - systematic sampling:_ Draw observations according to a set pattern; no random mechanism controlling which observations are sampled.
  
* __Granularity__: Refers to how precisely a variable is measured, i.e., level of detail for information contained by the variable.


### __Data Quality Issues__
* __Reasonableness__: Data values should be reasonable (make sense) in the context of the business problem, e.g. Let $\text{age, time} \geq 0$.
* __Consistency__: Records in the data should be inputted consistently on the same basis and rules, e.g., same unit for numeric variables, and same coding scheme for categorical variables.
* __Sufficient Documentation__: Examples of useful elements:
  * A clear description of each variable (numeric vs. factor).
  * Notes about any past updates or other irregularities of the dataset.
  * A statement of accountability for the correctness of the dataset.
  * A description of the governance processes used to manage the dataset.

### __Other Data Issues__
* __Personally identifiable information (PII)__: Information that can be used to trace an individual's identity, e.g., name, SSN, address, photographs, and biometric records.
<br></br>
_How to handle PII?_
<br></br>
* _Anonymization_: Anonymize or de-identify the data to remove the PII.
* _Data Security_: Ensure that the data recieves sufficient protection.
* _Terms of Use_: Be well aware of the terms and conditions and use the privacy policy related to the collection and use of data.

* __Variables Causing Unfair Descrimination__: Differential treatment based on sensitive variables, e.g., race, ethnicity, gender, or prohibited classes, may lead to unfair descrimination and may be deemed unethical.

* __Target Leakage (Frequently Tested in Recent PA Exams__: 
  * _Definition_: When predictors in a model "leak" information about the target variable that will not be available when the model is applied.
  * _Problem with this issue_: These variables cannot serve as predictors and would lead to artificially good model performance if mistakenly included.
  

## 8.1.3 Exploratory Data Analysis (EDA)

* __Aim:__ Use descriptive statistics + graphical displays to gain insights into the distriution of variables on their own and in relation to one another (esp. the target variable).


```math
\implies\begin{cases}
 & \text{1. Clean the data to make it ready for analysis} \\
 & \text{2. Identify potentially useful predictors} \\
 & \text{3. Generate useful features} \\
 & \text{4. Decide which type of model (GLMs or trees) is more suitable} \\ 
 & \text{(e.g., for a highly non-linear relation, trees may do better)}
\end{cases}
```

* __Univariate Data Exploration Tools:__

| Variable Type | Descriptive Statistics | Visual Displays | Observations |
|:---|:---|:---|:---|
| Numeric Variables | • Mean <br> • Median <br> • Variance <br> • Min <br> • Max | • Histograms <br> • Boxplots | • Any (right) skew? <br> • Any Outliers? |
| Categorical Variables | Class Frequencies | Bar Charts | • Which levels are common? <br> • Any sparse levels? <br> • (For binary targets) Presence of imblance |

* __Bivariate Data Exploration Tools:__

| Variable Type | Descriptive Statistics | Visual Displays | Observations |
|:---|:---|:---|:---|
| Numeric x Numeric         | • Correlations                              | • Scatterplots                                   | • Any noticeable relationships e.g., monotonic, non-lienar?               |
| Numeric x Categorical     | • Mean/Median Split By Categorical Variable | • Split boxplots, histograms (stacked or dodged) | • Any sizable differences in the means / medians among the factor levels? |
| Categorical x Categorical | • 2-way Frequency Table                     | • Bar charts (stacked, dodged or filled)         | • Any sizable differences in the proportions among the factor levels?     |





# 8.2 Specific Types of Models

# 8.3 Unsupervised Learning
