Movie Genre Classification
This repository contains code for a multi-label movie genre classification project. We fine-tune a BERT-based model for multi-label classification of movie genres based on textual summaries. Our approach addresses the challenges of label imbalance using a weighted loss function, and we further evaluate the model with dynamic threshold tuning and confusion matrix analysis.

Overview
Movie genre classification is a challenging multi-label task where a single movie may belong to several genres. This project covers:

Data Cleaning & Preprocessing:
Cleaning raw movie metadata and extracting genre information from various formats (pipe-separated strings or string representations of dictionaries).

Label Encoding:
Using the MultiLabelBinarizer to convert genre lists into multi-hot vectors.

Model Training:
Fine-tuning a BERT-based model (bert-base-uncased) using a custom weighted loss function to tackle label imbalance.

Evaluation:
Dynamic threshold tuning to optimize the F1 score, along with generating confusion matrices for in-depth analysis.

*Project Structure* 
├── README.md
├── train_movies_metadata.csv    # Raw movie metadata CSV
├── data_preprocessing.py        # Data cleaning and preprocessing script
├── train_model.py               # Model training script
├── evaluate_model.py            # Evaluation and threshold tuning script
├── img/                         # Folder for confusion matrix images

Results
Optimal Threshold:
Through threshold tuning, we determined that a global threshold of 0.70 maximizes the micro F1 score.

Evaluation Metrics (at threshold 0.70):

Subset (Exact Match) Accuracy: ~17-20%

Precision: ~52%

Recall: ~63%

F1 Score: ~57%

Confusion Matrix Analysis:
Confusion matrices were generated for each genre to identify areas of high misclassification, particularly for underrepresented genres.

Discussion
Our results indicate that while subset accuracy remains low due to the strict exact-match requirement, the model performs reasonably well on a per-label basis. The weighted loss function improved performance on rare genres, but further improvements are needed. Future work may include:

Per-label threshold tuning and model calibration (e.g., temperature scaling).

Data augmentation and using larger, more diverse datasets.

Ensembling techniques to further boost performance.

Exploring additional modalities (e.g., cast, visuals) for enhanced genre classification.


