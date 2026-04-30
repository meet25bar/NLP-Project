#📝 Yelp Review Sentiment Analysis (NLP)

This project performs Natural Language Processing (NLP) on Yelp reviews to classify them as positive (5 stars) or negative (1 star) using Machine Learning.

📌 Project Overview
The goal of this project is to:


Perform Exploratory Data Analysis (EDA) on Yelp reviews


Apply text preprocessing techniques


Build a classification model using:


Bag of Words


TF-IDF




Evaluate model performance



📂 Dataset


File: yelp.csv


Total Records: 10,000 reviews


Features include:


text → review content


stars → rating (1–5)


cool, useful, funny → engagement metrics





🔍 Exploratory Data Analysis (EDA)
Performed:


Histogram of review length by star rating


Boxplot of text length vs stars


Countplot of star distribution


Correlation heatmap


Key Insight:


Lower star ratings tend to have longer and more detailed reviews


Strong correlation between:


useful & funny


text length & engagement





⚙️ Feature Engineering
Created a new feature:
df['text length'] = df['text'].apply(len)

🤖 Machine Learning Models
1️⃣ Model 1: Bag of Words + Naive Bayes


Used:


CountVectorizer


MultinomialNB




Results:
Confusion Matrix:[[114  36] [ 18 650]]Accuracy: 93%
📊 Classification Report:


Precision (5-star): 0.95


Recall (5-star): 0.97


Overall Accuracy: 93%



2️⃣ Model 2: Pipeline (BoW + TF-IDF + Naive Bayes)
Pipeline used:
Pipeline([    ('bow', CountVectorizer()),    ('tfidf', TfidfTransformer()),    ('classifier', MultinomialNB()),])
Results:
Confusion Matrix:[[  0 228] [  0 998]]Accuracy: 81%
⚠️ Observation:


Model predicts only 5-star reviews


TF-IDF reduced performance significantly



📉 Why TF-IDF Performed Worse?
Possible reasons:


Dataset imbalance (more 5-star reviews)


Naive Bayes already works well with raw counts


TF-IDF may reduce importance of strong sentiment words



🧠 Key Learnings


Simpler models like Bag of Words + Naive Bayes can outperform complex pipelines


Always evaluate models — assumptions can be wrong


Feature engineering plays a critical role in NLP



🚀 Future Improvements


Use different models:


Logistic Regression


SVM


Random Forest




Handle class imbalance


Add text preprocessing:


Stopword removal


Lemmatization




Try deep learning models (LSTM, BERT)



🛠️ Tech Stack


Python 🐍


NumPy


Pandas


Matplotlib


Seaborn


Scikit-learn



▶️ How to Run
# Clone repositorygit clone https://github.com/your-username/yelp-nlp-project.git# Install dependenciespip install -r requirements.txt# Run notebookjupyter notebook

📌 Conclusion


Achieved 93% accuracy using a simple model


TF-IDF did not improve results in this case


Demonstrates importance of experimentation in ML



👨‍💻 Author
Meet Barot
