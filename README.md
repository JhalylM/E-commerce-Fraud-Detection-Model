# **Fraud Detection in E-Commerce Transactions**

## **Tags**  

**Project Type**:  
- Data Cleaning  
- Exploratory Data Analysis  
- Feature Engineering  
- Machine Learning Modeling  
- Model Evaluation  
- Fraud Detection  

**Tools/Libraries Used**:  
- **Python**  
- **Pandas** (for data manipulation and analysis)  
- **NumPy** (for numerical operations)  
- **Matplotlib** (for data visualization)  
- **Scikit-learn** (for machine learning models and evaluation)  
- **XGBoost** (for advanced boosting model)
- **Optuna** (for model training)

## **Overview**  
In the rapidly growing e-commerce industry, fraudulent transactions are a major concern for businesses. These transactions not only lead to direct financial losses but can also harm a company's reputation and erode customer trust. As a data scientist, I was assigned the task of developing a machine learning-based solution to detect fraudulent transactions, helping the business mitigate these risks. The goal is to build a model capable of automatically identifying fraudulent behavior with a high degree of accuracy while minimizing false positives, which can lead to unnecessary customer friction and increased operational costs.

The project began with receiving a large dataset from the business, containing over 1.4 million e-commerce transactions. This dataset included various features such as transaction amounts, payment methods, customer demographics, product categories, and transaction time stamps, which would be useful in uncovering patterns associated with fraud. The challenge was to create a model that could process this data and provide actionable insights that the fraud detection team could use to streamline their investigation process.

---

## **Objectives**  
### **Key Objectives**  
1. **Identify fraud patterns** to help mitigate risks in e-commerce transactions.  
2. Develop and evaluate **machine learning models** to accurately detect fraudulent activities.

---

## **Data Description**  
The dataset contains information on e-commerce transactions, with the following 16 features:  

| **Feature**            | **Description**                                                                                 |  
|------------------------|-------------------------------------------------------------------------------------------------|  
| `Transaction ID`        | Unique identifier for each transaction.                                                        |  
| `Customer ID`           | Unique identifier for each customer.                                                           |  
| `Transaction Amount`    | Monetary value of the transaction.                                                             |  
| `Transaction Date`      | Date of the transaction.                                                                       |  
| `Payment Method`        | Method used for payment (e.g., credit card, PayPal).                                           |  
| `Product Category`      | The category of the product purchased.                                                         |  
| `Quantity`              | The number of items in the transaction.                                                        |  
| `Customer Age`          | Age of the customer.                                                                           |  
| `Customer Location`     | The geographical location of the customer (e.g., city or region).                             |  
| `Device Used`           | Type of device used for the transaction (e.g., mobile, desktop).                               |  
| `IP Address`            | The IP address from which the transaction was made.                                            |  
| `Shipping Address`      | Address where the product was shipped.                                                         |  
| `Billing Address`       | Address associated with the payment method.                                                    |  
| `Is Fraudulent`         | Binary label indicating whether the transaction was fraudulent (`1`) or legitimate (`0`).       |  
| `Account Age Days`      | The number of days since the customer’s account was created.                                   |  
| `Transaction Hour`      | The hour during which the transaction took place.                                              |  

### **Dataset Highlights**  
- **Size**: 1,472,952 transactions (rows) and 16 features (columns).  
- **Fraud Rate**: Approximately 5%, indicating significant class imbalance.  
- **Data Quality**: No missing values, ensuring reliable modeling.

---

## **Objective Summary**  
The project aimed to identify fraudulent transactions while minimizing false positives. Metrics used for evaluation included:  
- **Accuracy**: Overall correctness of predictions.  
- **Precision**: Proportion of correctly identified fraud cases among flagged cases.  
- **Recall**: Proportion of actual fraud cases correctly identified.  

### **Best-Performing Model: XGBoost**  
The final model used **XGBoost**, which performed well in detecting legitimate transactions but had room for improvement in identifying fraudulent transactions. The classification report for the XGBoost model is as follows:

| **Metric**           | **Score**       |  
|-----------------------|-----------------|  
| **Accuracy**          | 95.50%         |  
| **Precision** (Class 1) | 73%          |  
| **Recall** (Class 1)    | 16%          |  
| **F1-Score** (Class 1)  | 26%          |  

Despite achieving high accuracy, the recall for fraudulent transactions (Class 1) remains low at 16%, indicating the model misses a significant number of fraud cases.

---

## **Key Insights Gained**  

### **Fraud Patterns**  
1. **High-Value Transactions**: Fraudulent transactions are disproportionately skewed toward higher amounts.  
2. **Account Age**: Newer accounts (e.g., less than six months old) exhibit higher fraud rates.  

### **Feature Importance (XGBoost)**  
The most predictive features identified by the XGBoost model were:  
- **Transaction Amount**: High correlation with fraudulent activity.  
- **Account Age**: Strong indicator of risk for newer accounts.  
---

## **Conclusion and Recommendations**  

### **Conclusion**  
The XGBoost model achieved **95.50% accuracy**, demonstrating strong performance in distinguishing legitimate transactions. However, the model's low recall for fraudulent transactions highlights the need for further improvements in detecting the minority class.

### **Recommendations**  
1. **Flag High-Value Transactions for Additional Review**  
   - **Rationale**: Insights show a strong correlation between transaction value and fraud likelihood. High-value transactions should be flagged and subjected to additional verification steps.  
   - **Business Impact**: Reduces exposure to significant financial losses while focusing efforts on higher-risk cases.

2. **Strengthen Monitoring for Newer Accounts**  
   - **Rationale**: Fraud is more prevalent in accounts less than six months old, as identified in the data. Implement stricter monitoring for these accounts.  
   - **Business Impact**: Prevents fraudulent activities tied to newly created accounts without affecting established customers.

3. **Model Enhancements to Improve Fraud Recall**  
   - **Rationale**: The current model's recall for fraudulent cases is limited (16%). Techniques like **SMOTE** can address class imbalance, and experimenting with additional models, such as **Gradient Boosting**, may boost performance.  
   - **Business Impact**: Improves the system’s ability to catch fraudulent cases while maintaining precision.

4. **Dashboard Development for Real-Time Insights**  
   - **Rationale**: Fraud teams need visibility into flagged transactions. Developing a user-friendly dashboard will allow for efficient review and intervention.  
   - **Business Impact**: Streamlines operations, improving fraud prevention workflows and response times.

---

## **Next Steps**  

### **Data Enhancements**  
- **Expand Features**: Collect data on transaction timestamps, geographic risk indicators, and user behavior for richer insights.  
- **External Data Sources**: Incorporate fraud intelligence from external sources to improve predictive accuracy.

### **Advanced Modeling**  
- **Address Class Imbalance**: Use oversampling techniques like **SMOTE** to increase recall for fraudulent transactions.  
- **Model Optimization**: Experiment with ensemble approaches, such as **Gradient Boosting**, or perform hyperparameter tuning with **Grid Search**.

### **Operational Deployment**  
- **Integrate into Transaction Systems**: Deploy the XGBoost model for real-time fraud detection.  
- **Threshold Optimization**: Define dynamic thresholds for flagging transactions, ensuring a balance between recall and false positives.

---

## **Contact**  
For inquiries or collaborations, feel free to reach out:  
- **Name**: Jhalyl Mason 
- **Email**: jhalyl.mason@colorado.edu
- **LinkedIn**: www.linkedin.com/in/jhalyl-mason
