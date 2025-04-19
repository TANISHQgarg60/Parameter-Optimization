SVM Parameter Optimization Assignment for UCS654

Overview of SVM and Parameter Optimization

Support Vector Machine (SVM) is a widely used supervised learning algorithm for classification and regression tasks, though it is primarily employed for classification. Key hyperparameters such as the kernel type, C (regularization parameter), and gamma significantly influence model performance. Hyperparameter tuning aims to optimize these parameters to enhance accuracy.

While methods like GridSearchCV are commonly used for this purpose, this project implements a custom fitness function to iteratively optimize SVM parameters, balancing exploration and exploitation for efficient tuning.

Dataset Description

The dataset is sourced from the UCI Machine Learning Repository: MAGIC Gamma Telescope Dataset

Link: https://archive.ics.uci.edu/ml/datasets/MAGIC+Gamma+Telescope Purpose: Differentiate gamma-ray signals from background cosmic particles. Instances: 19,020 Attributes: 11 continuous features describing particle characteristics. Class Distribution: Binary (gamma vs. hadron). Experimental Results

The table below summarizes the optimized parameters and accuracy across 10 independent runs:

Sample Best Accuracy Best Kernel Best Nu Best Epsilon 1 0.62 rbf 0.62 0.07 2 0.71 rbf 0.36 0.69 3 0.64 rbf 0.48 0.25 4 0.71 rbf 0.21 0.92 5 0.72 rbf 0.22 0.75 6 0.73 rbf 0.40 0.52 7 0.62 rbf 0.86 0.12 8 0.71 rbf 1.00 0.91 9 0.41 rbf 0.97 0.33 10 0.72 rbf 0.30 – Analysis and Discussion

Kernel Preference: The Radial Basis Function (rbf) kernel consistently achieved the highest accuracy across all samples, indicating its suitability for capturing the dataset's non-linear decision boundaries. Parameter Trends: Nu: Lower values (e.g., 0.21–0.40) generally correlated with higher accuracy, suggesting a balance between margin width and classification error. Epsilon: No clear trend emerged, though mid-range values (e.g., 0.52) often performed well. Model Generalization: The minimal gap between training and cross-validation accuracy curves (referenced in the original analysis) implies the model is not overfitting, confirming effective parameter optimization. Best-Performing Sample: Sample 6 achieved the highest accuracy (73%) with kernel=rbf, Nu=0.40, and epsilon=0.52. The results highlight the importance of tuning Nu (regularization) and epsilon (margin tolerance) for maximizing separability. Conclusion

The fitness function-driven optimization successfully identified robust hyperparameters for the SVM model. While the rbf kernel dominated, future work could explore hybrid optimization strategies (e.g., combining grid search with evolutionary algorithms) to further refine performance. Additionally, feature engineering or dataset balancing might address cases with lower accuracy (e.g., Sample 9: 41%).
