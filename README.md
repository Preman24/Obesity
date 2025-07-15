# Obesity
As one of the most serious public health challenges of the 21st century, the impact of obesity goes beyond the realm of personal health; obesity should no longer be viewed simply as a cosmetic problem affecting certain individuals but as an epidemic that threatens global health. It has become a heavy burden on the healthcare system and the economy. Data released by the World Health Organisation in 2024 reveals that 1 in 8 people in the world are obese (World Health Organization: WHO, 2024). Obesity not only directly contributes to the incidence of cardiovascular disease, type 2 diabetes, and specific cancers. The social and economic costs of obesity and its prevention or treatment are high. The dataset that was used to analyze was collected from Kaggle, and it is a questionnaire consisting of 16 questions with answers in categorical format that involve demographic and obesity-related attributes, with one additional variable showing the participants' weight classification group from 2112 participants from Mexico. To facilitate this analysis, the data was divided into 3 sections based on the nature of the question: Dietary Habits, Lifestyle Habits, and Demographic Factors, along with a prediction on obesity based on the features using a simple neural network model.

# Key Findings


Neural Network Predictions
=> Method
- Set the dependent variable (obesity_level) to sparse output for the multi-class output
- built 3 layers to keep the model simple since the dataset is considered small (~ 2112 samples)
- L1 as the regularizer to penalize some weights to zero, helping to generalize better to unseen data
- Implemented Dropout layers by randomly setting a percentage of neurons to zero during training to prevent overfitting by promoting redundancy
- Set the last layer to softmax since it is a multi-class problem
- Used EarlyStopping to stop the model once the performance does not improve after learning for a period of time

=> Result
- 
<img width="984" height="784" alt="image" src="https://github.com/user-attachments/assets/5c1ccb3f-205a-4da7-b21a-7a6099051659" />
