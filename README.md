## Sexism detection in Russian language.

*This is the blog entry, aimed to describe progress on the project conducted within the GSOC 2019.*

**The repository of the project itself can be found [here](https://github.com/clips/gsoc2019_crosslang) and the description of the content of the repository can be found further down**

**N.B.**: we decided to avoid the 4-page-long arxiv publication template, for the sake of completion and full documentation of the process. The references are given in the end of each of the subtopics. 

[Link to useful compilations]() collected by me to conduct a hate speech detection research.


### Part one. Creating sexist corpus and the process of its annotation.

[1.1. The definition of “hate speech” and difficulties of the task.](hate_speech_theory.md)
*(How to define the "hate speech"; what are the common problems with the annotation of hate speech)*

#### 1.2. The process of collecting corpora.
*(Sources of our data, comments to our code to collect the data, description of resulted corpora)*

#### 1.3. The problems with the annotation of our corpora.

*(Linguistical problems, general limitations)*

#### 1.4. The guidelines.

### Part two. Creating a sexism detector.

#### 2.3. Preprocessing of the corpora.

#### 2.2. Attempted models and results.

*(tf-idf + NB, tf-idf + Logistic Regression, pretrained word2vec + Logistic Regression, pretrained word2vec + SVM, pretrained ELMO)*

#### 2.3. Proposed possible improvements or future directions.

