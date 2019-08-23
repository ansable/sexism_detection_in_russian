##### 2.1. Preprocessing

The preprocessing.py file was responsible for preprocessing the text. At first I planned to divide the date into test and train by myself and wrote a separate function for this purpose. Later on, it didn't seem to be the best way to do it, that's why in the end I still used the function from sklearn to separate the date.

But this kind of distribution of information proved to be useful when preparing for saving processed cases.  As a result, functions were written to clear the text of punctuation, extract quotes and references using regular expressions (for example), extract stop words, perform lemmatization and stammatization. (However, it seems to me that lemmatization and stammatization are not very useful in this case).
All the resulting texts were saved in the folder "Temporary" to facilitate the process of preprocessing for those who wish to use this corpus for their research. 
 
 
 | tf-idf + NB | tf-idf + Logistic Regression | pretrained word2vec + Logistic Regression | pretrained word2vec + SVM | pretrained ELMO | trained ELMO
------------ | ----------|------------ | ----------|------------ | ----------|------------ 
| Content from cell 2
Content in the first column | Content in the second column
