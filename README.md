## Sexism detection in Russian language.

*This is the blog entry, aimed to describe progress on the project conducted within the GSOC 2019.*

**The repository of the project itself can be found [here](https://github.com/clips/gsoc2019_crosslang) and the description of the content of the repository can be found further down, [here]()**

**N.B.**: we decided to avoid the 4-page-long arxiv publication template, for the sake of completion and full documentation of the process. List of all references with links can be found after part one. 

### Part one. Creating sexist corpus and its annotation.

#### 1. The definition of “hate speech”.

Hate speech is difficult to define, and even after agreeing on some sort of definition, is still proving to be complicated to attribute something (a tweet or a message) to the hate speech.

In the article *"Measuring the Reliability of Hate Speech Annotations: The Case of the European Refugee Crisis"* authors noted that the agreement between the annotators of their hate speech corpus (measured with Krippendorff's alpha coefficient) ranged from 0.18 to 0.29, much lower than recommended coefficient of 0.8. 

Even more important is that after the annotators were acquainted with the definition of hate speech, a significant improvement of the coefficient did not follow. Similar thoughts are found in the paper *“Are You a Racist or Am I Seeing Things?"*, where the author faced a similar problem. In this article an attempt was made to compare the decisions from expert and amateur annotators. The mutual influence on attribution decisions was compared, and special attention was paid to annotation of tweets in two different corpora (one of them was made specifically for the purposes of the article, another was made for the article *“Hateful symbols or hateful people? predictive features for hate speech detection on twitter”*). By how different the labels turned out to be, one can draw additional conclusions about subjectivity of attribution attempts. The author of the article claims, that annotations made by amateur annotators should be accepted only if there is a complete agreement. They also support previous authors in the idea that the process of attribution is complicated without the intimate knowledge of the topic.

Similar ideas can be found in the article *“Abusive Language Detection in Online User Content”*, where the authors conducted so-called “Amazon Turk Experiment ”, where they hired several amateur annotators (not allowing each of them to annotate more than 50 text entities). The annotators were acquainted with guidelines, used by expert annotators. The agreement rate was acceptable only for the binary classification (coefficient of 0.867), but it dropped significantly for the categorical task. That could suggest that either there is a need for more extensive training, or that amateurs are much worse suited for the annotation task.

Some of the problems in the attribution can arise because of the focus on the word level, instead of tweet/message as an entity itself. This focus on words can be problematic in two ways. 

First, the problem of attribution something to the “hate speech” category is not limited to the question what is a hate speech. The article *“Automated Hate Speech Detection and the Problem of Offensive Language”* demonstrates how mutually confusable are hate speech and offensive language. 

Another problem is connected with the sarcasm or quotes of the opponent arguments, and it will be mentioned later.

In this work we hoped that because such specific area of the problem is picked (sexism detection) and because the annotator is familiar with the problem on more personal level, it will be easier to distinguish between the categories. Nevertheless, several problem arose. 
It is also worth noting, that while we were in the process of research, and first thought about just picking “hate speech” as the topic, we made a list of many publicly available or semi publicly available corpora. They are mainly in English, and there could be different annotation approaches, but it could be found helpful later for some further hate-speech research. You can find [the whole list here](https://github.com/clips/gsoc2019_crosslang/blob/master/theoretical_support/list%20of%20hate-speech%20corpora.ods).

