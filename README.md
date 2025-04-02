Movie Genre Classification
This repository contains code for a multi-label movie genre classification project. We fine-tune a BERT-based model to predict multiple genres from movie summaries. Our approach tackles label imbalance with a weighted loss function and includes dynamic threshold tuning and confusion matrix analysis for thorough evaluation.

Overview
Movie genre classification is a challenging multi-label task where a single movie may belong to several genres. This project covers:

Data Cleaning & Preprocessing:
Cleaning raw movie metadata and extracting genre information from various formats (pipe-separated strings or string representations of dictionaries).

Label Encoding:
Converting genre lists into multi-hot vectors using MultiLabelBinarizer.

Model Training:
Fine-tuning a BERT-based model (bert-base-uncased) using a custom weighted loss function to address label imbalance.

Evaluation:
Dynamic threshold tuning to optimize the F1 score and generating confusion matrices for in-depth analysis.

├── README.md
├── train_movies_metadata.csv    # Raw movie metadata CSV
├── data_preprocessing.py        # Data cleaning and preprocessing script
├── train_model.py               # Model training script
├── evaluate_model.py            # Evaluation and threshold tuning script
├── img/                         # Folder for confusion matrix images
└── requirements.txt             # List of dependencies

Optimal Threshold:
Through threshold tuning, we determined that a global threshold of 0.70 maximizes the micro F1 score.

Evaluation Metrics (at threshold 0.70):

Subset (Exact Match) Accuracy: ~17–20%

Precision: ~52%

Recall: ~63%

F1 Score: ~57%

Confusion Matrix Analysis:
Confusion matrices were generated for each genre to identify high misclassification rates, particularly for underrepresented genres.

Discussion
Our results indicate that:

Performance:
While subset accuracy remains low due to the strict exact-match requirement in multi-label tasks, per-label performance is reasonable (F1 ~57%).

Weighted Loss Impact:
The custom weighted loss improved detection of rare genres, though the model still over-predicts some labels, affecting precision.

Challenges & Future Work:

Threshold Tuning & Calibration: Further work on per-label thresholds and model calibration (e.g., temperature scaling) could improve performance.

Data Augmentation: Utilizing larger, more diverse datasets or data augmentation techniques might help the model generalize better.

Ensembling & Additional Modalities: Combining multiple models or incorporating extra information (e.g., cast, visuals) could further enhance genre classification.
