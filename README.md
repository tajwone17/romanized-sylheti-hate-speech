# Romanized Sylheti Hate Speech Dataset

This repository contains the dataset, stopword list, and baseline code for the paper:

> **Hate Speech Detection in Romanized Sylheti: A Baseline Study Using Machine Learning**  
> [Author Names] — [Conference Name, Year]

---

## Dataset

The dataset contains **7,054 manually annotated social media samples** in Romanized Sylheti (Sylheti written in Latin script).

| Split | Hate Speech | Non-Hate Speech | Total |
|-------|-------------|-----------------|-------|
| Train (80%) | 3,025 | 2,618 | 5,643 |
| Test (20%) | 756 | 655 | 1,411 |
| **Total** | **3,781 (53.6%)** | **3,273 (46.4%)** | **7,054** |

### Sources
- **3,044 samples**: Converted from the [BIDWESH dataset](https://arxiv.org/abs/2507.16183) into Romanized Sylheti
- **4,010 samples**: Directly collected from Facebook

### Annotation
All samples were manually labeled by two native Sylheti speakers following [Facebook's Community Standards](https://transparency.fb.com/policies/community-standards/hate-speech/).  
- `1` = Hate speech  
- `0` = Non-hate speech

---

## Stopword List

`dataset/romanized_sylheti_stopwords.txt` contains **157 Romanized Sylheti stopwords** built through corpus frequency analysis and reviewed by native speakers.

---

## Code

`code/sylheti_hate_speech_detection.ipynb` contains the full pipeline:
- Data loading and preprocessing
- Feature extraction (CountVectorizer, TF-IDF, word and character n-grams)
- Training and evaluation of 10 ML models
- Results tables and figures

### Requirements