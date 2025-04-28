# Credit Scoring Lending Automation

## 📚 Introduction

Automating lending decision-making using machine learning is revolutionizing the finance and lending industry by leveraging advanced algorithms to streamline and enhance the approval process.

Traditionally, loan approvals involved labor-intensive manual reviews and subjective judgments which not only leads to inefficiencies and potential biases but also can be time consuming.

Machine learning lending decision automation hold high promise in speeding up the approval process, reducing the time from application to decision, improving operational efficiency and reducing on labor-related costs.

Advanced machine learning algorithms analyze vast amounts of data to predict borrower risk more accurately than traditional methods, leading to better decision-making.

Automated systems enable real-time processing of loan applications, can handle large volumes of applications simultaneously and hence scale operations without the need for proportional increases in resources.

By analyzing individual borrower profiles, machine learning can tailor loan offers and terms to better meet the needs and risk profiles of applicants.

This work focuses on evaluating the extent to which leveraging the three machine learning algorithms: Random Forest, XGBoost, and LGBM in loan application decision-making can reduce the cost of loan processing.

---

## 📌 Business Problem

Manual processing of loan applications is labor-intensive, costly, and prone to human errors. It requires significant manpower for reviewing, assessing, and deciding on each application. As application volumes grow, this method becomes inefficient and unsustainable. Financial institutions risk higher costs, slower services, and potential biases in decision-making.

---

## 🎯 Main Task

Develop a machine learning model that can automatically assess and decide on loan applications. The model must minimize incorrect approvals and rejections while maximizing accuracy. It should enhance operational efficiency, reduce labor dependency, and enable scalable processing of large application volumes.

---

## 🚀 Performance Evaluation of the Models

The accuracy of these models was optimized through hyper-parameter tuning using Microsoft AutoML (FLAML), which runs cross-validation internally, and creates optimal parameters based on the number of runs which is determined by the assigned ‘time budget’.

![Performance Evaluation Table](figures/table_22.png)

- As shown in the above table, the accuracy of the three models are in range 72-76% with the LGBM Classifier being the best model in all the metrics, and offers the best balance of precision and recall, hence well-balanced in identifying rejections and accepts while also performing accurately overall.

- The F1-score is highest for LGBM, indicating it provides the best trade-off between precision and recall among the models. LGBM has a better ability to classify loan applications accurately with a balanced approach to both types of errors.

- LGBM has the highest recall, meaning it is the most effective at identifying loan applications that should be rejected. This reduces the risk of false negatives, ensuring that more of the applications that need rejection are correctly identified.

- Hence, utilizing the LGBM Classifier model can significantly enhance the accuracy of loan rejections, leading to better risk management and reduced financial losses. RF offers a reliable alternative.

- XGBoost lags behind in all metrics, showing lower precision and recall, which translates to a higher rate of both false positives and false negatives. It also has the lowest accuracy among the three, suggesting it is less effective overall for this classification task. However, it may benefit from further tuning or adjustments to enhance its results.

- To evaluate the prediction performance of the models, the loan application dataset which contains 9898 loan applications was split into 90% for training the models and 10% testing set (unseen data) for testing their performance.

---

## 📈 Further Evaluation Based on Confusion Matrices

![Confusion Matrix Figure](figures/fig2.png)

- LGBM excels in approving valid loan applications, with a true positive rate of 84%. This means it’s highly effective at identifying genuine applicants, which helps in increasing the number of approved loans and boosting potential revenue.

- LGBM also performs well in avoiding false rejections, with a lower false positive rate of 41%. This minimizes the risk of denying valid loan applications, which is crucial for maintaining customer satisfaction and not losing out on potential business.

- RF is strong but slightly less effective than LGBM in approving loans, with an 82% true positive rate. While it still performs well, the slight decrease in effectiveness could mean a few more missed valid applications, potentially impacting revenue.

- RF maintains a good balance between precision and recall for loan approvals and rejections. However, its performance is not as high as LGBM, which could affect its efficiency in accurately processing loan applications.

