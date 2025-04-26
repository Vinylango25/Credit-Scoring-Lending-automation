Machine Learning Automation of Lending Decisions/Credit Scoring

Automating lending decision-making using machine learning is revolutionizing the finance and 
lending industry by leveraging advanced algorithms to streamline and enhance the approval process.

 
  Traditionally, loan approvals involved labor-intensive manual reviews and subjective judgments which 
 not only leads to inefficiencies and potential biases but also can be time consuming.

Machine learning lending decision automation hold high promise in speeding up the approval process, 
reducing the time from application to decision, improving operational efficiency and reducing on 
labor-related costs.

Automated systems enables real-time processing of loan applications, can handle large volumes of 
applications simultaneously and hence scaling operations without the need for proportional 
increases in resources.

This work focus on evaluating the extend at which leveraging the three machine learning 
algorithms: Random Forest, XGBoost and LGBM in loan application decision making can reduce 
the cost of loan processing

# Credit Scoring and Lending Automation

## Overview
This project automates the loan approval process by using machine learning models to assess borrower risk. Traditional credit scoring is manual, time-consuming, and prone to inconsistencies. Our system accelerates decision-making, reduces operational costs, and minimizes human bias in lending.

## Problem Statement
Loan providers face scaling challenges due to manual reviews. By automating credit evaluation with ML, institutions can ensure faster, fairer, and more scalable lending operations.

## Approach
- Preprocessed and cleaned credit data.
- Trained and evaluated three models: **Random Forest**, **XGBoost**, and **LightGBM**.
- Analyzed feature importance to identify key approval drivers.
- Visualized class balance and performance metrics.
- Evaluated operational benefits of automation.

## Models and Techniques
- **Random Forest Classifier**: Reduces overfitting through ensemble learning.
- **XGBoost**: High-performance gradient boosting algorithm.
- **LightGBM**: Fast, scalable gradient boosting model for large datasets.

Each model was tuned to balance recall (identifying high-risk clients) and precision (avoiding false approvals).

## Key Visualizations
- **Feature Importance Charts** (bar_rf2.pdf, bar_xgb2.pdf)
- **Class Distribution Graph** (class_weights.pdf)
- **Performance Summary Table** (table_22.png)

## Results
| Model         | Accuracy | F1-Score | AUC-ROC  |
|---------------|----------|----------|----------|
| Random Forest | High     | Strong   | Good     |
| XGBoost       | Very High| Strong   | Very Good|
| LightGBM      | Fast Training | Good | Moderate to Good |

- Random Forest and XGBoost demonstrated strong predictive power.
- LightGBM trained faster but required tuning to match performance.
- Key features included loan amount, income, and past delinquencies.

## Conclusion
Automating credit scoring through machine learning greatly improves the scalability, speed, and fairness of lending decisions. XGBoost emerged as the top-performing model, balancing predictive accuracy and operational efficiency.

## How to Run
1. **Clone this repository**:
    ```bash
    git clone https://github.com/Vinylango25/Credit-Scoring-Lending-automation.git
    cd Credit-Scoring-Lending-automation
    ```
2. **Install dependencies**:
    ```bash
    pip install scikit-learn xgboost lightgbm matplotlib seaborn pandas numpy
    ```
3. **Run the notebook**:
    Launch Jupyter Notebook and open `Machine Learning Automation of Loans Approval.ipynb`.

## Folder Structure



## Future Work
- Deploy the best-performing model into a real-time loan approval platform.
- Enhance interpretability using SHAP values.
- Address class imbalance using advanced sampling techniques like SMOTE.
- Implement model monitoring to detect drift over time.

## Author
**[Vinylango25](https://github.com/Vinylango25)**


