
# NBA Tweets Sentiment Analysis and Retrieval

This project provides a **sentiment analysis** and **text retrieval** system based on NBA fans' tweets, using traditional NLP models.

## ✨ Features

- **Data Preprocessing**: Clean and normalize tweet texts.
- **Sentiment Classification**: Classify tweets into `positive`, `neutral`, or `negative` using TF-IDF + Naive Bayes.
- **Text Retrieval**: Retrieve the most relevant tweets for a query using N-gram + cosine similarity.
- **Model Saving**: Persist trained models (`joblib`) for reuse.

---

## 🗂 Project Structure

```
├── nbadataset.csv                     # Raw dataset (Tweets from 12-07-2020 to 19-09-2020)
├── sentiment_tfidf_nb.pkl              # Trained sentiment analysis model
├── ngram_vectorizer.pkl                # Trained N-gram vectorizer
├── ngram_matrix.npz                    # Precomputed N-gram matrix
├── main.py                             # Main source code (your provided script)
└── README.md                           # Project documentation
```

---

## 📚 Requirements

Install dependencies:

```bash
pip install pandas scikit-learn numpy scipy joblib
```

Recommended Python version: **Python 3.8+**

---

## 🚀 Usage

1. **Clone the repository**

```bash
git clone https://github.com/yourusername/nba-sentiment-retrieval.git
cd nba-sentiment-retrieval
```

2. **Run the script**

```bash
python main.py
```

It will automatically:
- Train a sentiment classifier
- Save the models
- Perform sample sentiment predictions
- Perform sample text retrieval queries

---

## 🛠 How It Works

### 1. Data Preprocessing
- Remove URLs, mentions, non-alphabet characters
- Lowercase all text
- Remove stopwords

### 2. Sentiment Analysis
- `TfidfVectorizer` with 1-2 grams (`max_features=10000`)
- `Multinomial Naive Bayes` classifier
- Output metrics: Precision, Recall, F1-score, Confusion matrix

### 3. Text Retrieval
- `CountVectorizer` with 2-3 grams
- Precompute sparse matrix
- Retrieval by cosine similarity between query and all tweets

---

## 📈 Example Output

### Sentiment Classification

| Text Example | Predicted Sentiment |
| :--- | :--- |
| The Lakers are unstoppable tonight! | Positive |
| I can't believe how bad that refereeing was. | Negative |
| Neutral comment about the game. | Neutral |

### Text Retrieval Example

```
Query: Lakers versus Suns highlights
Top 3 Matches:
0.755 | Lakers played outstanding against Suns yesterday...
0.732 | Full match analysis: Lakers vs Suns playoff series...
0.701 | What a night for Lakers' fans after beating the Suns...
```

---

