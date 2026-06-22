# BlogMiner — Automated Blog Analysis & NLP Pipeline

**NED University of Engineering & Technology**
Department of Computer Science & Information Technology
Course: CT-377 Data Mining | Fall 2025

---

## Project Overview

BlogMiner is a complete end-to-end data mining pipeline built in Python (Jupyter Notebook) that:

1. Takes a keyword from the user (e.g., `"machine learning"`)
2. Scrapes 10 blog posts from **dev.to**, **GeeksforGeeks**, and **FreeCodeCamp**
3. Cleans and preprocesses all text using NLP techniques
4. Extracts keywords, discovers topics, analyzes tone, and infers blog motive
5. Runs sentiment analysis on reader comments using VADER
6. Generates 5 charts + 1 word cloud
7. Auto-generates a personalized comment per article using **DistilGPT-2** (HuggingFace)

---

## Pipeline Phases

| Phase | Description | Key Libraries |
|-------|-------------|---------------|
| **1 — Data Collection** | DuckDuckGo search + BeautifulSoup scraping | `ddgs`, `requests`, `bs4` |
| **2 — Preprocessing** | Lowercase, remove HTML/URLs/stopwords, lemmatize | `nltk` |
| **3 — NLP Analysis** | TF-IDF keywords, LDA topics, TextBlob tone, motive inference | `sklearn`, `textblob` |
| **4 — Sentiment Analysis** | VADER on comments, popularity proxy via comment count | `vaderSentiment` |
| **5 — Visualization** | 5 charts + word cloud saved to `output/` | `matplotlib`, `seaborn`, `wordcloud` |
| **6 — Comment Generation** | DistilGPT-2 generates a context-aware comment per article | `transformers`, `torch` |

---

## Sample Output (Keyword: "machine learning")

**Sentiment Distribution**
- 40% Positive, 60% Neutral across all scraped comments

**Dominant Blog Motive**
- 8 out of 9 articles classified as Tutorial, 1 as Promotional

**Top TF-IDF Keywords**
`algorithm`, `model`, `data`, `learning`, `clustering`, `supervised`, `prediction`, `sklearn`

**AI-Generated Comment Sample**
> *"This tutorial on 'What is Machine Learning' breaks down a complex topic clearly — the
> step-by-step structure makes it accessible for beginners and experienced practitioners alike."*

---

## Notes

- **No API key required** — uses DuckDuckGo (free) and DistilGPT-2 (local)
- First run downloads the DistilGPT-2 model (~330 MB) automatically
- For articles with no scrapable comments, meaningful sentences from the article
  body are used as a proxy for sentiment analysis
- The HuggingFace unauthenticated warning on Phase 6 is harmless and does not
  affect output

---

## Technologies Used

`Python 3.10` · `Jupyter Notebook` · `NLTK` · `Scikit-learn` · `TextBlob` · `VADER` ·
`HuggingFace Transformers` · `DistilGPT-2` · `Matplotlib` · `Seaborn` · `WordCloud` ·
`BeautifulSoup` · `DuckDuckGo Search`
