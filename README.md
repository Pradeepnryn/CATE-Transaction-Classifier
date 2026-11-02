# CATE-Transaction-Classifier
# Artham-CATE

### Financial Transaction Categorization Using Machine Learning

An experimental machine learning project designed to automatically classify financial transaction descriptions into expense categories.

CATE is being developed as the transaction categorization component for **Artham**, an iOS personal finance application.

**Project Status:** Active Development | ML Prototype

## 1. Project Overview

Manually categorizing financial transactions can be repetitive and time-consuming. CATE explores how Natural Language Processing (NLP) and supervised machine learning can automate transaction classification.

The model takes a transaction description as input and predicts its corresponding expense category.

**Example**

- Input: `grocery purchase`
- Predicted Category: `Groceries`

## 2. Technologies Used

| Technology | Purpose |
|---|---|
| Python | Model development |
| Pandas & NumPy | Data preparation and analysis |
| Scikit-learn | Machine learning |
| TF-IDF | Text feature extraction |
| Logistic Regression | Multiclass classification |
| Joblib | Model serialization |
| Google Colab | Experimentation and development |

## 3. Dataset

The baseline notebook uses a transaction classification dataset containing:

- **2,026 transaction examples**
- **16 dataset columns**
- Approximately **90 expense categories**
- Transaction descriptions and hierarchical category labels

The model uses transaction descriptions as input features and category identifiers as target labels.

Dataset provenance, generation methodology and sharing permissions should be documented before publishing the full dataset.

## 4. Machine Learning Workflow

The baseline classification pipeline follows these stages:

1. Load and inspect the transaction dataset.
2. Select transaction descriptions and target categories.
3. Split the dataset into training and testing subsets.
4. Convert descriptions into numerical TF-IDF features.
5. Train a multiclass Logistic Regression classifier.
6. Evaluate predictions on the held-out test set.
7. Experiment with predictions on new transaction descriptions.
8. Save trained model components for subsequent use.

## 5. Feature Extraction

CATE uses **Term Frequency–Inverse Document Frequency (TF-IDF)** to convert text descriptions into numerical representations.

The baseline implementation uses:

- Unigrams and bigrams
- Lowercase normalization
- Sublinear term frequency scaling

These features allow the classifier to learn patterns associated with different transaction categories.

## 6. Model Training

The baseline model uses Logistic Regression with balanced class weights.

The notebook uses an 80:20 stratified training/testing split with a fixed random state for reproducibility.

## 7. Model Evaluation

The saved baseline notebook output reports:

| Metric | Recorded Result |
|---|---|
| Accuracy | 97.04% |
| Test examples | 406 |
| Learned categories | 90 |
| TF-IDF vocabulary | 2,401 features |

**Important:** These are experimental results from the saved notebook, not independently verified production performance.

Additional evaluation is needed to assess generalization to unfamiliar merchants, ambiguous descriptions, unseen transaction patterns and potential train/test similarity.

## 8. Integration with Artham

CATE is intended to support automatic transaction categorization within Artham.

The broader development work includes experimentation with model serialization, local prediction services and Swift client communication.

Full integration with the Artham iOS application is planned and should not be considered completed.

## 9. Current Limitations

- The training dataset is relatively small for the number of categories.
- Some categories have limited examples.
- Performance on genuinely unseen transaction descriptions needs further evaluation.
- Ambiguous transaction descriptions may require additional context.
- The model is experimental and not production-ready.

## 10. Future Improvements

- Expand and diversify the training dataset.
- Evaluate macro and weighted F1-scores.
- Introduce stronger duplicate and data-leakage checks.
- Improve classification of ambiguous transactions.
- Add confidence-based manual review.
- Create reproducible model training and inference workflows.
- Integrate CATE with the Artham iOS application.

## 11. Development Approach

This project was developed through an AI-assisted workflow using ChatGPT for code generation, debugging, experimentation and technical guidance.

The project also serves as a practical learning exercise in machine learning, NLP, classification evaluation and model integration.

## 12. Project Author

**Dharma Pradeep Gunisetty**

GitHub: https://github.com/Pradeepnryn

**Note:** CATE is an ongoing experimental project. Reported performance may change as the dataset, evaluation methodology and model are improved.
