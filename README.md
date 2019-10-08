# Building a Naive-Bayes Classifier
Program written and developed in the language Python as the first project for the subject COMP30027: Machine Learning at the University of Melbourne - Semester 1, 2019.

### Goal: 
To implement a supervised Naive Bayes learner, evaluate it with respect to various supervised datasets, and examine the impact of attribute correlation on the classifier. To be able to critically reason with a simple Naive-Bayes classifier based on the observations and analyses.

---
### The Core of Naive Bayes Probabilistic Model
![naive-bayes](https://raw.githubusercontent.com/nickangmc/naive-bayes-classifier/master/readme-images/naive-bayes-concept.png)

### Tasks:
- To code a learner from scratch based on Naive-Bayes concept.
- To implement probabilistic smoothing to improve the performance.
- To be able to make predictions given a dataset.
- To evaluate the predictions and output its evaluation metrics.
- To examine the impact of attribute correlation have on the classifier (Information Gain & Entropy).

### Classifier Performance:
There were 8 datasets used in evaluating the performance of the classifier. Note that the datasets were used for both training and testing in this project for learning purposes.

e.g.
1. For Nursery dataset:
    - Derived from (https://archive.ics.uci.edu/ml/datasets/Nursery). 
    - It is comprised of 12960 instances, with 8 attributes (9 including the class). There are five possible class labels: {not_recom, recommend, very_recom, priority, spec_prior}. There are no missing values in this dataset.
    - Evaluation metrics:

         ![nursery-evaluation](https://raw.githubusercontent.com/nickangmc/naive-bayes-classifier/master/readme-images/nursery-evaluation.png)

2. For Breast-Cancer dataset:
    - Derived from (https://archive.ics.uci.edu/ml/datasets/Breast+Cancer). 
    - It is comprised of 286 instances, with 9 attributes (10 including the class). There are two possible class labels: {recurrence-events, no-recurrence-events}. There are a small number of missing values in this dataset, which are indicated by a question mark ("?").
    - Evaluation metrics:

         ![breast-cancer-evaluation](https://raw.githubusercontent.com/nickangmc/naive-bayes-classifier/master/readme-images/breast-cancer-evaluation.png)

---
### Analysis
##### The following is my own interpretation and attempt to answer the question given. There were 2 questions that I've attempted in total, feel free to check out the code file (.ipynb) for more details.

- How does information gain of each attribute, with relative to the class distribution, affect the behaviours of the classifier?

By the definition of information gain, it is “the expected reduction in the entropy (the amount of unpredictability) caused by knowing the values of an attribute”.

If an attribute has high information gain relative to the class distribution, by knowing the value of the attribute, it reduces the amount of unpredictability for the given class, or in other words, the classifier is able to identify the class label that is generated partly from the attribute value with more confidence. Hence, attribute that have information gain increases the likelihood for the classifier to make accurate predictions.

 However, information gain alone is not sufficient to explain the behaviour of the classifier in the entropy context. Root entropy (the unpredictability in the class distribution) together with information gain can then largely suggest the effectiveness of the classifier. High root entropy suggests high unpredictability, that the class distribution is fairly even, no particular class label is significantly more probable than the other, predictions are unlikely to be accurate as a result. Hence, in most cases where root entropy is high, attributes with high information gain are necessary to make accurate predictions, conversely, in most cases where root entropy is low, it is not necessary to have attributes with high information gain relatively in order to make accurate predictions.

One particular surprising result is that the value of accuracy stays the same even with respect to different attributes. This is observed across several datasets, namely 'breast-cancer.csv', 'hepatitis.csv', 'hypothyroid.csv', and 'mushroom.csv'. The reason being that all these datasets only have two class labels, where one true positive prediction with respect to the first class label becomes the true negative prediction with respect to the second class. Since that accuracy by definition is (true positives + true negatives)/(total predictions) and that the values of sums of true positives and true negatives are the same for both class labels, they have the same accuracy value.

---

### Project Outcome
All the tasks and challenges within the scope of this project were completed. 

