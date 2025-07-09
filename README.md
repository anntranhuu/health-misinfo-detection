# 🩺 Health Misinformation Detection in Online News

## 🧠 Project Overview

This project investigates the use of machine learning techniques to classify **health misinformation** in online news articles. The models were trained on real-world annotated news reviews from [HealthNewsReview.org](https://healthnewsreview.org), using both a traditional **Multinomial Naive Bayes (MNB)** classifier and the transformer-based **SciBERT** model. This work was completed as part of my MSc Applied Data Science dissertation and awarded the **Townsend Prize** for achieving the highest mark in the cohort.

---

## 🎯 Objectives

- Classify health news articles as *satisfactory* or *unsatisfactory* based on 10 health misinformation criteria.
- Compare performance between a lightweight **Naive Bayes model** and a domain-specific **SciBERT transformer**.
- Explore the impact of feature extraction, hyperparameter tuning, and text characteristics on model performance.
- Investigate how language patterns (e.g., uncertainty words) correlate with misinformation.

---

## 📂 Dataset

- **Source**: [FakeHealth repository](https://github.com/EnyanDai/FakeHealth)
- **Subset used**: `HealthStory`
- **Size**: 1,180 reviewed articles from 40+ US media outlets
- **Labels**: Binary labels — *Satisfactory* vs *Unsatisfactory* based on expert reviews

---

## ⚙️ Methods & Technologies

- **Languages**: Python  
- **Libraries**: `scikit-learn`, `transformers`, `PyTorch`, `NLTK`, `Matplotlib`, `Seaborn`  
- **Models Used**:
  - 🔹 **Multinomial Naive Bayes** with Bag-of-Words & TF-IDF
  - 🔹 **SciBERT** fine-tuned using Hugging Face Transformers  
- **Metrics**: Weighted **Precision**, **Recall**, **F1 Score**, and **Accuracy**

---

## 📈 Key Results

| Model                  | Weighted F1 | Unsatisfactory F1 | Satisfactory F1 |
|-----------------------|-------------|--------------------|------------------|
| **Random Baseline**   | 0.50        | 0.00               | 0.67             |
| **Naive Bayes (Final)** | 0.66      | 0.36               | 0.77             |
| **SciBERT (Final)**     | **0.72**  | **0.49**           | **0.81**         |

- **SciBERT outperformed** Naive Bayes overall, particularly for identifying misinformation.
- **Bag-of-Words** outperformed TF-IDF, likely due to the value of common comparison and uncertainty terms.
- Adjusting stopword lists and thresholds modestly improved performance on the minority class.

---

## 🔍 Insights

- Articles labeled *satisfactory* were significantly longer and used more uncertainty/modality words (e.g., *might*, *could*).
- Feature engineering decisions (e.g., keeping uncertainty words) had a noticeable impact on recall for misinformation.
- SciBERT showed signs of overfitting in training but **generalised well** on the test set.

---

## 💡 What I Learned

- How to fine-tune and compare transformer models for text classification  
- Challenges of working with **imbalanced datasets** in sensitive contexts  
- Importance of interpretability when dealing with real-world misinformation  
- Best practices for **evaluating binary classifiers** beyond simple accuracy  
- Leveraging domain-specific embeddings (SciBERT) for nuanced detection tasks

---

## 🗂️ Project Structure

📦 health-misinformation-detection/  
┣ 📄 MA981_Dissertation_2322761.pdf ← Full academic report with analysis and results  
┣ 📄 README.md ← This file  
┗ 📁 /models/ ← Model files

---

## 🤝 Acknowledgements
Data provided by FakeHealth

News article reviews by HealthNewsReview.org

Developed as part of the MSc Applied Data Science at the University of Essex
