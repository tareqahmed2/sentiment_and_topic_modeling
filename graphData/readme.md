# 📊 Graph Data (Neo4j) – YouTube Interaction Network

## 📁 Folder: `graphData`

This folder contains structured CSV files for building a **graph-based interaction model** using **Neo4j**.

The graph represents relationships between:

* 👤 Users
* 💬 Comments
* 🔴 Live Chats
* 🎥 Videos
* 📺 Channels

---

## 🎯 Purpose

The goal of this graph is to:

* Track how users interact with content
* Combine **comments + live chat + video data**
* Analyze engagement patterns
* Support network-based analysis

---

## 🧠 Graph Model Overview

```text
(User) ──POSTED──▶ (Comment)
(User) ──POSTED──▶ (LiveChat)

(Comment) ──ON_VIDEO──▶ (Video)
(LiveChat) ──ON_CHANNEL──▶ (Channel)

(Video) ──BELONGS_TO──▶ (Channel)
```

---

## 📂 Node Files (Entities)

| File           | Description                               |
| -------------- | ----------------------------------------- |
| `users.csv`    | Unique users from comments and live chat  |
| `videos.csv`   | Video metadata (video_id, channel, title) |
| `comments.csv` | Comment text data                         |
| `live.csv`     | Live chat messages                        |

---

## 🔗 Relationship Files

| File                | Relationship                      | Meaning                        |
| ------------------- | --------------------------------- | ------------------------------ |
| `user_comment.csv`  | User → Comment (`POSTED`)         | User wrote a comment           |
| `user_live.csv`     | User → LiveChat (`POSTED`)        | User sent a live message       |
| `comment_video.csv` | Comment → Video (`ON_VIDEO`)      | Comment belongs to a video     |
| `live_channel.csv`  | LiveChat → Channel (`ON_CHANNEL`) | Live chat belongs to a channel |
| `video_channel.csv` | Video → Channel (`BELONGS_TO`)    | Video belongs to a channel     |

---

## ⚙️ How Data Was Generated

The graph data is created by:

1. Loading:

   * `comments.csv`
   * `live.csv`
   * `videos.csv`

2. Merging:

   * Comments with videos to get channel information

3. Creating:

   * Unique node IDs (`comment_id`, `live_id`)
   * Node tables (users, videos, comments, live)
   * Relationship tables

---

## 🚀 How to Use in Neo4j

### Step 1: Copy Files

Place all CSV files into:

```text
Neo4j/import/
```

---

### Step 2: Create Constraints

```cypher
CREATE CONSTRAINT user_id IF NOT EXISTS FOR (u:User) REQUIRE u.user_id IS UNIQUE;
CREATE CONSTRAINT video_id IF NOT EXISTS FOR (v:Video) REQUIRE v.video_id IS UNIQUE;
CREATE CONSTRAINT comment_id IF NOT EXISTS FOR (c:Comment) REQUIRE c.comment_id IS UNIQUE;
CREATE CONSTRAINT live_id IF NOT EXISTS FOR (l:LiveChat) REQUIRE l.live_id IS UNIQUE;
```

---

### Step 3: Import Nodes

```cypher
LOAD CSV WITH HEADERS FROM 'file:///users.csv' AS row
CREATE (:User {user_id: row.user_id});

LOAD CSV WITH HEADERS FROM 'file:///videos.csv' AS row
CREATE (:Video {
    video_id: row.video_id,
    title: row.Title,
    channel: row.channel
});

LOAD CSV WITH HEADERS FROM 'file:///comments.csv' AS row
CREATE (:Comment {
    comment_id: row.comment_id,
    text: row.translated_text
});

LOAD CSV WITH HEADERS FROM 'file:///live.csv' AS row
CREATE (:LiveChat {
    live_id: row.live_id,
    text: row.translated_text,
    channel: row.channel
});
```

---

### Step 4: Import Relationships

```cypher
// User → Comment
LOAD CSV WITH HEADERS FROM 'file:///user_comment.csv' AS row
MATCH (u:User {user_id: row.source}),
      (c:Comment {comment_id: row.target})
CREATE (u)-[:POSTED]->(c);

// User → LiveChat
LOAD CSV WITH HEADERS FROM 'file:///user_live.csv' AS row
MATCH (u:User {user_id: row.source}),
      (l:LiveChat {live_id: row.target})
CREATE (u)-[:POSTED]->(l);

// Comment → Video
LOAD CSV WITH HEADERS FROM 'file:///comment_video.csv' AS row
MATCH (c:Comment {comment_id: row.source}),
      (v:Video {video_id: row.target})
CREATE (c)-[:ON_VIDEO]->(v);

// LiveChat → Channel
LOAD CSV WITH HEADERS FROM 'file:///live_channel.csv' AS row
MATCH (l:LiveChat {live_id: row.source})
MERGE (ch:Channel {name: row.target})
CREATE (l)-[:ON_CHANNEL]->(ch);

// Video → Channel
LOAD CSV WITH HEADERS FROM 'file:///video_channel.csv' AS row
MATCH (v:Video {video_id: row.source})
MERGE (ch:Channel {name: row.target})
CREATE (v)-[:BELONGS_TO]->(ch);
```

---

## 🔍 Example Queries

### Most Active Users

```cypher
MATCH (u:User)-[:POSTED]->(n)
RETURN u.user_id, COUNT(n) AS activity
ORDER BY activity DESC
LIMIT 10;
```

---

### Channel Engagement (Comments + Live)

```cypher
MATCH (ch:Channel)<-[:BELONGS_TO]-(v:Video)<-[:ON_VIDEO]-(c:Comment)
OPTIONAL MATCH (l:LiveChat)-[:ON_CHANNEL]->(ch)
RETURN ch.name,
       COUNT(DISTINCT c) AS comments,
       COUNT(DISTINCT l) AS live_messages;
```

---

### Most Commented Videos

```cypher
MATCH (c:Comment)-[:ON_VIDEO]->(v:Video)
RETURN v.video_id, COUNT(c) AS total_comments
ORDER BY total_comments DESC
LIMIT 10;
```

---

## 📊 Key Benefits

* Combines multiple data sources into one model
* Enables relationship-based analysis
* Identifies active users and popular content
* Supports real-time vs static interaction comparison

---

## 🎓 Project Context

This graph is part of a **YouTube Channel Comparative Analysis Project**, including:

* Sentiment Analysis
* Topic Modeling
* Channel Comparison
* Graph-Based Analysis

---

## ✅ Status

✔ Graph data generated
✔ Neo4j-ready format
✔ Supports advanced querying

---

## 👨‍💻 Author

Developed for academic research and data analysis.
