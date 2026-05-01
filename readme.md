# Sentiment and Topic Modeling Project

## 📌 Overview

This project performs **Sentiment Analysis** and **Topic Modeling** on textual data such as comments and live chat messages.
It applies techniques from Natural Language Processing (NLP) to extract meaningful insights from datasets.

---

## 🚀 Features

* Sentiment classification (Positive, Negative, Neutral)
* Topic modeling from comments and chat data
* Text preprocessing and cleaning
* Analysis of translated English datasets

---

## 🗂️ Project Structure

```
.
├── Data/
│   └── English_version/
│       ├── English_translated_comment_data.csv
│       ├── English_translated_live_chat_data.csv
│       └── English_translated_video_informationt.csv
├── notebooks/
├── src/
├── requirements.txt
├── README.md
└── .gitignore
```

---

## ⚠️ Dataset Notice

Large dataset files are **not included in this repository** due to GitHub file size limits.

### Required files:

* Data/English_version/English_translated_comment_data.csv
* Data/English_version/English_translated_live_chat_data.csv
* Data/English_version/English_translated_video_informationt.csv

👉 Please download them from:
[Add your Google Drive / Kaggle link here]

---

## 📂 Dataset Setup

After downloading, place the files in the following directory:

```
Data/English_version/
```

Your folder structure should look like:

```
Data/
└── English_version/
    ├── English_translated_comment_data.csv
    ├── English_translated_live_chat_data.csv
    └── English_translated_video_informationt.csv
```

---

## 🛠️ Installation

1. Clone the repository:

```
git clone https://github.com/tareqahmed2/sentiment_and_topic_modeling.git
cd sentiment_and_topic_modeling
```

2. Create a virtual environment:

```
python -m venv venv
```

3. Activate the environment:

**Windows:**

```
venv\Scripts\activate
```

**Mac/Linux:**

```
source venv/bin/activate
```

4. Install dependencies:

```
pip install -r requirements.txt
```

---

## ▶️ Usage

Example usage:

```
import pandas as pd

comments = pd.read_csv("Data/English_version/English_translated_comment_data.csv")
live = pd.read_csv("Data/English_version/English_translated_live_chat_data.csv")

print(comments.head())
```

Run your scripts or notebooks to perform:

* Sentiment Analysis
* Topic Modeling

---

## 🧠 Technologies Used

* Python
* Pandas
* Scikit-learn
* Natural Language Processing (NLP)

---

## 📌 Notes for Developers

* Ensure datasets are placed correctly before running the project
* Large files are excluded using `.gitignore`
* You can replace datasets with your own if needed

---

## 🤝 Contribution

Contributions are welcome!

1. Fork the repository
2. Create a new branch
3. Make your changes
4. Submit a pull request

---

## 📄 License

This project is intended for academic and research purposes.

---

## 👨‍💻 Author

Tareq Ahmed
