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
pip install scikit-learn pandas numpy matplotlib seaborn
---

## Results

Best result: **Logistic Regression** with character 4-gram CountVectorizer features on preprocessed text.

| Model | Accuracy | F1-Score |
|-------|----------|----------|
| Logistic Regression | 0.8356 | 0.8358 |
| SVM | 0.8271 | 0.8272 |
| Bernoulli NB | 0.8214 | 0.8214 |

---

## Citation

If you use this dataset or code, please cite:

```bibtex
@inproceedings{yourkey2025,
  author    = {Your Names},
  title     = {Hate Speech Detection in Romanized {Sylheti}:
               A Baseline Study Using Machine Learning},
  booktitle = {[Conference Name]},
  year      = {2025}
}
```

---

## License

The dataset is released under [Creative Commons Attribution 4.0 (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).  
The code is released under the [MIT License](LICENSE).