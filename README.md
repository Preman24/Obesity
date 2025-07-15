# Obesity
As one of the most serious public health challenges of the 21st century, the impact of obesity goes beyond the realm of personal health; obesity should no longer be viewed simply as a cosmetic problem affecting certain individuals but as an epidemic that threatens global health. It has become a heavy burden on the healthcare system and the economy. Data released by the World Health Organisation in 2024 reveals that 1 in 8 people in the world are obese (World Health Organization: WHO, 2024). Obesity not only directly contributes to the incidence of cardiovascular disease, type 2 diabetes, and specific cancers. The social and economic costs of obesity and its prevention or treatment are high. The dataset that was used to analyze was collected from Kaggle, and it is a questionnaire consisting of 16 questions with answers in categorical format that involve demographic and obesity-related attributes, with one additional variable showing the participants' weight classification group from 2112 participants from Mexico. To facilitate this analysis, the data was divided into 3 sections based on the nature of the question: Dietary Habits, Lifestyle Habits, and Demographic Factors, along with a prediction on obesity based on the features using a simple neural network model.

# Key Findings
Demographic Factors

- Gender
> Females: More "Insufficient Weight" found (173 vs. 134 expected).
> Males: More "Overweight" found(332 vs. 293 expected).
- Age: Significant link (F-statistic: 95.573, p-value: 5.39e-58); younger individuals show higher obesity.

- Height: Taller individuals are often "Normal" weight (F-statistic: 16.109, p-value: 2.36e-10).

- Family History: Strong relationship (Chi-square: 575.571, p-value: 0.0000); those with a family history are more likely to be "Obese" (964 vs. 177 expected).



Correlation analysis

=> Obesity
- Weight: Strongest correlation with obesity at 0.418, indicating higher weight significantly increases obesity risk.
- Frequent Snacking: Moderate correlation of 0.362, suggesting that eating between meals contributes to increased caloric intake and obesity risk.
- Family History: Correlation of 0.359, highlighting the role of genetic predisposition and shared environmental factors in obesity.
- Age: Correlation of 0.291, indicating that older individuals may face metabolic changes and lifestyle factors that contribute to weight gain.
- Gender: Weakest correlation at 0.114, suggesting that while there are differences in obesity rates by gender, they are less significant than other factors.

=> Insights on Independent Variables
- Gender and Height: Highest correlation at 0.618, indicating a strong relationship that may affect weight perceptions and management.
- Weight and Family History: Correlation of 0.497, underscoring the connection between weight and genetic predisposition.
- Height and Weight: Correlation of 0.462, suggesting that height influences weight norms and perceptions.


Neural Network Predictions

=> Method
- Set the dependent variable (obesity_level) to sparse output for the multi-class output
- built 3 layers to keep the model simple since the dataset is considered small (~ 2112 samples)
- L1 as the regularizer to penalize some weights to zero, helping to generalize better to unseen data
- Implemented Dropout layers by randomly setting a percentage of neurons to zero during training to prevent overfitting by promoting redundancy
- Set the last layer to softmax since it is a multi-class problem
- Used EarlyStopping to stop the model once the performance does not improve after learning for a period of time

=> Result
<img width="984" height="784" alt="image" src="https://github.com/user-attachments/assets/5c1ccb3f-205a-4da7-b21a-7a6099051659" />

| Metric                | Value   |
|-----------------------|---------|
| Training Accuracy      | 0.9323  |
| Training Loss          | 0.4241  |
| Validation Accuracy     | 0.9734  |
| Validation Loss         | 0.3335  |
| Overall Accuracy (Based on testing)        | 0.9551  |

The model demonstrates strong performance with a training accuracy of 93.23%, indicating that it effectively learns from the training data. The training loss of 0.4241 suggests that the model is minimizing errors during training. The validation accuracy of 97.34% reflects its ability to generalize well to unseen data, indicating that the model is not overfitting. With an overall accuracy of 95.51%, the model achieves a high level of accuracy across all evaluations, making it reliable for practical applications
