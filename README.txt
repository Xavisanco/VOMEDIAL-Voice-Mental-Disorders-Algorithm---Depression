# Algorithm VOMEDIAL (Voice Mental Disorders Algorithm)

This repository contains the implementation of the algorithm described in the article:
"FEATURE EXTRACTION IN VOICE SIGNALS FOR DEPRESSION DETECTION: A Machine Learning Perspective with Empirical Mode Decomposition". 

## Description

This algorithm decomposes the voice signals of clinically selected individuals with depression and healthy controls using the EMD (Empirical Mode Decomposition) method. 
It implements a voice signal processing and modeling pipeline to distinguish between two groups (e.g., individuals with depression vs. healthy), 
leveraging intrinsic mode functions (IMFs) and machine learning techniques.

Comparison of IMFs using Gaussian kernel
A similarity function based on a Gaussian kernel is defined to compare pairs of signals (IMFs) between the two groups.
For each IMF (out of 16 possible), the average similarity between groups is calculated.
IMFs whose similarity is less than or equal to a fixed threshold (1e-10) are selected, as they are considered to contain relevant discriminative information.

Extraction of statistics from selected IMFs
Selected IMF signals are segmented into windows.
For each window, descriptive statistics are extracted: skewness, kurtosis, median, standard deviation, and mean.
These statistics are aggregated to form a feature vector for each signal.

Class balancing
Random sampling is applied to equalize the number of samples between the two groups, avoiding bias in model training.

Data splitting and scaling
Balanced data are split into training and test sets.
Normalization (StandardScaler) is applied to improve model performance.

Model training and tuning
A Gradient Boosting model is defined, and hyperparameter tuning is performed using GridSearchCV with cross-validation.
The model is evaluated on the test set, and performance metrics are calculated: accuracy, F1-score, precision, recall, and specificity.

Results visualization
A confusion matrix and ROC curve are generated to visualize model performance.
Optimal parameters and obtained metrics are stored and displayed.

Conclusion:
The algorithm allows automatic identification of the most relevant frequency bands (IMFs) for classification between groups, 
extraction of statistical features from signals, data balancing, and supervised model training—all within a reproducible and visualizable pipeline. 
This facilitates the analysis of vocal biomarkers in clinical and research contexts.

## License
This software is available under the **Academic/NonCommercial License**:

- Free for academic, research, and educational use.
- Commercial use requires a separate license.

For commercial licensing inquiries, contact: xavisanco@gmail.com & jordi.sole@uvic.cat


