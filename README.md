# Predicting Student Alcohol Consumption
Project done with George Li, Derek Modzelewski, Zenny Chu

## Introduction
This project was done to see how effectively we could predict alcohol consumption amongst students based on various demographic features as well and their success and investment in their studies. The dataset was downloaded from : https://www.kaggle.com/uciml/student-alcohol-consumption

The data was taken from a survey of Portugese high school students who reported their alcohol consumption on a 1-5 scale with 5 with a greater score indicating a heavier drinker. All binary categorical variables were converted to numerical representations whereas non binary 

To perform classfiication, we grouped the students into two classes, drinking more that the median drinker and drinking less than the median drinker.

## Vizualization
The following heatmap was produced to visualize the relationship between the various features. Most of the features are uncorellated. Grades however were corrletted, indicating consist student performances. Other correlations were parental education as well as weekend and weekday drinking levels

![heatmap](https://user-images.githubusercontent.com/36087346/36117937-60725dfe-1009-11e8-81c0-6230fce24bfe.png)

## PCA
![pcavisual](https://user-images.githubusercontent.com/36087346/36120447-39f178a6-1011-11e8-9a05-2c5de8c15753.png)

We see that PCA is not very effective as a small number of components do not explain the majority of the variance. This may be due to the largely independent features
## Classifier Comparison
Mean scores were computed using 10-Fold Cross Validation
Random Forest before PCA had parameters trees = 9 and depth = 2
Random Forest after PCA had parameters trees = 8 and depth =3
![classifiercomparison](https://user-images.githubusercontent.com/36087346/36120217-72fc3bc8-1010-11e8-8d61-aba0aafe90fa.png)
![classifiervisual](https://user-images.githubusercontent.com/36087346/36120221-760851f8-1010-11e8-8321-35a9d346f95f.png)
## Results
We used both linear and nonlinear classifiers on the data, and our tests yielded scores around 60-65%.

While none of the features are dominant, the three that had the most value in predicting alcohol consumption were “goout”, “sex”, and “G1”.
## Summary
These unimpressive scores reflect the mediocre reconstruction explained variance of 25%.
While none of the features are dominant, the three that had the most value in predicting alcohol consumption were “goout”, “sex”, and “G1”.
The data clouds for “drinkers” and “non-drinkers” heavily overlap, explaining why the decision boundary for kNN is terrible. Linear SVC seems to be the most successful classifier because it has the least model variance and so is least affected by the noisy data. 
Improvements that could be made include changing the 50% threshold for heavy drinker, as well as using data with more quatifiable benchmarks for drinking such as number of drinks. Another consideration is isolating the school, home, and personal life features and see how each feature set works independetly.


