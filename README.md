# Classification of Non-Coding RNA using SVM

## Objective
This project addresses the classification of non-coding RNA (ncRNA) sequences using Support Vector Machines (SVMs).

## Data and Feature Representation
The dataset includes a labeled set of ncRNA instances formatted for LIBSVM. Each instance comprises an 8-dimensional feature vector, with features scaled between 0 and 1, which were utilized as inputs to the SVM model for training and evaluation.

## Methodology
### 1. Linear SVM Classification
The first task involved training SVMs with a linear kernel by varying the regularization parameter \( C \) across an exponential sequence. For each \( C \) value, a linear SVM was trained on the entire training set, and the classification accuracy on the test set was computed. The results were plotted to show the relationship between accuracy and \( C \) values.

### 2. RBF Kernel SVM Classification with Cross-Validation
To further optimize the SVM, an RBF kernel with two hyperparameters, \( C \) and \( \alpha \), was used. A 5-fold cross-validation was conducted on 50% of the training set, randomly chosen. This subset was divided into five equal folds (200 instances per fold), where each fold served as a validation set for a classifier trained on the remaining four folds. The average cross-validation accuracy was computed for each combination of \( C \) and \( \alpha \) values (evaluated over a grid of 13x13).

The cross-validation accuracy matrix for each pair of \( C \) and \( \alpha \) values was visualized, allowing the identification of the optimal parameters that maximize accuracy.

### 3. Final Model Training and Testing
With the best \( C \) and \( \alpha \) values from the cross-validation, the RBF SVM was trained on the complete training set and then tested on the independent test set to evaluate its classification accuracy.

## Conclusion
This project successfully demonstrated the effectiveness of SVMs, particularly with an RBF kernel, in classifying ncRNA sequences. By optimizing hyperparameters through cross-validation, we achieved an improvement in classification accuracy.
