#### 1.2. The process of collecting corpora.
The first source was the Russian social network Vkontakte (avaliable at https://vk.com/ ). It is perfectly equipped for the needs of developers, right inside it is provided with an API with detailed documentation.

We chose three different popular groups in vk, representing three different Russian media. They all have more than 500,000 subscribers, and ideologically they represent different directions.
The media we have chosen are: 

**"Lentach"** (https://vk.com/oldlentach) is a highly oppositional media in the past, now with a slightly less obvious focus, especially interesting because of the huge number of subscribers (over 2 million). Comments are cleaned by the bot: comments shorter than five words are prohibited, which members of the community are fighting with the help of padding - for example, writing five words comments like: "bot blow [me] three four five". Also in the comments obscene words are prohibited, but but not too ingenious, which gives rise to a lot of obscene vocabulary, where words are spelled in the opposite direction or letters are omitted. The rest of the restrictions seem insignificant to us.

**"Medusa"** (https://vk.com/meduzaproject) is a liberal, oppositional media (more than 500,000 subscribers); the only media that promotes feminist views (at least on words). However, there may also be very long sexist debates in the comments. (Comments are open to all)

**"RT News in Russian"** (https://vk.com/rt_russian) - part of Russia Today, basically just automatically post articles published on the portal. Despite the impressive list of rules for commentators, comments are not particularly moderated. Since there are so many posts, the comments are not so numerous, despite the large number of subscribers (over a million).

We approached all these media in the same way, trying to find the comments we are interested in. This function was responsible for collecting the corpus (it can be found [in this file](https://github.com/clips/gsoc2019_crosslang/blob/master/sexism_detector/collect_corpus.py)):
```python
def make_corpus(name,community, query_list, service_token,vk_api_vers):
```
We used it to find posts with any of the words in the query list because we assumed that it was the news related to these topics that would cause the most discussion. Here we also give the translation of the query sheet: 
```python
query_list= {'sexism', 'meToo', 'sexual harassment', 'decriminalization of domestic violence', 'rape', 'feminism', 'Shurygina', 'harassment' }
```
For each post we took only the first hundred comments: quite often news posts were compilative (included several different news), and then the whole dialogue could be devoted to something else. Often, this also turned out to be a type of hate speech, for example, our corpus contains a rather long racist dialogue related to Yakutia.
In the resulting corpus we wrote the post id, comment id, label (by default, it just had "sexist" as label, and then I manually checked the text of the comment). 
![An example of corpus](images/example_corpus.png)
When I checked each comment, I marked the label as one of three possible ones: "sexist", "not sexist" and "sexist in context". The latter category was used for messages that were not sexist in isolation from the context, but worked in this way in conjunction with the post. I did not include them in my train/test datasets, but they also present an interesting potential for analysis. (Read more about this in the last part of our report).
 
