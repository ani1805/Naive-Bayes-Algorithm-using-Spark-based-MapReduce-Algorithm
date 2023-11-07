Description of the project:
This project focuses on implementing the Naive Bayes Algorithm for Sentiment Analysis using PySpark. The unique aspect here is the utilization of a Spark-based MapReduce Algorithm to execute the Naive Bayes Algorithm to meet the project requirements. The process involved several key steps:
1. Feature Engineering: The dataset initially contained 13 class labels. To simplify classification, the labels were categorized into three main groups: Positive, Neutral, and Negative.
2. The preprocessing stage consisted of the following steps:
   1. The NLTK library's inbuilt function, PorterStemmer(), was utilized to reduce words to their base form (stemming).
   2. The next step involved tokeinzation of the content column using RegexTokenizer() and then removing the stopwords from the tokenized column.
   3. In the final preprocessing step, the DataFrame (DF) was converted into an RDD, and then the remaining regular expressions were removed from the tokenized data.
3. The Tf-idf Vectorizer was employed to vectorize the already tokenized column. To utilize the Tf-idf Vectorizer in PySpark, firstly, HashingTF and IDF were employed together using a Pipeline(), and the data was passed into the Pipeline().
4. The preprocessed data was divided into training data and testing data using a 60-40 random split on the vectorized data.
5. The prior probabilities were calculated using MapReduce, and to avoid division by zero, Laplace smoothing was also utilized, again using MapReduce.
6. A function was implemented to predict on the test data. This function utilized normal list comprehension and the numpy library.
7. The model was able to predict the correct sentiment with an accuracy of around 40% based on the test data.

Note:
1. The dataset used is hosted on github and is accessible using a public link that is mentioned in the code.
2. The prior probabilities for the Positive, Neutral, and Negative labels were calculated to be 0.3279, 0.272, and 0.401, respectively.
3. The use of Tf-idf Vectorizer over a CountVectorizer resulted in a 0.2% boost in accuracy.
4. In conclusion, according to my analysis, a decent accuracy is achieved by the Spark-based MapReduce Naive Bayes Algorithm. A more in-depth and detailed preprocessing and feature engineering of the data may potentially result in an improved accuracy of up to 65%.