- XGBoost has the lowest performance among the models, with the highest rate of missed valid loan applications and the lowest true positive rate for approvals. This could lead to more missed opportunities and a higher risk of incorrectly rejecting deserving applicants.

- XGBoost’s performance suggests it may need substantial improvements. For better business outcomes, focusing on enhancing RF or opting for models like LGBM could lead to more accurate loan approvals and rejections, improving overall business effectiveness and customer satisfaction.

---

## 💰 Cost Evaluation

![Cost Evaluation Figure](figures/cost.png)

- To evaluate the cost-saving capability of each of the three models, the cost of predictions resulting in incorrect acceptance and incorrect rejection was calculated for each model and converted as a percentage of the total labor costs as shown in yellow and blue bars in each of the three figures.

- Note that the predictions and calculations were based on the test data (unseen data). Evaluating the models on test data simulates the real scenario of loan applications evaluations where the truth values are not known with certainty.

- Based on the model’s cost of incorrect acceptance and cost of incorrect rejection, and taking the total labor costs as reference (100%), the saving cost of each model was calculated as a percentage of total labor costs (shown by the bars with green color in each of figures).

- The result shows that the proportion of cost due to incorrect acceptance is generally higher (49-54% of the total labor cost) compared to the cost of incorrect rejection (28-31% of the total labor cost). This agrees well with the information in the confusion matrices; high false positives and low false negatives. Thus, further work on data engineering and robust model optimizations is needed to reduce the number of incorrect loan acceptances.

- The machine learning saving cost on unseen data is in the range of 14–23%, with LGBM model having the biggest cost saving (23%), agreeing with the previous results (LGBM being the best model).

---

## ⚖️ Class Weights and Optimal Probability Thresholds

Having found that LGBM is the best model compared to the other models implemented in this work, its probability decision threshold is investigated at different class weights. Note that in each tree model, the default class weight is {0: 1, 1: 1 }.

Note from the data in the table that the optimal probability decision threshold and the accuracy depends on the set class weights.

![Class Weights Figure](figures/cw.png)

| Class Weights        | Optimal Probability Threshold | Accuracy |
|----------------------|-------------------------------|----------|
| {0:1, 1:1}            | 0.504949                      | 0.754545 |
| {0:1, 1:2}            | 0.643535                      | 0.755556 |
| {0:1, 1:3}            | 0.683131                      | 0.754545 |
| {0:1, 1:4}            | 0.772222                      | 0.754545 |
| {0:1, 1:5}            | 0.693030                      | 0.753535 |
| {0:1, 1:6}            | 0.801919                      | 0.753535 |

- For this specific problem, the optimal accuracy is achieved when the class weight is set at {0: 1, 1: 2 } and the corresponding probability decision threshold is 0.643535.

- From the figure, the smaller the difference in the values of class weights, the lower the probability thresholds required to achieve high accuracy and vice versa.

---

## 🏁 Conclusion and Recommendations

**Conclusion**:
- Machine learning, especially using the LGBM Classifier, significantly improves the efficiency and accuracy of loan approvals.
- Automating loan decisions with machine learning can lead to up to a 23% reduction in labor-related costs.
- Among the evaluated models, LGBM performs best in balancing precision and recall, while XGBoost shows the lowest effectiveness.
- Optimal decision thresholds for LGBM depend on class weights, with a weight setting of {0: 1, 1: 2} providing the highest accuracy.

**Recommendation**:
- Use the LGBM Classifier for loan decision-making to leverage its superior accuracy and efficiency.
- Continue to optimize models and refine data engineering to further reduce incorrect loan decisions and improve cost savings.
- Reassess the performance of XGBoost and consider further tuning or alternative models to enhance overall effectiveness.

---

## 📬 Contact

For further questions or collaborations, feel free to reach out:

**Vinylango25**  
[GitHub Profile](https://github.com/Vinylango25)

