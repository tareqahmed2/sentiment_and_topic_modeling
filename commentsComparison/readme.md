# 💬 Comments Analysis (YouTube Audience Feedback)

## 📁 Folder: `commentsComparison`

This module analyzes **YouTube comments data** to understand audience opinions using:

* Sentiment Analysis
* Topic Modeling
* Text Processing

---

## 🎯 Objective

The goal of this analysis is to:

* Understand audience feedback on videos
* Identify sentiment distribution
* Discover common discussion topics
* Extract insights from user comments

---

## 📂 Dataset

| File                                  | Description                 |
| ------------------------------------- | --------------------------- |
| `English_translated_comment_data.csv` | Translated YouTube comments |

📊 Dataset Size:

* Total comments: **257,497**

---

## ⚙️ Processing Pipeline

```text
Load Data → Clean Text → Sentiment Analysis → Topic Modeling → Visualization → Save Output
```

---

## 🔍 Analysis Steps

### 1️⃣ Text Cleaning

* Convert text to lowercase
* Remove URLs
* Remove special characters
* Remove extra spaces
* Remove empty rows

---

### 2️⃣ Sentiment Analysis

* Tool: `TextBlob`
* Metrics:

  * Polarity (-1 to +1)
  * Subjectivity (0 to 1)
* Classification:

  * Positive
  * Neutral
  * Negative

---

## 📊 Sentiment Results

### 🔢 Count

| Sentiment | Count   |
| --------- | ------- |
| Neutral   | 179,827 |
| Positive  | 62,306  |
| Negative  | 14,081  |

---

### 📊 Percentage

| Sentiment | Percentage |
| --------- | ---------- |
| Neutral   | 70.19%     |
| Positive  | 24.32%     |
| Negative  | 5.50%      |

---

### 🔍 Insight

* Most comments are **neutral**
* Positive feedback is significant
* Negative feedback is relatively low

---

### 3️⃣ Polarity Distribution

* Shows distribution of sentiment intensity
* Most values are around **0 (neutral)**

---

### 4️⃣ Topic Modeling (LDA)

* Model: Latent Dirichlet Allocation
* Number of topics: 3

---

### 🔑 Top Words per Topic

* **Topic 0:** love, tantrik, mir, heart
* **Topic 1:** story, suspense, smiling, face
* **Topic 2:** golpo, kore, priyabrata

---

### 🏷️ Topic Labels

| Topic | Meaning                |
| ----- | ---------------------- |
| 0     | Positive Feedback      |
| 1     | Requests / Suggestions |
| 2     | Emotional Response     |

---

## 📊 Topic Results

### 🔢 Count

| Topic                | Count  |
| -------------------- | ------ |
| Requests/Suggestions | 93,254 |
| Positive Feedback    | 90,174 |
| Emotional Response   | 72,786 |

---

### 📊 Percentage

| Topic                | Percentage |
| -------------------- | ---------- |
| Requests/Suggestions | 36.40%     |
| Positive Feedback    | 35.19%     |
| Emotional Response   | 28.41%     |

---

### 🔍 Insight

* Requests and suggestions are most common
* Positive feedback is nearly equal
* Emotional responses are also significant

---

## 📈 Output Files

| File                         | Description                            |
| ---------------------------- | -------------------------------------- |
| `comments_full_analysis.csv` | Full dataset with sentiment and topics |
| `sentiment_count.csv`        | Sentiment counts                       |
| `sentiment_percentage.csv`   | Sentiment percentages                  |
| `topic_count.csv`            | Topic counts                           |
| `topic_percentage.csv`       | Topic percentages                      |
| `sentiment_distribution.png` | Sentiment graph                        |
| `polarity_distribution.png`  | Polarity graph                         |
| `topic_distribution.png`     | Topic graph                            |

---

## 🧠 Key Insights

* Audience feedback is mostly neutral
* Positive sentiment is strong
* Low negativity indicates audience satisfaction
* Topic analysis shows active engagement and feedback

---

## 🎓 Project Context

This module is part of a **YouTube Channel Comparative Analysis System**, which includes:

* Comments Analysis
* Live Chat Analysis
* Video Performance Analysis
* Graph-Based Analysis

---

## ✅ Status

✔ Data cleaned
✔ Sentiment analysis completed
✔ Topic modeling completed
✔ Results saved

---

## 👨‍💻 Author

Developed for academic research on audience behavior and sentiment analysis.
