# Predicting Student Alcohol Consumption
Project done with George Li, Derek Modzelewski, Zenny Chu

## Introduction
Student alcohol consumption clearly impacts young people’s health and education. Is it possible to identify students who engage in high levels of drinking? This project tests several classification models to find an effective model to predict student drinking levels.

The dataset used was downloaded from: https://www.kaggle.com/uciml/student-alcohol-consumption

It contains responses from a survey of 396 Portuguese math students. It includes features that describe their personal (health, sex) and family information (sex, parental education, family size), education (trimester grades, study time, absences), and other factors (free time, going out with friends).
## Data Cleansing
The data was taken from a survey of Portuguese secondary school students who reported their alcohol consumption on a 1-5 scale (5 being the highest drinking level).

All binary categorical variables were converted to numerical representations whereas non binary categorical variables were not used.

Weekend and weekday drinking levels were averaged to create a single drinking variable 'alc'. To perform classification, we grouped the students into a binary class 'drinker', 1 being having a drinking level higher than the median, 0 representing a drinking level below the median.

## Visualization
The following heatmap visualizes the relationship between the various features. There are very few strong correlations. The three grades (g1,g2,g3) however were correlateted, indicating consistent academic performances. Other correlations were between the mother and father's education (medu,fedu) as well as weekend and weekday drinking levels (Dalc,Walc).

![heatmap](https://user-images.githubusercontent.com/36087346/36117937-60725dfe-1009-11e8-81c0-6230fce24bfe.png)

## PCA
We found that PCA is not very effective as a small number of components do not explain the majority of the variance. This may be due to the largely independent features.

![pcavisual](https://user-images.githubusercontent.com/36087346/36120447-39f178a6-1011-11e8-9a05-2c5de8c15753.png)


## Classifier Comparison
The classifiers were tested using 10-Fold Cross Validation. The score represents the mean accuracy of the 10 results.

For the random forest classifier, we varied the number of trees and their depth, choosing the ones with the strongest performance.

![classifiercomparison](https://user-images.githubusercontent.com/36087346/36120217-72fc3bc8-1010-11e8-8d61-aba0aafe90fa.png)

Below is a visualization of the classification boundaries.

![classifiervisual](https://user-images.githubusercontent.com/36087346/36120221-760851f8-1010-11e8-8321-35a9d346f95f.png)
## Conclusion
We used both linear and nonlinear classifiers to analyze the data which yielded validation scores around 60-65%.

hile none of the features are dominant, we found that going out with friends (goout), sex, and first period grades (G1) had the most value in predicting alcohol consumption.
## Discussion

The data clouds for “drinkers” and “non-drinkers” heavily overlap, explaining why the decision boundary for kNN is poor. Linear SVM is the most successful classifier likely because it has the least model variance and is least affected by the noisy data. 

Improvements that could be made include changing the median threshold for heavy drinker. Better results could be gotten by collecting alcohol consumption data with quantifiable benchmarks for drinking such as number of drinks instead of self reported levels. Another consideration is to separate features into subsets such as school, home, or personal life features and focus on collecting data and performing analyses on those subsets.


