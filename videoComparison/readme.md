# 🎥 Video Performance Analysis (YouTube Channels)

## 📁 Folder: `videoComparison`

This module analyzes **YouTube video metadata** to compare performance between two channels (**Ch-1 vs Ch-2**) using:

* View count
* Comment count
* Likes
* Engagement rate

---

## 🎯 Objective

The goal of this analysis is to:

* Compare overall performance of two channels
* Identify top-performing videos
* Measure audience engagement
* Understand content effectiveness

---

## 📂 Dataset

| File                                        | Description    |
| ------------------------------------------- | -------------- |
| `English_translated_video_informationt.csv` | Video metadata |

📊 Dataset Size:

* Total videos: **230**

---

## ⚙️ Processing Pipeline

```text id="2xzx2q"
Load Data → Clean Numeric Fields → Aggregate Metrics → Compare Channels → Visualize → Save Output
```

---

## 🔍 Analysis Steps

### 1️⃣ Data Cleaning

* Convert numeric fields:

  * `view_count`
  * `comment_count`
  * `video_likes`
* Remove missing values

---

### 2️⃣ Channel Average Performance

📊 Average values per channel:

| Channel | Avg Views | Avg Comments | Avg Likes |
| ------- | --------- | ------------ | --------- |
| Ch-1    | 696,017   | 1,028        | 16,431    |
| Ch-2    | 863,007   | 1,490        | 23,060    |

👉 Insight:

* Ch-2 performs better on average

---

### 3️⃣ Total Performance

📊 Total values:

| Channel | Total Views | Total Comments | Total Likes |
| ------- | ----------- | -------------- | ----------- |
| Ch-1    | 116,930,929 | 172,864        | 2,760,519   |
| Ch-2    | 53,506,453  | 92,410         | 1,429,771   |

👉 Insight:

* Ch-1 has more total content and overall reach

---

### 4️⃣ Top Videos

Top 10 videos are selected based on **view count**.

👉 Observation:

* Most top videos belong to **Ch-1**
* Indicates strong high-performing content

---

### 5️⃣ Engagement Rate (Key Metric)

```text id="vvtbnj"
Engagement = (Likes + Comments) / Views
```

📊 Results:

| Channel | Engagement Rate |
| ------- | --------------- |
| Ch-1    | 0.026           |
| Ch-2    | 0.029           |

👉 Insight:

* Ch-2 has higher engagement despite fewer total views

---

### 6️⃣ Visualization

Generated graphs:

* Average comparison (bar chart)
* Total performance (bar chart)
* View distribution (histogram)
* Engagement rate comparison

---

## 📈 Output Files

| File                    | Description              |
| ----------------------- | ------------------------ |
| `channel_average.csv`   | Average metrics          |
| `channel_total.csv`     | Total metrics            |
| `top_videos.csv`        | Top 10 videos            |
| `engagement_rate.csv`   | Engagement values        |
| `avg_comparison.png`    | Average comparison graph |
| `total_comparison.png`  | Total comparison graph   |
| `view_distribution.png` | View distribution graph  |
| `engagement_rate.png`   | Engagement graph         |

---

## 🧠 Key Insights

* Ch-2 has stronger **average performance**
* Ch-1 dominates in **total views and content volume**
* Engagement rate is higher in Ch-2
* Popular content is concentrated in Ch-1

---

## 🎓 Project Context

This module is part of a **YouTube Channel Comparative Analysis System**, including:

* Comments Analysis
* Live Chat Analysis
* Video Performance Analysis
* Graph-Based Analysis

---

## ✅ Status

✔ Data cleaned
✔ Channel comparison completed
✔ Engagement analysis completed
✔ Results saved

---

## 👨‍💻 Author

Developed for academic research on YouTube performance and audience engagement analysis.
