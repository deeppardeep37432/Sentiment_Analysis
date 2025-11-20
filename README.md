Sentiment Analysis Project
End-to-End Text Processing Using Azure, Python & Power BI

Author: Pardeep Kaur (200632295)
        Gurleen Kaur(200604519)

📌 Project Overview:
This project performs end-to-end sentiment analysis on text data collected from multiple online articles. It integrates Python, Azure Cloud services, and Power BI to create a complete machine-learning workflow — from preprocessing to visualization.

The main steps include:
Data preprocessing using Python (cleaning, tokenization, sentiment scoring)
Uploading processed data to Azure Blob Storage
Creating an Azure Data Factory (ADF) pipeline to load data into Azure SQL Database
Importing SQL data into Power BI for analysis and visualization

📂 Repository Structure
Sentiment_Analysis/
│
├── sentimentanalysis.ipynb     # Main Jupyter Notebook with preprocessing + model
├── data/
│   └── sentiment.csv           # Cleaned dataset (if included)
├── README.md                   # Project documentation
└── assets/                     # Screenshots (optional)

🧠 Technologies Used
Component	Technology
Programming	Python (NLTK, TextBlob, Pandas)
Cloud Storage	Azure Blob Storage
Data Pipeline	Azure Data Factory
Database	Azure SQL Database
Visualization	Power BI
Version Control	GitHub

⚙️ Step-by-Step Workflow

1️⃣ Data Preprocessing (Python Notebook)

Performed in the Jupyter Notebook:

✔ Load raw text
✔ Clean text (remove HTML tags, stopwords, punctuation)
✔ Apply sentiment scoring
✔ Create final structured CSV
✔ Export cleaned file: sentiment.csv

2️⃣ Azure Blob Storage Upload

Steps executed:

✔ Create a Storage Account
✔ Create a Container
✔ Upload sentiment.csv file
✔ Copy Blob SAS URL (used in ADF)

3️⃣ Azure Data Factory Pipeline

Pipeline included:

Source: Azure Blob Storage

Linked Service: Storage account

Dataset: CSV file

Sink: Azure SQL Database (sentiments table)

Copy Activity: Load data into SQL DB

Outcome:
The CSV is now loaded into SQL for reporting.

4️⃣ Azure SQL Database

✔ Created SQL database
✔ Created table using:

CREATE TABLE sentiment_table (
    id INT IDENTITY(1,1),
    text NVARCHAR(MAX),
    text_clean NVARCHAR(MAX),
    sentiment_label NVARCHAR(50),
    sentiment_score FLOAT
);


✔ Data successfully inserted via the ADF pipeline.

5️⃣ Power BI Visualization

Imported SQL database into Power BI.

Created visuals:

📊 Bar Chart — Sentiment Distribution
🥧 Pie Chart — Sentiment Percentage
📄 Table — Original vs. Cleaned Text
📉 Score visualization

Insights:

Majority of articles were positive

Some texts expressed neutral viewpoints

Very few articles demonstrated negative sentiment

📊 Project Results & Insights

Positive sentiment dominates majority of the dataset

Topic-based sentiment trends can be identified

Text cleaning improves accuracy of sentiment scoring

Visualizations clearly separate sentiment categories

🚀 How to Run This Project
Prerequisites

Python 3.9+

Azure subscription

Power BI Desktop

Git installed

Steps

Clone repo:

git clone https://github.com/deeppardeep37432/Sentiment_Analysis.git


Install libraries:

pip install pandas textblob nltk azure-storage-blob


Run Notebook:

jupyter notebook sentimentanalysis.ipynb

🔮 Future Enhancements

Use Azure Machine Learning for model deployment

Enhance dataset quantity for improved accuracy

Add topic modeling (LDA)

Deploy a dashboard on Power BI Service
