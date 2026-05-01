# 📊 YouTube Channel Comparative Analysis (Final System)

## 📁 Folder: `finalComparison`

This module performs a **comprehensive comparative analysis of two YouTube channels (Ch-1 vs Ch-2)** by integrating:

* 💬 Comments
* 🔴 Live Chat
* 🎥 Video Metadata

The system combines **sentiment analysis, topic modeling, and performance metrics** into a unified comparison framework.

---

## 🎯 Objective

The goal of this system is to:

* Compare audience behavior across two channels
* Analyze sentiment from both comments and live chat
* Identify dominant discussion topics
* Evaluate channel performance using video metrics

---

## 📂 Input Datasets

| File                                        | Description        |
| ------------------------------------------- | ------------------ |
| `English_translated_comment_data.csv`       | Video comments     |
| `English_translated_live_chat_data.csv`     | Live chat messages |
| `English_translated_video_informationt.csv` | Video statistics   |

---

## ⚙️ Processing Pipeline

```text
Load Data → Clean Text → Sentiment Analysis → Topic Modeling → Channel Comparison → Visualization → Save Output
```

---

## 🔍 Analysis Components

### 1️⃣ Text Cleaning

* Lowercasing
* Removing URLs
* Removing special characters
* Removing empty text

---

### 2️⃣ Sentiment Analysis

* Tool: `TextBlob`
* Output:

  * Positive
  * Neutral
  * Negative

✔ Applied on both:

* Comments
* Live chat

---

### 3️⃣ Combined Sentiment Analysis

```text
Comments Sentiment + Live Sentiment → Combined Sentiment
```

### 📊 Result:

| Channel | Negative | Neutral | Positive |
| ------- | -------- | ------- | -------- |
| Ch-1    | 21,512   | 266,925 | 62,540   |
| Ch-2    | 6,639    | 159,174 | 27,828   |

👉 Insight:

* Neutral sentiment dominates
* Ch-1 has higher total engagement

---

### 4️⃣ Topic Modeling (LDA)

* Model: Latent Dirichlet Allocation
* Topics: 3

Labels:

* Positive Feedback
* Requests/Suggestions
* Emotional Response

---

### 📊 Topic Results

| Channel | Emotional | Positive | Requests |
| ------- | --------- | -------- | -------- |
| Ch-1    | 134,245   | 100,623  | 116,109  |
| Ch-2    | 50,080    | 95,482   | 48,079   |

👉 Insight:

* Emotional responses are dominant
* Ch-1 has higher discussion volume

---

### 5️⃣ Video Performance Analysis

Metrics:

* View count
* Comment count
* Likes
* Engagement rate

---

### 📊 Results

| Channel | Avg Views | Comments | Likes | Engagement |
| ------- | --------- | -------- | ----- | ---------- |
| Ch-1    | 696K      | 1028     | 16K   | 0.026      |
| Ch-2    | 863K      | 1490     | 23K   | 0.029      |

👉 Insight:

* Ch-2 has better performance
* Ch-2 has higher engagement rate

---

## 📈 Output Files

| File                     | Description               |
| ------------------------ | ------------------------- |
| `combined_sentiment.csv` | Sentiment counts          |
| `combined_topics.csv`    | Topic distribution        |
| `video_summary.csv`      | Video performance metrics |
| `combined_sentiment.png` | Sentiment graph           |
| `combined_topics.png`    | Topic graph               |
| `video_performance.png`  | Video comparison graph    |

---

## 🔗 Data Integration Logic

```text
Comments → Video → Channel  
Live Chat → Channel  
Videos → Channel  
```

👉 All data is unified at **channel level** for comparison.

---

## 🧠 Key Insights

* Live chat captures real-time reactions
* Comments reflect post-viewing feedback
* Combining both gives a complete audience view
* Video metrics validate audience engagement

---

## 🎓 Project Significance

This system provides:

* Multi-source analysis
* Channel-level comparison
* Audience behavior understanding
* Data-driven insights

---

## 🧾 Conclusion

The integrated analysis shows:

* Ch-1 has higher interaction volume
* Ch-2 has stronger engagement performance
* Audience behavior differs across platforms

---

## 👨‍💻 Author

Developed as part of an academic project on **YouTube Channel Comparative Analysis**.
