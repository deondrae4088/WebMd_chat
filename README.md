# 🧠 MedAI

MedAI is an intelligent chatbot developed by a collaborative team aimed at providing insightful medical information and assistance to users. Leveraging state-of-the-art machine learning techniques, including natural language processing (NLP), MedAI is being built to understand and respond to a wide range of medical queries efficiently.

---

## 📘 PROJECT OVERVIEW

**Title:** MedAI  
**Description:**  
MedAI is a chatbot designed to assist users with medical inquiries using machine learning and natural language processing. The project is in early stages, with a focus on building a clean and structured medical Q&A dataset and preparing for model training and evaluation.

---

## 🛠️ INSTALLATION

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install Libraries & Dependencies like pandas, numpy, tensorflow keras, SentimentIntensityAnalyzer, seaborn, Dense, Scikitlearn, Matplotlib, vaderSentiment etc. refer to the [requirements.txt](https://github.com/deondrae4088/WebMd_chat/blob/main/Code/requirements.txt)

#### Pandas

```bash
pip install pandas
```

#### numpy

```bash
pip install numpy
```

#### Matplot

```bash
pip install matplotlib
```

#### tensorflow kearas

```bash
pip install tensorflow kearas
```

#### sklearn

```bash
pip install sklearn
```

#### vaderSentiment

```bash
pip install vaderSentiment
```

#### torch

```bash
pip install torch
```

#### transformers

```bash
pip install transformers
```

## 🧹 DATA PREPROCESSING

**Dataset Used:**  
[Comprehensive Medical Q&A Dataset (Kaggle)](https://www.kaggle.com/datasets/thedevastator/comprehensive-medical-q-a-dataset/data)

**Steps Completed:**

- Loaded `train.csv` containing medical question-answer pairs.
- Renamed the `qtype` column to `Question Type`.
- Removed all rows with missing data.
- Verified structure and saved a cleaned version: `medical_qa_data.csv`.

```python
import pandas as pd

df = pd.read_csv('/content/train.csv')
df.rename(columns={'qtype': 'Question Type'}, inplace=True)
df.dropna(inplace=True)
df.to_csv('medical_qa_data.csv', index=False)
```

**Resulting Dataset:**  
- Shape: 16,407 rows × 3 columns  
- Columns: `Question Type`, `Question`, `Answer`

---

## 📁 PROJECT STRUCTURE

```
├── Resource/
│   └── medical_qa_data.csv
├── notebooks/
│   └── eda_and_preprocessing.ipynb
├── README.md
```

---

## 👥 PROJECT CONTRIBUTORS

- **Justin** – Proposal, Slides, README  
- **Xavier** – Proposal, Slides, README  
- **Thomas** – Slides, README  
- **Dexter** – Clean Data, PreProcessed Data, Train Model  
- **Gabe** – Gradio  
- **Justinian** – Gradio

---

## 📚 REFERENCES

- [Comprehensive Medical Q&A Dataset – Kaggle](https://www.kaggle.com/datasets/thedevastator/comprehensive-medical-q-a-dataset/data)
- [Pandas Documentation](https://pandas.pydata.org/)

---

> 🔧 Additional sections (model architecture, demo, visuals) will be added as development progresses.
