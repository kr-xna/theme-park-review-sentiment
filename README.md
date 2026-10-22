# Theme Park Review Sentiment & Topic Modelling

Turning thousands of free-text visitor reviews into two clear business signals: **how guests feel** about each park branch, and **what they talk about** most.

## Overview

| Question | Technique |
| --- | --- |
| Which branches get the most reviews? | Exploratory counts by branch |
| How positive is each branch's feedback? | TextBlob polarity scoring, averaged per branch |
| What words dominate reviews overall? | Word cloud with English stop words removed |
| What are the recurring themes? | Latent Dirichlet Allocation (LDA), 5 topics, top 10 words each |

## Pipeline

1. Load reviews and drop empty entries.
2. Score each review's sentiment polarity (−1 = negative, +1 = positive).
3. Compare average sentiment across branches.
4. Tokenise, lower-case and strip stop words and punctuation.
5. Build a document–term matrix and fit an LDA topic model.
6. Print the top keywords for each topic for interpretation.

## Getting started

```bash
git clone https://github.com/kr-xna/theme-park-review-sentiment.git
cd theme-park-review-sentiment
pip install -r requirements.txt
python theme_park_reviews.py
```

Place `ThemeParkReviews.csv` in the project folder first. It needs at least two columns: `Branch` and `Review_Text`. The dataset is not included in this repository. NLTK downloads its tokeniser and stop-word data on first run.

## Tech stack

Python · pandas · NLTK · TextBlob · scikit-learn (LDA) · WordCloud · Matplotlib · seaborn

---

Built for the *Advanced AI for Business* unit of the Master of Business Analytics at Deakin University.
