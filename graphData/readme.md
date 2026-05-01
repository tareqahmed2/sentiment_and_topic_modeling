# 📊 Graph Data (Neo4j) – YouTube Interaction Network

## 📁 Folder: `graphData`

This folder contains **11 files** used to build a complete **graph-based interaction model** for YouTube channel analysis.

---

## 📦 Total Files Overview

### 🔹 Node Files (4)

* `users.csv`
* `videos.csv`
* `comments.csv`
* `live.csv`

### 🔹 Relationship Files (5)

* `user_comment.csv`
* `user_live.csv`
* `comment_video.csv`
* `live_channel.csv`
* `video_channel.csv`

### 🔹 Additional Files (2)

* `graph_relation.png` → Graph structure diagram
* `readme.md` → Documentation

---

## 🧠 Graph Model

```text
(User) ──POSTED──▶ (Comment)
(User) ──POSTED──▶ (LiveChat)

(Comment) ──ON_VIDEO──▶ (Video)
(LiveChat) ──ON_CHANNEL──▶ (Channel)

(Video) ──BELONGS_TO──▶ (Channel)
```

---

## 🎯 Purpose of This Graph

This graph is used to:

* Track user interaction across platforms
* Combine comments + live chat + video data
* Analyze engagement patterns
* Support advanced network analysis

---

## 🔗 How This Graph Works

### Step 1: User Interaction

* Users create:

  * Comments
  * Live chat messages

---

### Step 2: Content Mapping

* Comments → linked to videos
* Live chat → linked to channels

---

### Step 3: Channel Mapping

* Videos → linked to channels

---

### Final Flow

```text
User → Comment → Video → Channel  
User → LiveChat → Channel
```

---

## 🚀 How to Use This Graph (Neo4j)

### Step 1: Move Files

Copy all CSV files into:

```text
Neo4j/import/
```

---

### Step 2: Import Nodes

Load:

* Users
* Videos
* Comments
* Live chats

---

### Step 3: Create Relationships

Connect:

* User → Comment
* User → Live
* Comment → Video
* Live → Channel
* Video → Channel

---

## 📊 Future Use Cases (VERY IMPORTANT)

👉 This graph is powerful for:

### 🔹 1. Finding Active Users

* Who comments or chats the most

---

### 🔹 2. Identifying Popular Videos

* Which videos get the most interaction

---

### 🔹 3. Channel Engagement Analysis

* Compare Ch-1 vs Ch-2

---

### 🔹 4. Real-Time vs Post Interaction

* Live chat vs Comments

---

### 🔹 5. Network Analysis

* User behavior patterns
* Interaction flow

---

## 🔥 Why Graph is Needed (Key Idea)

👉 Normal data (tables):

* Shows numbers

👉 Graph data:

* Shows **connections**

💡 Example:
Instead of:

> "1000 comments"

Graph shows:

> "Which users made those comments and on which videos"

---

## 📈 Example Queries (Future Usage)

### Most Active Users

```cypher
MATCH (u:User)-[:POSTED]->(n)
RETURN u.user_id, COUNT(n) AS activity
ORDER BY activity DESC
LIMIT 10;
```

---

### Channel Engagement

```cypher
MATCH (c:Comment)-[:ON_VIDEO]->(v:Video)-[:BELONGS_TO]->(ch:Channel)
RETURN ch.name, COUNT(c);
```

---

### Live Chat Activity

```cypher
MATCH (l:LiveChat)-[:ON_CHANNEL]->(ch:Channel)
RETURN ch.name, COUNT(l);
```

---

## 🎓 Project Importance

This graph adds:

* Relationship-based analysis
* Deeper insights beyond statistics
* Support for advanced research

---

## ✅ Status

✔ Graph data complete
✔ Includes comments + live + video
✔ Ready for Neo4j
✔ Supports advanced queries

---

## 👨‍💻 Author

Developed as part of a **YouTube Channel Comparative Analysis Project**.
