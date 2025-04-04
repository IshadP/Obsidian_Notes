### 2.1 Data Preprocessing

To build a robust machine learning model for spam detection and malicious link identification, a comprehensive dataset was curated by aggregating multiple publicly available sources from Kaggle. The final dataset includes three major categories: spam versus ham messages, malicious versus benign links, and fake versus real news. All data samples were restricted to the English language for consistency.

#### Text and Message Preprocessing

Textual data such as messages, news titles, and article bodies underwent standard Natural Language Processing (NLP) preprocessing steps. This included lowercasing all text, removing punctuation and special characters, and eliminating stop-words. Further, URLs were extracted and separated from text content for specialized analysis. Tokenization was applied to split text into word units, aiding feature extraction.

#### Link Analysis

To identify potentially harmful URLs, features such as domain length and the presence of suspicious patterns (e.g., numeric-only domains, excessive use of subdomains or encoded characters) were extracted. These engineered features were fed into a Logistic Regression classifier to distinguish malicious links from safe ones.

#### Label Consolidation

Labels from different datasets were normalized into three binary classification tasks:

1. **Spam Detection** (Spam / Ham)
2. **Malicious Link Detection** (Malicious / Benign)
3. **Fake News Detection** (Fake / Real)

This unified format enabled streamlined preprocessing and model training across tasks.

#### Data Splitting

The entire dataset was partitioned into training and testing sets to evaluate model performance. A stratified split was used to preserve label distribution across sets, ensuring generalization during evaluation.


---

