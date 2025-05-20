# SVM Parameter Optimization

This project focuses on optimizing Support Vector Machine (SVM) parameters using the Car Evaluation dataset from the UCI Machine Learning Repository.

## Dataset Overview

The Car Evaluation dataset consists of 1,728 samples, each described by 6 categorical features and classified into 1 of 4 target classes.

### Features
1. **buying**: Buying price (v-high, high, med, low)
2. **maint**: Maintenance cost (v-high, high, med, low)
3. **doors**: Number of doors (2, 3, 4, 5-more)
4. **persons**: Passenger capacity (2, 4, more)
5. **lug_boot**: Luggage boot size (small, med, big)
6. **safety**: Safety rating (low, med, high)

### Target Classes
- **unacc**: Unacceptable
- **acc**: Acceptable
- **good**
- **v-good**: Very good

## Methodology

1. **Data Preprocessing**
   - Encode categorical features using `LabelEncoder`
   - Standardize features with `StandardScaler`
   - Split data into 70% training and 30% testing sets
   - Generate 10 random samples using different random seeds

2. **Parameter Optimization**
   - Evaluate four SVM kernels: linear, polynomial, RBF, and sigmoid
   - For each sample:
     - Randomly select values for C (Nu) and gamma (Epsilon) in the range [0, 10]
     - Train SVM with these parameters
     - Record the best parameters based on accuracy

3. **Evaluation**
   - Identify the best parameters for each sample
   - Plot learning curves to visualize model convergence
   - Store results in a DataFrame for further analysis

## Results

The optimization explores combinations of:
- **Kernels**: linear, poly, rbf, sigmoid
- **C (Nu)**: 0 to 10
- **Gamma (Epsilon)**: 0 to 10

### Example Results

| Sample | Best Accuracy | Best Kernel | Best Nu | Best Epsilon |
|--------|--------------|-------------|---------|--------------|
| 1      | 0.96         | rbf         | 8.23    | 3.37         |
| 2      | 0.94         | linear      | 9.52    | 6.62         |
| ...    | ...          | ...         | ...     | ...          |

### Learning Curve

The learning curve illustrates:
- **Training Score**: Accuracy on training data
- **Cross-Validation Score**: Accuracy on validation data
- **X-axis**: Number of training samples
- **Y-axis**: Accuracy

This graph highlights:
1. Model learning progression
2. Convergence behavior
3. Signs of overfitting or underfitting
4. Optimal training set size

## Conclusion

SVM parameter optimization effectively identified optimal hyperparameters for car evaluation classification, achieving high accuracy and demonstrating strong generalization across different data splits.

## Requirements

- Python 3.x
- scikit-learn
- pandas
- numpy
- matplotlib
- seaborn
- ucimlrepo