# Breast cancer prediction

Classifies a breast mass as malignant or benign from cell measurements.

## Data

`datasets/wisconsin.csv` is the Breast Cancer Wisconsin (Diagnostic) set. The label `diagnosis` is `M` or `B`. Both notebooks map that to 1 and 0, scale the features, and reduce them with principal component analysis.

## Models

`01-xgboost.ipynb` trains an XGBoost classifier. Grid search tunes `max_depth`, `learning_rate`, and `n_estimators`.

`02-neural-net.ipynb` trains a Keras network of dense layers and dropout.

A separate comparison, run with PyCaret, is not included as a notebook. It tested logistic regression, SVM, a ridge classifier, random forest, and others, with and without PCA. Logistic regression was the strongest of that set.

## Results

Accuracy on the reported test comparison:

| Model | Accuracy |
| --- | ---: |
| Logistic regression, no PCA | 94.74% |
| Logistic regression, with PCA | 96.49% |
| XGBoost | 97.36% |
| Neural net | 98.24% |

PCA raised the logistic regression score. XGBoost and the neural net were higher still. The write-up judged them on accuracy, precision, recall, and F1.

## Run

```bash
pip install -r requirements.txt
```

Open either notebook from this folder.
