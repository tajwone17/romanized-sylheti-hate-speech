# SylHate: Romanized Sylheti Hate Speech Dataset

This repository contains a Romanized Sylheti hate speech dataset, a curated stopword list, and the baseline code used for experimentation on this task.

---

## Overview

Romanized Sylheti is a low-resource, informal, and highly variable dialect commonly used on social media. This project provides the first publicly organized dataset and baseline workflow for hate speech detection in Romanized Sylheti.

The repository includes:

- A manually labeled dataset of 7,054 Romanized Sylheti comments
- A custom stopword list of 157 terms
- Preprocessing and feature engineering scripts
- Classical machine learning baselines
- A multilingual transformer baseline using mBERT
- Reproducible notebooks for training and evaluation

---

## Conference and Author Information

The work was prepared for the following conference context:

- IEEE 3rd International Conference on Computing, Applications and Systems (COMPAS 2026)
- Date: 9–10 October 2026
- Venue: University of Dhaka, Bangladesh

### Authors

- Jakaria Chowdhury Tajwone  
  Department of CSE, North East University Bangladesh, Sylhet, Bangladesh  
  0562310005101031@neub.edu.bd

- Mst. Fahimajjman Jaina  
  Department of CSE, North East University Bangladesh, Sylhet, Bangladesh  
  0562310005101045@neub.edu.bd

- Snehasish Saha Roy Akash  
  Department of CSE, North East University Bangladesh, Sylhet, Bangladesh  
  0562310005101040@neub.edu.bd

- Arif Ahmad  
  Department of CSE, North East University Bangladesh, Sylhet, Bangladesh  
  arif@neub.edu.bd

---

## Dataset

The full dataset is stored in the repository under:

- `Dataset/romanized_sylheti_hate_speech.csv`
- `Dataset/romanized_sylheti_stopwords.txt`

### Dataset statistics

| Split       |   Hate Speech | Non-Hate Speech | Total |
| ----------- | ------------: | --------------: | ----: |
| Train (80%) |         3,024 |           2,619 | 5,643 |
| Test (20%)  |           756 |             655 | 1,411 |
| Total       | 3,780 (53.6%) |   3,274 (46.4%) | 7,054 |

### Data sources

- 3,044 samples converted from a Bangla regional hate speech dataset into Romanized Sylheti
- 4,010 Facebook comments collected manually from public pages and discussions

### Annotation protocol

The annotation work was conducted by two native Sylheti speakers.

- Label `1`: hate speech
- Label `0`: non-hate speech

The dataset includes consistent label assignment and was checked for duplicate and near-duplicate content.

---

## Stopword List

The repository includes a curated Romanized Sylheti stopword list:

- `Dataset/romanized_sylheti_stopwords.txt`

This list contains 157 stopwords and was built from corpus-based frequency analysis and reviewed by native speakers. It was specifically designed to keep function words while excluding words that may carry hateful or semantic meaning.

The stopword generation workflow is available in:

- `codes/SylHeti_Stopword_Generator.ipynb`

The stopword list was created to support preprocessing for this dataset and can be used in experiments or future research.

---

## Code and Experiments

The main experimental pipeline is in:

- `codes/sylheti_hate_speech_detection.ipynb`

The notebook covers:

- Dataset loading and preprocessing
- Cleaning and normalization of Romanized Sylheti text
- Stopword filtering
- Feature extraction using CountVectorizer and TF-IDF
- Word n-grams and character n-grams
- Training on multiple machine learning models
- Fine-tuning a multilingual transformer baseline (mBERT / bert-base-multilingual-cased)
- Evaluation and comparison between classical models and transformer results

### Models evaluated

- Logistic Regression
- Support Vector Machine (SVM)
- Random Forest
- Bernoulli Naive Bayes
- Multinomial Naive Bayes
- Decision Tree
- Gaussian Naive Bayes
- K-Nearest Neighbors
- mBERT transformer baseline

### Transformer baseline

The repository also includes a transformer-based experiment using `bert-base-multilingual-cased`, trained on the same dataset for comparison with the traditional ML pipelines.

---

## Repository Structure

```text
romanized-sylheti-hate-speech/
├── README.md
├── Dataset/
│   ├── romanized_sylheti_hate_speech.csv
│   └── romanized_sylheti_stopwords.txt
├── codes/
│   ├── sylheti_hate_speech_detection.ipynb
│   └── SylHeti_Stopword_Generator.ipynb
├── Figures/
│   └── (visuals and result plots)
└── LICENSE
```

---

## Setup

This project is implemented in Python, primarily using Jupyter notebooks and standard scientific libraries.

Recommended dependencies:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
```

Open the notebook in `codes/sylheti_hate_speech_detection.ipynb` to reproduce the full pipeline.

---

## License

This project is released for academic and research use. Please refer to the repository license and dataset usage terms when reusing the materials.

---

## Contact

For questions regarding the dataset, methodology, or project usage, contact the authors listed above.
