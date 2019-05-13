+++

+++
<h1>**Multinomisl Naive Bayes Classification**</h1>
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

$$ P(A \mid B) = \frac{P(B \mid A) \, P(A)}{P(B)} $$
