##### 2.1. Preprocessing

The **preprocessing.py** file was responsible for the preprocessing of the text. 
At first I planned to divide the date into test and train by myself and wrote a separate function for this purpose. Later on, it started to seem as not the be the best way to deal with it, that's why in the end I still used the function from the library sklearn to separate the date.

But nevertheless this kind of handling the distribution of comments proved to be useful when preparing for saving processed corpora (it helped to process the data in small portions). 

In the end number of functions were written to preprocess the text, mostly they were using Russian support of nltk.
They were functions to strip the punctuation, extract quotes and references using regular expressions, extract stopwords, and perform lemmatization and stemming. (However, it seems to me that the later ones are not very useful in the case of Russian hate speech detection).
All the resulting texts were saved in the folder "TemporalCorpora" to facilitate the process of preprocessing for those who wish to use this corpus for their research. 
 
 ##### 2.2. Attempted models and their results.
 
I ambitiously planned three different ways of embedding, and several models of different complexity.
I started with a simple tf-idf as an embedding and combined it with a naive bayes classifier. 

Since our corpus is very imbalanced, instead of calculating f1-score, I used a balanced accuracy score as a metric, which is recommended in such cases.
Just in case, we compared the results at different stages of text's preprocessing and then compared the use of logistical regression instead of naive bayes classifier. The results can be found in the table below.

The difference in result between types of preprocessing was not significant. The only interesting thing was, that  it seems that the result is surprisingly worse when both punctuation and stop words disappear from the text. This probably deserves a separate analysis in the future.

Obviously all the results below are not particulary stable and set in stone: the accuracy in this case seemed more like an interval. I dealt with it with possibly slight profanity: just got results five times, each time and found the mean, in attempt to catch the logic behind change.
 
 type | tf-idf + NB | tf-idf + Logistic Regression 
------------ | ----------|------------ 
no preprocessing | 63% | 62%
minus quotes and references | 64% | 64%
minus punctuation | 61 % | 64%
minus all above | 62% | 62%
lemmatization + all above | 66% | 63%

In the last few days, while I was in a hurry to finish this report, I had a late but interesting idea. I realized that I could still make my corpus less imbalanced, which could change the results somehow.

To do this, I excluded completely non-sexist corpus (ns_1.csv) from my final test/train. My  corpus continued to be imbalanced: I still had to use a balanced accuracy score as a metric, but now the data was more like 2,000 to 8,000, not 2,000 to 20,000.

The result was instantaneous and significantly improved. Unfortunately, the idea came to me too late, so I couldn't test it as thoroughly as I wanted, but the results can still be found in the table below. 

 type |  tf-idf + Logistic Regression 
------------ | ----------
no preprocessing |  73%
minus quotes and references |  71%
minus punctuation | 70% 
minus all above | 69% 
lemmatization + all above | 74% 

More advanced type of embeddings, which I have attempted, are ELMO. Our architecture was quite simple: we used ELMO embeddings - first, we used pretrained embedding in Russian, then trained it on our own (our resulted options and weight file can be found here in the repository), then plugged the results into LSTM, then to the simple feedforward neural network of one layer.

Because the training of ELMO took something which seemed like a million hours, I couldn't play around much with data and also only tried it exclusively on my very imbalanced corpus.
Nevertheless the results were pretty nice
 type | (finetuned by me) ELMO | (pretrained **and** finetuned by me) ELMO 
------------ | ---------- | -----------
no preprocessing |  67% | 74%
Both numbers are given in the same balanced accuracy score.

