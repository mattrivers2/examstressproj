# Wearable Exam-Stress Analysis

In this project for my Applied Data Science class, my partner (Melissa B.) and I used wearable sensor data recorded during real university exams to test whether physiological signals can predict student exam performance.

**Team:** Melissa Bernal Garcia & Matthew Rivers

## Results

| Metric    | Score |
|-----------|-------|
| Accuracy  | 0.554 |
| Recall    | 0.700 |
| AUC       | 0.585 |

- The logistic regression model was only slightly better than chance
- Heart rate and skin temperature were the strongest predictors of high performance
- Takeaway: raw physiological signals alone are weak predictors of exam performance

## Approach

- Merged 6 sensor streams (heart rate, EDA, BVP, skin temperature, accelerometer) recorded at different sampling rates into one 348K-row dataset across 30 exam sessions
- Cleaned/preprocessed signals throughout the dataset
- Labeled students as high or low performers by splitting their average exam grade at the median (74.8)
- Trained a logistic regression model on 8 standardized features and evaluated it with a classification report, confusion matrix, and ROC curve

## Dataset

**A Wearable Exam Stress Dataset for Predicting Cognitive Performance in Real-World Settings** from PhysioNet (10 students, 3 exams, Empatica E4 wristband). The data is not included in this repo. It can be downloaded here: https://physionet.org/content/wearable-exam-stress/1.0.0/

## Limitations

- Only 10 students, so there are really just 10 independent labels behind the 348K rows
- The train/test split was done by row, so the same students appear in both sets. Holding out entire students would be a stronger test
