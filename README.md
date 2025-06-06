 </div>
<div align="center"> <h1>🧠 MedAI</h1></div>

MedAI is an intelligent chatbot developed by a collaborative team aimed at providing insightful medical information and assistance to users. Leveraging state-of-the-art machine learning techniques, including natural language processing (NLP), MedAI is being built to understand and respond to a wide range of medical queries efficiently.

TO RUN THE [Medai_llm.ipynb](https://colab.research.google.com/drive/1DzIzVHDosinNcmLC3bwUGK7CbTkdPv3X?usp=drive_link) FILE          

---

## 📘 PROJECT OVERVIEW


 </div>
<div align="center">
 <h2>Description </div> 
MedAI is a chatbot designed to assist users with medical inquiries using machine learning and natural language processing. The project is in early stages, with a focus on building a clean and structured medical Q&A dataset and preparing for model training and evaluation. The MedQuad dataset provides a comprehensive source of medical questions and answers for natural language processing. With over 43,000 patient inquiries from real-life situations categorized into 31 distinct types of questions, the dataset offers an invaluable opportunity to research correlations between treatments, chronic diseases, medical protocols and more. Answers provided in this database come not only from doctors but also other healthcare professionals such as nurses and pharmacists, providing a more complete array of responses to help researchers unlock deeper insights within the realm of healthcare

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
  * Navigate to [Google Slide Presentation](https://docs.google.com/presentation/d/1oBG04dmTUMlyVrlXENFrVYv2byGMZqBb/edit?usp=drive_link&ouid=106577312720845901210&rtpof=true&sd=true)
  * Navigate to [Demo](https://drive.google.com/file/d/1dmxHiC8GkAj6smPeZmkal1t4C30YWiFF/view?usp=sharing)   
- Here in the Demo video we run the code its like downloading and installing a tool called "datasets" that helps the user handle large amounts of text-based data for machine learning tasks.
  
- The code imports essential libraries for a Natural Language Processing (NLP) task, specifically question answering. It utilizes the transformers library to leverage pre-trained models (AutoModelForQuestionAnswering) and tools (AutoTokenizer, pipeline) for this purpose. Additionally, it incorporates torch for deep learning functionalities and pandas for efficient data handling.
  
- This section of the code is responsible for loading a pre-trained model and tokenizer from the Hugging Face model hub. This is a common practice in Natural Language Processing (NLP) as it allows you to leverage powerful models that have been trained on massive datasets.

- This code snippet is specific to Google Colab environments and deals with accessing files stored in your Google Drive.

- The code snippet you provided is part of a larger project that aims to build a medical question-answering system. This system uses a pre-trained model from Hugging Face and fine-tunes it on a medical dataset. It then allows users to ask medical questions and get answers based on the information in the dataset.

- Testing the Pretrained Model
This code snippet is designed to test a pre-trained Question Answering model called deepset/roberta-base-squad2 on a dataset of medical questions and answers.

- This line is creating a new DataFrame called medical_df_filtered from an existing DataFrame called medical_df.

- This preprocess_function takes raw medical question-answer pairs and transforms them into a structured format containing tokenized input, along with the precise location of the answer within the text, which is crucial for training the model to accurately answer medical questions

- Splitting Data for Training and Testing
This part of the code is crucial for building a robust machine learning model. It focuses on splitting the dataset into two parts: one for training the model and another for testing its performance.

- Training the Question Answering Model
This code snippet focuses on training a pre-trained Question Answering model using the Hugging Face Transformers library. The goal is to fine-tune the model on a specific medical question-answering dataset to improve its performance on similar questions.

- This code snippet loads a pre-trained tokenizer, prepares the question and context, and then uses the tokenizer to convert them into a numerical format suitable for input to the fine-tuned model.

- The code imports the re module, which provides tools for working with regular expressions. Regular expressions are essentially search patterns used to find specific sequences of characters within text.

In this case, re is used to extract the relevant answer from the model's raw output. It achieves this by using the re.search function, which locates the first occurrence of a specific pattern within the output string. The pattern itself is designed to identify and isolate the desired answer amidst special tokens that the model uses to mark the answer's beginning and end.

</div>
<div align="center"> <h1>FINAL SUMMARY</h1></div>
This project aims to create a Medical Question Answering System using a fine-tuned deep learning model. The system is designed to provide answers to medical questions using a large medical dataset as its knowledge base.

Here's a breakdown of the key steps and components:

1. Data Acquisition and Preprocessing:

The model utilizes a medical question-answer dataset, likely containing pairs of questions and corresponding answers from a reliable medical source.
The dataset is preprocessed, which involves cleaning and formatting the data into a suitable format for the model. This includes tokenization, splitting the data into training and testing sets, and potentially other steps like handling special characters and medical terminology.

2. Model Selection and Fine-tuning:

A pre-trained language model, specifically "deepset/roberta-base-squad2," is chosen as the base for this project. This model is already trained on a massive dataset and possesses a general understanding of language.
The pre-trained model is fine-tuned using the medical question-answer dataset. Fine-tuning involves adjusting the model's parameters to specialize it for answering medical questions based on the provided dataset.
The fine-tuned model is saved to be used for inference (answering new questions).

3. Question Answering Pipeline:

To answer a new question, the question and relevant medical context are fed into the fine-tuned model.
The model processes the input and predicts the answer span within the context.
The predicted answer is extracted and presented to the user.

4. Gradio Interface:

A user-friendly interface is built using the Gradio library to make the model accessible.
Users can enter their medical questions into a text box.
The model's predicted answer is displayed in another text box.
Overall Goal and Functionality:

The goal of this project is to create an accessible and user-friendly system that can provide answers to medical questions based on a reliable knowledge base. By fine-tuning a pre-trained language model with a medical dataset and deploying it through a Gradio interface, the system aims to offer accurate and relevant medical information to users.

In essence, this project develops a specialized chatbot that can understand and answer medical questions, potentially assisting individuals in obtaining information about medical conditions and treatments.





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
├── Demo & Presentation
├─── Demo Run.md
├─ Medical Model Files
├─- !to many to list!
├─ content 
├─── Cleaned Medical_qa_data.png
├─── One-hot encoding.png
├─── Trained the Model.png 
├─.gitignore
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
- [Huggingface](https://huggingface.co/deepset/roberta-base-squad2)

---

> 🔧 Additional sections (model architecture, demo, visuals) will be added as development progresses.
