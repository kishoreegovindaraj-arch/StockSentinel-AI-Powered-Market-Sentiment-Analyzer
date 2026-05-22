# 📈 StockSentinel – AI-Powered Market Sentiment Analyzer

StockSentinel is a complete, end-to-end Machine Learning application designed to analyze and predict financial market sentiment from textual data (tweets, financial news, and stock comments). By combining traditional NLP TF-IDF features with lexical sentiment scores from VADER and TextBlob, the system achieves robust classification performance via a tuned Logistic Regression model.

The project features a sleek, interactive web interface built using **Streamlit**, making real-time sentiment analysis accessible to traders and analysts alike.

---

## 📊 Key Performance Metrics

The underlying machine learning model was optimized using hyperparameter tuning (`GridSearchCV`) and yielded the following evaluation results on the test split:

* **Overall Accuracy:** **80.59%**
* **Class -1 (Negative):** Precision: `0.74` | Recall: `0.71` | F1-Score: `0.73`
* **Class 1 (Positive):** Precision: `0.84` | Recall: `0.86` | F1-Score: `0.85`

---

## 🛠️ Tech Stack & Architecture

* **Frontend UI:** Streamlit
* **Core Machine Learning:** Scikit-Learn (Logistic Regression, GridSearchCV, TfidfVectorizer)
* **Natural Language Processing:** NLTK, TextBlob, VADER Sentiment Intensity Analyzer
* **Data Manipulation:** Pandas, NumPy, SciPy (Sparse Matrices)
* **Model Serialization:** Joblib

### Feature Engineering Pipeline
To capture both semantic meaning and emotional context, the feature pipeline utilizes a hybrid approach:
1. **TF-IDF Vectorization:** Extracts unigrams and bigrams (`ngram_range=(1,2)`) capped at the top 6,000 features from cleaned, lemmatized text.
2. **Lexicon Sentiment Scores:** Computes VADER compound scores along with TextBlob polarity and subjectivity features.
3. **Feature Stacking:** Horizontally stacks sparse text features and dense numerical scores into a single unified matrix ($X$).

---

## 🚀 Getting Started

### Prerequisites
Make sure you have Python 3.10+ installed on your system.

### 1. Clone the Repository
```bash
git clone [https://github.com/YOUR_USERNAME/StockSentinel.git](https://github.com/YOUR_USERNAME/StockSentinel.git)
cd StockSentinel

### 2. Install Dependencies
pip install -r requirements.txt



### 3. Download NLTK Corpora
Run a quick Python snippet to download the necessary text processing resources:

Python
import nltk
nltk.download('stopwords')
nltk.download('wordnet')


### 4. Run the Streamlit Application
Bash
streamlit run app.py

Open the local URL provided in your terminal (usually http://localhost:8501) in your browser to interact with the app.

Author
Kishore G
