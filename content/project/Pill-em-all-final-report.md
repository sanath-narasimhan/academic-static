+++
+++

title = "Pill-em-All A Search engine for Medicine reviews"

**Pill-em-all** is a Medication review app where you can search user reviews and find ratings. You can search by symptoms and see 
which of them are working according to your requirment.

The Project is developed in python using flask for the webapp development. The system is built on dataset available 
[here] https://www.kaggle.com/jessicali9530/kuc-hackathon-winter-2018/home which has **_patient reviews_** on specific drugs along
with related conditions and a **_10 star_** patient rating with **_useful count_** reflecting overall patient satisfaction.

# Demo video:
{{<https://www.youtube.com/watch?v=8uatyMzRIKA>}}

>Webapp: http://050e0e36.ngrok.io/

### Data Preprocessing
The dataset, like any other, has lot of missing values and is dropped from the dataset. 
Each review is converted into a **bag of words** representation. These are used to build the final system.
Some techniques used are **stopword removal**and **lemmatizaion** for removing redundent words.

# Search Engine
* Inverted Index method is used to build a vocabulary that stores the weights of every word in the entire dataset of reviews. 

* Cosine similarity is used to calculate the similarity between the query and the associated reviews that uses the tf-idf weights of words in query that are present in the vocabulary.

Follow [this](https://sananara-aryabhata.netlify.com/post/first-search-engine/) blog to understand the implementation of the Inverted Index.

# Classifier
* A multinominal Naive Bayes Classifier that is implemented in python gives the probablity of a given review belonging to the top 10 **condition** class in the dataset.

* This uses prior probablities of every **condition** and the probablity of the **_key words_** in a review belonging to each of these **condition** class to compute the score.

* A simple yet effective algorithm for classification of text.

Follow the blog [here](https://sananara-aryabhata.netlify.com/post/naive-bayes-classifier/) to understand and implement the Naive bayes classifier.

# Recommender system
* A content-based recommender that shows **_reviews_** of **medications** thaat are similar to the selected review which are associated with the same **condition**.

* A fairly simple approach for recommendation, useful for when lacking user preferrence data or a detailed description of items, that is in this case **medicine**.

Understand the basic idea behind the recommender system [here](https://sananara-aryabhata.netlify.com/post/recommendor-system/).


>**Github Repository:** (https://github.com/sanath-narasimhan/Pill-em-all2.0)

#### Referrences:
* (https://nlp.stanford.edu/IR-book/html/htmledition/a-first-take-at-building-an-inverted-index-1.html)

* [Sample code given] (https://colab.research.google.com/drive/1n1hUx-mO4EqhKyFmN--9pK5MhKR68MpB#scrollTo=8ILVjili5Xmu)

* (https://towardsdatascience.com/multinomial-naive-bayes-classifier-for-text-analysis-python-8dd6825ece67)

* (https://medium.com/syncedreview/applying-multinomial-naive-bayes-to-nlp-problems-a-practical-explanation-4f5271768ebf)

* (https://nlp.stanford.edu/IR-book/html/htmledition/naive-bayes-text-classification-1.html)

* (https://nlp.stanford.edu/IR-book/html/htmledition/naive-bayes-text-classification-1.html)
