+++
title="Multinomial Naive Bayes Classification"
+++
<h1>**Multinomial Naive Bayes Classification**</h1>
<body>
A classifier is an algorithm that differentiates similar objects based on some features. Naive Bayes is one of the more popular classifiers 
when it comes to text classification as it has been successfully applied to many domains, particularly Natural Language Processing(NLP).
We have about **836** different classes in the dataset and we can see that this will be a difficult 
task to achieve as there are large number of classes and we need lots of good features to be select inorder to justify and understand each
class.

<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>

Naive Bayes is a family of algorithms based on applying Bayes theorem with an assumption, that every feature is independent of the others,
in order to predict the category of a given sample. They are probabilistic classifiers, therefore will calculate the probability of each 
class using Bayes theorem, and the classes with the highest probability will be output.

In our dataset the **condition** column that represents the medical condition a review is related, to is the class which we will try to predict.

We have already preprocessed the reviews in Part 1 while building our search engine.
Inorder to make the iterative process of tuning the algorithm we split the entire dataset into train, validation and test. Train consists 50% of the dataset, validation and test each have 25% of the remaining dataset.

Use the exsisting code from part 1 to generate an Inverted Index vocabulary on the training set.

$$ P(A \mid B) = \frac{P(B \mid A) \, P(A)}{P(B)} $$
</body>

<h2>Steps to calculating the prior probablities:</h2>
<body>
1. Create a temporary python **dictionary** which stores the list of all documents that occur in each class, all unique words from the vocabulary in each class and the count of total number of words in each class.
<pre>
temp_class_dict = { class-1 : [[review-1, review-2,.......,review-n], 
                              [word-1, word-2, word-3,.......,word-n], 
                              count_total_words]
                      .
                      .
                      . }
</pre>
2. Create the **dictionary** to store the prior probablities of each class by
<p>
  P(class) = Number of reviews within the class / Total number of training set.
</p>
  
3. Create an inner dictionary for each class with words that occur within the class as keys and store the number for times the word occured within all reviews in the class and the total number of reviews in which it occured within the class.
<pre>
naive_class_dict = { class : [P(class), count_total_words, count_unique_words,
                              {word-1 : [count_total_occurence, count_review_occurrence]
                                 .
                                 .
                                 . }
                       .
                       .
                       .
                          }
</pre> 

<h4>Calculating probablity of a given review belonging to a class:</h4>

Consider the below example, we will see how to use the priop probablities to calculate the probablity of this review belonging to 
class **Urinary Tract Infection**.

<pre>

<table>
  <tr>**<th>drugName</th> <th>condition</th>	                                   <th>review</th>	                 <th>rating</th>	<th>usefulCount</th> 	        <th>revvec</th>	           <th>revID</th>**</tr>

<tr><td>Cipro</td> 	<td>Urinary Tract Infection</td>	<td>"I also had a very bad reaction to this medication!"</td>	<td>1</td>		<td>44</td>	<td>['bad', 'reaction', 'medication']</td> <td>109180</td></tr>

</table>
</pre>
naive_class_dict['Urinary Tract Infection'][3]['bad'] = [315, 249]
naive_class_dict['Urinary Tract Infection'][3]['reaction'] = [74, 66]
naive_class_dictnaivecps['Urinary Tract Infection'][3]['medication'] = [265, 198]

* so, the probablity of a given query belonging to a class is

P(class | w1,w2,w3) = log(P(w1 | class) * P(w1 | class) * P(w1 | class) * P(class))

* probablity of a class is

P(class) = number of reviews in the class / total number of reviews

* probablity of a word w1 occuring in a class

* p(w1 | clas) = (number of times w1 occurs in class + alpha) / (total number of words in class + total number of vords in the vocabulary)

* Here aplha is the smoothing factor which helps overcome problems of when a word in the query does not occur within a class.
This hyperparameter comes handy when trying to optimize the classificaation, that is increase the accuracy.

<pre>
P(Urinary Tract Infection) = 0.008207509918583007
P(bad | Urinary Tract Infection) = (315 + 1 )/ (28831 + 32622) = -4.376021118875437
P( reaction | Urinary Tract Infection ) = (74 + 1) / (28831 + 32622) =  -7.295332487596864
P( medication | Urinary Tract Infection ) = (265 + 1) / (28831 + 32622) =  -9.66062970253546
</pre>
</body>

<h2>Challenges Faced</h2>
<body>
1. Optimizing the algorithm was a bit challenging. Created a custom list stop words that are dataset specific. As the text we analyse are reviews the features are not all that unique between classes.

2. Choosing the alpha value was a decission I took to improver the accuracy of the classifier. Generally alpha is assumed to be 1, but the accuracy was 
<pre> aplha       Accuraacy%       Error% </b>
        1           53.6 %          46.4 %</b>
       0.1          54.2 %          45.8 %</b>
      0.0001        53.304 %        46.69 %</b>
      0.00001       55.4 %          44.59 %</b>
     0.0000001      59.69 %         42.3 %</b>
     0.00000001     54.2 %          45.8 %</b>
</pre>
</body>

<h5>Contributions</h5>
1. Developed the classifier algorithm in numpy.
2. Smoothing hyperparameter optimized to 0.0000001 insted of default value 1.

<h6>Referrences:</h6>

* (https://towardsdatascience.com/multinomial-naive-bayes-classifier-for-text-analysis-python-8dd6825ece67)
* (https://medium.com/syncedreview/applying-multinomial-naive-bayes-to-nlp-problems-a-practical-explanation-4f5271768ebf)
* (https://nlp.stanford.edu/IR-book/html/htmledition/naive-bayes-text-classification-1.html)
* (https://nlp.stanford.edu/IR-book/html/htmledition/naive-bayes-text-classification-1.html)


[Part 1]({{<ref "/post/First-Search-engine/index.md">}})
        
