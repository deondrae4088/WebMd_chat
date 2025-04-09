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

## 🧹 DATA CLEANING

**Dataset Used:**  
[Comprehensive Medical Q&A Dataset (Kaggle)](https://www.kaggle.com/datasets/thedevastator/comprehensive-medical-q-a-dataset/data)
 We are aiming to load, clean, and preprocess a dataset containing Medical Questions and Answers. So we are preparing the data for potential use in a chatbot or question-answering system related to medical information.

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

<b>Cleaned medical_qa_data</b>

 This block attempts to execute the code within it. If any error occurs during execution, it jumps to the corresponding except block.

df = pd.read_csv('medical_qa_data.csv'): This line uses the read_csv function from pandas (pd) to load the data from the CSV file into a DataFrame named df. A DataFrame is like a table that organizes the data in rows and columns.

display(df.head()): This line displays the first few rows of the DataFrame df using the display function. This gives you a quick glimpse of the data's structure and content.

print(df.shape): This line prints the shape of the DataFrame df, which represents the number of rows and columns in the data. It's displayed as (number of rows, number of columns).

except FileNotFoundError:: If the file 'medical_qa_data.csv' is not found in the current directory, this block is executed, printing an error message and setting df to None.

except pd.errors.EmptyDataError:: If the file 'medical_qa_data.csv' is empty, this block is executed, printing an error message and setting df to None.

except pd.errors.ParserError:: If there is an issue parsing the file (e.g., incorrect format), this block is executed, printing an error message and setting df to None.

except Exception as e:: This block is a catch-all for any other unexpected errors that might occur. It prints a general error message along with the specific error (e) and sets df to None.
<p align="center"><img src="Resource/content/Cleaned Medical_qa_data.png"/></p>

<b>Apply one-hot encoder</b>

One-hot encoding takes a categorical column (like 'Question Type', which might have values like 'diagnosis', 'treatment', etc.) and creates new columns, one for each unique category. Each row will have a '1' in the column corresponding to its original category and '0' in all other columns.
<p align="center"><img src="Resource/content/One-hot encoding.png"/></p>
---

## ⚙️ PREPROCESSING

## Load and prepare the Dataset ##

- The code loads a dataset from a CSV file (medical_qa_data.csv) into a Pandas DataFrame (df)
- It then splits the data into training and testing sets using train_test_split from sklearn. The 'Question' column contains the input text, and the 'Answer' column is assumed to hold the corresponding labels or target variables.

  ```pytthon
  df = pd.read_csv('Resource/medical_qa_data.csv')
   X = df['Question']  
   y = df['Answer']    
   X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
  ```

  ## Tokenization and Padding ##

  - The text data is preprocessed to make it suitable for the machine learning model.
  - Tokenization converts the text into numerical sequences, where each word is represented by a unique number.
  - Padding ensures that all sequences have the same length, which is a requirement for many deep learning models.

```python
tokenizer = Tokenizer(num_words=5000) # Adjust num_words as needed
tokenizer.fit_on_texts(X_train)

X_train_sequences = tokenizer.texts_to_sequences(X_train)
X_test_sequences = tokenizer.texts_to_sequences(X_test)


max_sequence_length = 100 # Adjust max_sequence_length as needed
X_train_padded = pad_sequences(X_train_sequences, maxlen=max_sequence_length)
X_test_padded = pad_sequences(X_test_sequences, maxlen=max_sequence_length)
```

## 🎥 DEMO & PRESENTATION
* Model Run 
  * Navigate to [Demo](resources/content/cg_demo.gif)   


## 📁 PROJECT STRUCTURE
```
├─ code
├── Cleaned_Data.ipynb
├── DATA_CLEANING.ipynb
├── Model_Test.ipynb
├── PREPROCESSING.ipynb
├── medical_qa_data.csv
├─── requirements.txt
├─ Resource
├──Medical Model Files
├─── Lots of Files to Name
├─ Presentation
├─ content
├─── Cleaned Medical_qa_data.png
├─── One-hot encoding.png
├─── Trained the Model.png
├─.gitignore
├─README.md
├─── 
├─── 
├─── 
├─── 
├─── 
├─ README.md
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
