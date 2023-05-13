# Multi-Lbl2Vec

_Adit Jindal, Akshay Iyer, Preethi Narayan_

A new approach for Topic Modeling and Analysis of Yelp Reviews using Predefined Topic List
======= 

Accurate unsupervised classification is a crucial task in today’s world where large amounts of unlabeled data exist. Modern day approaches primarily focus on single class classification and might perform poorly in multiclass classification. Through the example of restaurant reviews, My team and I introduce Multi-Lbl2Vec, a modified version of Lbl2Vec specifically for classifying unlabeled data based on predefined topic lists. The additions include a new max_docs variable, outlier detection, and a multiclass evaluation metric. On comparing this approach with industry standard approaches like Lbl2Vec and BartMNLI, we notice slightly better performance. To showcase the utility of Multi-Lbl2Vec, we target reviews of a particular business and run the classifier followed by a trained semantic analyzer. The results are analyzed to give recommendations to the business.

Benefits of Approach
--------

1. No need to label the whole document dataset for classification.
3. No need for stemming/lemmatization.
4. Works on short text.
5. Creates jointly embedded label, document, and word vectors.

Steps
--------

1. Use open source restaurant data from Yelp 
2. Choose classes to segregate. (Food, Time, Ambience, Service, and Price are chosen in above model)
3. Choose keywords for each class:
<img width="367" alt="Screenshot 2023-05-13 at 2 48 57 PM" src="https://github.com/aditjindal27/ReviewSegregator/assets/54547947/92279b7f-da23-49b7-8c6c-5372ef13ed4c">

4. Preprocess reviews and train doc2Vec model
5. Use doc2Vec model to segregate reviews based on similarity with keywords
6. Find centroid for each label -> gives label vector
7. Use similarity scores with these labels to segregate reviews

Use Cases
--------

1. Combined with BartMNLI, final macro f-1 score was 0.5887 which is good for unsupervised learning.
<img width="373" alt="Screenshot 2023-05-13 at 2 55 46 PM" src="https://github.com/aditjindal27/ReviewSegregator/assets/54547947/a98c0dab-015b-4e92-b075-cc631ab6c2b1">

2. Semantic Analysis Model for restaurants: restaurants can first use Multi-lbl2vec for review segregation and can then combine them with a semantic analyzer to locate exactly where they need improvements. Eg output: 
<img width="408" alt="Screenshot 2023-05-13 at 2 57 20 PM" src="https://github.com/aditjindal27/ReviewSegregator/assets/54547947/b4e4bbc3-76a0-4c7f-b07c-8d3818667206">

