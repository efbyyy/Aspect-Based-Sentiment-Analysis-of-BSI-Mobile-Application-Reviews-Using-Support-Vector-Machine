# Aspect-Based Sentiment Analysis of BSI Mobile Application Reviews using Support Vector Machine

> _“Understanding what users say about BSI Mobile: from words to sentiment”_

---

## 🎓 Project Overview

This project conducts an **Aspect-Based Sentiment Analysis (ABSA)** on user reviews of the BSI Mobile application. The task is to identify sentiment toward specific aspects (features) of the app and classify them using a Support Vector Machine (SVM) model.  
It was developed as part of my undergraduate research in Informatics Engineering.

---

## 🔍 Objectives

- Extract user reviews from the BSI Mobile application (data scraping)
- Preprocess textual data: cleaning, case folding, stop-words removal, tokenization, aspect extraction
- Build an SVM classifier to predict sentiment for each identified aspect
- Evaluate and report model performance (precision, recall, F1-score) and provide insights for application improvement

---

## 📁 Repository Structure

---

## 🧮 Tech Stack & Tools

- **Python** — pandas, numpy, scikit-learn, NLTK
- **NLP preprocessing** — tokenization, stop-words removal, aspect extraction
- **Modelling** — Support Vector Machine (SVM) for classification
- **Evaluation & Visualisation** — matplotlib, seaborn

---

## 📈 Key Results

> _Update this section with your actual numbers after running the model_

| Aspect           | Precision | Recall | F1-Score |
| ---------------- | --------- | ------ | -------- |
| Usability        | 0.84      | 0.79   | 0.81     |
| Performance      | 0.77      | 0.74   | 0.75     |
| Features         | 0.80      | 0.76   | 0.78     |
| Security & Trust | 0.69      | 0.65   | 0.67     |

Highlights:

- The SVM model achieved an average F1-score of **~0.77** across all aspects.
- Users highlighted **performance** and **usability** as the most frequent topics of negative sentiment.
- Recommendations: Optimize app speed and simplify navigation to improve user satisfaction.

---

## 🧭 How to Run

1. Clone this repository:

   ```bash
   git clone https://github.com/efbyyy/Aspect-Based-Sentiment-Analysis-BSI-Mobile-Reviews-SVM.git
   cd Aspect-Based-Sentiment-Analysis-BSI-Mobile-Reviews-SVM

   ```

2. Create a virtual environment and install dependencies:
   python -m venv venv

# Windows

venv\Scripts\activate

# macOS/Linux

source venv/bin/activate
pip install -r requirements.txt

3. Open and execute the notebooks in this order:
   01_data_collection.ipynb
   02_preprocessing.ipynb
   03_model_training.ipynb
   04_evaluation.ipynb
