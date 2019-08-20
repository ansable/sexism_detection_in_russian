#### 1. The definition of “hate speech” and problems and difficulties of the task.

Hate speech is difficult to define, and even after agreeing on some sort of definition, is still proving to be complicated to attribute something (a tweet or a message) to the hate speech.

In the article *"Measuring the Reliability of Hate Speech Annotations: The Case of the European Refugee Crisis"* authors noted that the agreement between the annotators of their hate speech corpus (measured with Krippendorff's alpha coefficient) ranged from 0.18 to 0.29, much lower than recommended coefficient of 0.8. 

Even more important is that after the annotators were acquainted with the definition of hate speech, a significant improvement of the coefficient did not follow. Similar thoughts are found in the paper *“Are You a Racist or Am I Seeing Things?"*, where the author faced a similar problem. In this article an attempt was made to compare the decisions from expert and amateur annotators. The mutual influence on attribution decisions was compared, and special attention was paid to annotation of tweets in two different corpora (one of them was made specifically for the purposes of the article, another was made for the article *“Hateful symbols or hateful people? predictive features for hate speech detection on twitter”*). By how different the labels turned out to be, one can draw additional conclusions about subjectivity of attribution attempts. The author of the article claims, that annotations made by amateur annotators should be accepted only if there is a complete agreement. They also support previous authors in the idea that the process of attribution is complicated without the intimate knowledge of the topic.

Similar ideas can be found in the article *“Abusive Language Detection in Online User Content”*, where the authors conducted so-called “Amazon Turk Experiment ”, where they hired several amateur annotators (not allowing each of them to annotate more than 50 text entities). The annotators were acquainted with guidelines, used by expert annotators. The agreement rate was acceptable only for the binary classification (coefficient of 0.867), but it dropped significantly for the categorical task. That could suggest that either there is a need for more extensive training, or that amateurs are much worse suited for the annotation task.

Some of the problems in the attribution can arise because of the focus on the word level, instead of tweet/message as an entity itself. This focus on words can be problematic in two ways. 

First, the problem of attribution something to the “hate speech” category is not limited to the question what is a hate speech. The article *“Automated Hate Speech Detection and the Problem of Offensive Language”* demonstrates how mutually confusable are hate speech and offensive language. 

Another problem is connected with the sarcasm or quotes of the opponent arguments, and it will be mentioned later.

In this work we hoped that because such specific area of the problem is picked (sexism detection) and because the annotator is familiar with the problem on more personal level, it will be easier to distinguish between the categories. Nevertheless, several problem arose. 
It is also worth noting, that while we were in the process of research, and first thought about just picking “hate speech” as the topic, we made a list of many publicly available or semi publicly available corpora. They are mainly in English, and there could be different annotation approaches, but it could be found helpful later for some further hate-speech research. You can find [the whole list here](https://github.com/clips/gsoc2019_crosslang/blob/master/theoretical_support/list%20of%20hate-speech%20corpora.ods).

#### References:
*All references are provided with links to the articles*

Thomas Davidson, Dana Warmsley, Michael Macy, and Ingmar Weber. 2017. [Automated Hate Speech Detection and the Problem of Offensive Language.](https://arxiv.org/pdf/1703.04009.pdf) 11th International Conference on Web and Social Media (ICWSM), pages 512–515, Montreal, Quebec, Canada 

C. Nobata, J. Tetreault, A. Thomas, Y. Mehdad, and Y. Chang. 2016. [Abusive language detection in on-line user content.](http://www.yichang-cs.com/yahoo/WWW16_Abusivedetection.pdf) In 25th International World WideWeb Conference, WWW 2016, pages 145–153 

Bjorn Ross, Michael Rist, Guillermo Carbonell, Benjamin Cabrera, Nils Kurowsky, and Michael Wojatzki. 2016. [Measuring the reliability of hate speech annotations: The case of the European refugee crisis.](https://arxiv.org/pdf/1701.08118.pdf) Bochum, Germany, September. 

Zeerak Waseem. 2016. [Are you a racist or am I seeing things? Annotator influence on hate speech detection on Twitter.](https://www.aclweb.org/anthology/W16-5618) 1st Workshop on Natural Language Processing and Computational Social Science, pages 138–142. 

Zeerak Waseem and Dirk Hovy. 2016. [Hateful symbols or hateful people? predictive features for hate speech detection on twitter.](https://www.aclweb.org/anthology/W16-5618) NAACL Student Research Workshop, San Diego, California, June. Association for Computational Linguistics. 
