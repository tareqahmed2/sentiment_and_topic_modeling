# 🔴 Live Chat Comparative Analysis (Ch-1 vs Ch-2)

## 📁 Folder: `liveComparison`

This module analyzes **YouTube live chat data** to compare audience behavior between two channels (**Ch-1 and Ch-2**) using:

* Sentiment Analysis
* Topic Modeling
* Channel-wise comparison

---

## 🎯 Objective

The purpose of this analysis is to:

* Understand real-time audience reactions
* Compare emotional engagement between channels
* Identify common discussion topics in live chat

---

## 📂 Dataset

| File                                    | Description                                |
| --------------------------------------- | ------------------------------------------ |
| `English_translated_live_chat_data.csv` | Live chat messages (translated to English) |

📊 Dataset Size:

* Total rows: **290,548 messages**

---

## ⚙️ Processing Pipeline

```text
Load Data → Clean Text → Sentiment Analysis → Topic Modeling → Channel Comparison → Visualization → Save Output
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

### 📊 Sentiment Results

#### 🔢 Count

| Channel | Negative | Neutral | Positive |
| ------- | -------- | ------- | -------- |
| Ch-1    | 9,965    | 154,852 | 19,439   |
| Ch-2    | 4,105    | 91,420  | 8,623    |

---

#### 📊 Percentage

| Channel | Negative | Neutral | Positive |
| ------- | -------- | ------- | -------- |
| Ch-1    | 5.40%    | 84.04%  | 10.55%   |
| Ch-2    | 3.94%    | 87.77%  | 8.28%    |

---

### 🔍 Insight

* Neutral sentiment dominates live chat
* Ch-1 shows higher interaction volume
* Ch-2 has slightly lower negativity

---

### 3️⃣ Topic Modeling (LDA)

* Model: Latent Dirichlet Allocation
* Number of topics: 3

---

### 🔑 Top Words per Topic

* **Topic 0:** hii, ami, laughing, rolling
* **Topic 1:** nice, ghost, ki, tumi
* **Topic 2:** heart, joy, smiling, face

---

### 🏷️ Topic Labels

| Topic | Meaning                |
| ----- | ---------------------- |
| 0     | Positive Feedback      |
| 1     | Requests / Suggestions |
| 2     | Emotional Response     |

---

### 📊 Topic Distribution

| Channel | Emotional | Positive | Requests |
| ------- | --------- | -------- | -------- |
| Ch-1    | 58,416    | 74,797   | 51,043   |
| Ch-2    | 23,546    | 36,073   | 44,529   |

---

### 🔍 Insight

* Positive feedback is dominant
* Emotional expressions are common
* Ch-1 has higher activity across all topics

---

## 📈 Output Files

| File                        | Description                          |
| --------------------------- | ------------------------------------ |
| `live_full_analysis.csv`    | Full dataset with sentiment & topics |
| `sentiment_count.csv`       | Sentiment counts                     |
| `sentiment_percentage.csv`  | Sentiment percentages                |
| `topic_count.csv`           | Topic distribution                   |
| `sentiment_comparison.png`  | Sentiment graph                      |
| `polarity_distribution.png` | Polarity distribution graph          |
| `topic_comparison.png`      | Topic comparison graph               |

---

## 🧠 Key Insights

* Live chat reflects **real-time audience emotions**
* Most messages are neutral or short interactions
* Positive reactions dominate over negative ones
* Ch-1 has higher engagement volume

---

## 🎓 Project Context

This module is part of a **YouTube Channel Comparative Analysis System**, which includes:

* Comments Analysis
* Live Chat Analysis
* Video Performance Analysis
* Graph-Based Analysis

---

## ✅ Status

✔ Live data processed
✔ Sentiment analysis completed
✔ Topic modeling completed
✔ Channel comparison generated

---

## 👨‍💻 Author

Developed for academic research on audience behavior and engagement in YouTube live streams.
