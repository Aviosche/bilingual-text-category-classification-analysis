# ML Model Text Classification Comparison on a Bilingual Text Dataset with Category Labels
Comparison of Multinomial Naive Bayes, Logistic Regression and Random Forest models, with vectorizer (Count vs TF-IDF) and word formatting (Stemming vs None) configurations operating on a Bilingual dataset with Turkish and English texts along with their category label of 6 unique categories.

Dataset used in the analysis can be found in this url: https://github.com/metunlp/hate-speech.
Dataset v2 was used in this project.

Dataset was taken and used without any modifications besides preprocessing steps for model training and testing.

Our findings indicate that Logistic Regression performs the best with highest Accuracy and F1-Scores in all configurations but the training time is much longer compared to the other two models, Multinomial Naive Bayes is the fastest to train and test while Random Forest is the worst on all metrics. We believe the reason for Random Forest's abysmal performance is due to the bilingual nature of the dataset resulting in some trees to learn parts of both languages while others learn only one of them. Another issue with Random Forest can be seen in the confusion matrices as it kept predicting a single category and we believe the reason is the fact that sports category has much more entries than the rest, creating a large imbalance which trains many of the trees how to predict sports.

In terms of configurations, Count Vectorizer performed better for both Logistic Regression and Multinomial Naive Bayes while stemming reduced the performance for both algorithms. On the other hand, Random Forest performed better with stemming and TF-IDF Vectorizer. The differences in results for the configurations for each model were less than 2% in F1-Score.

Result Metrics:
<img width="1136" height="408" alt="image" src="https://github.com/user-attachments/assets/0d9bc098-7846-49c5-8c8a-40cc456d0d09" />

Confusion Matrices:
<img width="1989" height="1621" alt="image" src="https://github.com/user-attachments/assets/cc9399b6-bdd1-46fb-bc44-2cbccbed7aa7" />
