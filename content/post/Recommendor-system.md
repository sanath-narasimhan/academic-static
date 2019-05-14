+++ 

title="Content Based Recommendor System" 

+++

<h1> **Content Based Recommendor System** </h1>
<body>
Recommendor systems are one of the most facinating algorithms that have been in the lime-light in the recent years. There are common algorithms that are used for making recommendations.
Collaborative filtering is one of the most precise recommendation algorithm used by Netflix that is really popular.

Unfortunately collaborative filtering requires a lot of data related about user preferrences which is unavailable in our dataset.

Content-Based recommendation is a better fit for our dataset. In this technique we simply find the items in our dataset that are similar to the items already viewed by our user.

<h2> Implementation of the system </h2>

1. In the dataset the review fiels acts like the content description of the items, that is a specific medicaition related to a certain condition(disease)

2. Everytime a user performes asearch, they are provided with a set ofresults given by our Inverted index algorithm, which calculates the cosine similarity between our search query and reviews in our dataset.

3. It sounds like most of our work is done as the same algorithm can be used to find the similarity beetween the current review selected and the reviews that can be recommended.

4. When an item is selected for viewing we simply take the review it is assosiated with and apply the similarity between the selected review and our dataset using the inverted index vocabulary already generated.

5. To keep the recommendations relevant to the selected item, we filter out the result from the reviews that are not in the same class as the selected item. This is to prevent irrelevant recommendations.


**Algorithm**
<pre>
1. Retrive the review ID of the selected item.

2. Perform search to find reviews that are similar to the selected one with k=50.

3. Filter the result to display reviews that are for the same condition as the selected review.
</pre>

<h3> Challenges faced </h3>

1. As the dataset lacks the required contentlike user history we need to get creative with the algorithm. Used inly current selected item for recommendation insted of history of viewed objects.

2. Cannot use any standart techniques to improve content-based recommendations. Usedthe classof items toensure quality of recommendation. 

<h4> Contributions </h4>

1. Implemented psudo Content-Based recommendation system with the already created Inverted Index and similarity matrix.

2. Using top 50 results fromthe similarity algorithm provides better recommendations.

<h5> Referrences: </h5>

* (https://medium.com/@tomar.ankur287/content-based-recommender-system-in-python-2e8e94b16b9e)

* (https://medium.com/@cfpinela/content-based-recommender-systems-a68c2aee2235)

**Check Part 1 of this series to find how to implement the similarity algorithm using the generated Inverted index**

[Part 1] (https://sananara-aryabhata.netlify.com/post/first-search-engine/)
