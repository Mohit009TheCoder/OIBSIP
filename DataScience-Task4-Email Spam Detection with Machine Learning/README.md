# Task 4: Email Spam Detection with Machine Learning

This folder contains a Natural Language Processing (NLP) binary classification pipeline built to distinguish spam messages from legitimate (ham) ones.

## Project Overview
- **Tech Stack**: Python, `pandas`, `numpy`, `scikit-learn`, `nltk`, `matplotlib`, `seaborn`, `wordcloud`
- **Data Engineering**: Implemented a text cleaning pipeline to lowercase letters, remove punctuation, extract alphanumeric symbols, strip stopwords, and stem words using NLTK's `PorterStemmer`.
- **Feature Extraction**: Used `TfidfVectorizer` (TF-IDF) to convert textual data into sparse vector representation.
- **Classification Models**: Trained and evaluated Multinomial Naive Bayes (MultinomialNB) and Linear Support Vector Classifier (SVC).
- **Best Model**: **Support Vector Machine (Linear SVC)** achieved a **98.12% accuracy** and a high **92.47% F1-Score**.

---

## Preprocessing Pipeline
The raw messages are cleaned using NLTK text processing:
1. **Case Conversion**: Shift all text to lowercase.
2. **Special Character Removal**: Use regex (`[^a-z\s]`) to remove digits, punctuation, and emojis.
3. **Stopword Elimination**: Strip common English helper words (e.g. "is", "the", "and") using NLTK's `stopwords` corpus.
4. **Stemming**: Reduce words to their base roots (e.g. "freeing", "freely" -> "free") using Porter Stemmer.

---

## Classification Performance Comparison

| Model | Test Accuracy | Test Precision (Spam) | Test Recall (Spam) | Test F1-Score |
| :--- | :---: | :---: | :---: | :---: |
| **Linear SVM (SVC)** | **98.12%** | **99.23%** | **86.58%** | **92.47%** |
| **Multinomial Naive Bayes** | 96.77% | 99.13% | 76.51% | 86.36% |

- **Precision vs. Recall Focus**: Legitimate emails misclassified as spam (False Positives) represent a major issue, as users may miss critical correspondence. Thus, **Precision is the most critical metric** in spam filtering. Both models achieved ~99.2% Precision, indicating high quality of spam flags.

---

## File Deliverables
- `spam_detection.ipynb`: Pre-rendered Jupyter Notebook containing data loading, pre-processing, EDA, tf-idf vectorization, model training, evaluation heatmaps, WordClouds, and metric discussions.
- `spam.csv`: Local SMS Spam dataset (5,572 messages).
- `README.md`: This reference sheet.

---

## How to Run

1. Clone or navigate to this folder.
2. Install dependencies:
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn wordcloud nltk notebook
   ```
3. Run the Jupyter environment:
   ```bash
   jupyter notebook
   ```
4. Open `spam_detection.ipynb` and run all cells.
