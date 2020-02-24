---
theme: beige
transition: slide
slideNumber: true
enableZoom: true
title: NLP103
logoImg: https://i.imgur.com/Xpd2e0z.jpg
---

# NLP 103

Hamza Mohd. Zubair

---

## NLP Series

1. Introduction and Basic Concepts {.fragment}
2. Regex {.fragment}
3. NLP with Python {.fragment}


---

### Let's Practice!


---

### NLTK

Oldest NLP Library of Python {.fragment}

Base of all other NLP libraries {.fragment}

---

#### Getting Started


```python
import nltk
nltk.__version__
dir(nltk)
dir()
```
load library and check version {.fragment .current-only data-code-focus=1-2}

all objects and modules inside nltk {.fragment .current-only data-code-focus=3}

python tip {.fragment .current-only data-code-focus=4}

{.fragment .current-only data-code-focus=1-4}

--

#### Corpus


```python
nltk.corpus.gutenberg.fileids()

w = nltk.corpus.gutenberg.words()
len(w)

s = nltk.corpus.gutenberg.sents()
len(s)

from nltk.corpus import webtext
webtext.raw(<fileid>)
```
files inside a corpus {.fragment .current-only data-code-focus=1}

all words inside a corpus {.fragment .current-only data-code-focus=3-4}

all sentences {.fragment .current-only data-code-focus=6-7}

corpus of scrapped text from the web {.fragment .current-only data-code-focus=9-10}

{.fragment .current-only data-code-focus=1-10}

--

Exercise

> Print out first 100 characters of each file

```{.fragment}
for file in webtext.fileids():
    print(file, webtext.raw(file)[:100])
```

--

![Imgur](https://i.imgur.com/4rof8tf.png?1)

--

#### More Corpora


```python
from nltk.corpus import brown

brown.fileids()
brown.categories()
brown.fileids(categories='fiction')
brown.words(categories=['romance','adventure'])

from nltk.corpus import indian
indian.fileids()
indian.words('hindi.pos')
```
load brown corpus {.fragment .current-only data-code-focus=1}

all files {.fragment .current-only data-code-focus=3}

all categories {.fragment .current-only data-code-focus=4}

all files within a category {.fragment .current-only data-code-focus=5}

all words within a category {.fragment .current-only data-code-focus=6}

indian files {.fragment .current-only data-code-focus=8-9}

hindi words {.fragment .current-only data-code-focus=10}

{.fragment .current-only data-code-focus=1-10}

--

#### Tokens and Types

```python
len(nltk.corpus.movie_reviews.words())
len(set(nltk.corpus.movie_reviews.words()))
```
tokens {.fragment .current-only data-code-focus=1}

types {.fragment .current-only data-code-focus=2}

{.fragment .current-only data-code-focus=1-4}

Lexical Diversity = Types / Tokens {.fragment}

--

#### NLTK Text Objects


```python
from nltk import Text
all_words = brown.words(categories='romance')
text_object = Text(all_words)
text_object.count('love')

from nltk import FreqDist
dist = FreqDist(text_object)
dist.most_common(20)
dist['love']
dist.freq('love')
dist.plot(100)
dist.hapaxes()

text_object.concordance('love')
text_object.similar('love')
text_object.common_contexts(['love', 'hate'])
text_object.dispersion_plot(['love', 'hate'])
nltk.Text(nltk.corpus.reuters.words(categories=['trade','fuel'])
.dispersion_plot(['war','money','oil'])
```
import text class {.fragment .current-only data-code-focus=1}

all words in one category {.fragment .current-only data-code-focus=2}

create text object {.fragment .current-only data-code-focus=3}

count occurence {.fragment .current-only data-code-focus=4}

frequency distributions {.fragment .current-only data-code-focus=6-8}

word count {.fragment .current-only data-code-focus=9}

Percentage {.fragment .current-only data-code-focus=10}

frequency plot {.fragment .current-only data-code-focus=11}

Rarest of the rare {.fragment .current-only data-code-focus=12}

concordance {.fragment .current-only data-code-focus=14}

words with similar context {.fragment .current-only data-code-focus=15}

common context {.fragment .current-only data-code-focus=16}

dispersion plots {.fragment .current-only data-code-focus=17}

dispersion plot in one line {.fragment .current-only data-code-focus=18-19}

{.fragment .current-only data-code-focus=1-20}

--

Exercise

> Filter out words that are less than 6 chars long and then look at most common words

```{.fragment}
w = [w for w in set(text_object) if len(w) > 6]
```

> Filter out words that are less than 6 chars long and occur less than 15 times and then look at most common words

```{.fragment}
w = [w for w in set(text_object) if len(w) > 6 and dist[w] > 15]
```

--

#### Hapax Legomenon

- Term used by Computational Linguists

![Imgur](https://i.imgur.com/44eNxhH.png)

--

#### Zipf's Law

- The frequency of any word is inversely proportional to its rank in the frequency table.

![Imgur](https://i.imgur.com/hVxM6B7.png)

--

#### Zipf's Law

![Imgur](https://i.imgur.com/62t1j3N.png)

--

#### Zipf's Law

![Imgur](https://i.imgur.com/IQEPqlT.png)

--

#### Zipf's Law

- Applies to many naturally occuring phenomenon
- Population of cities {.fragment}
- Number of stars in Galaxies {.fragment}
- Neuron Activity in Brain {.fragment}
- Employees in Corporations {.fragment}
- Number of people watching a TV show {.fragment}

---

#### N-grams

![Imgur](https://i.imgur.com/MBNsIyq.png) {.fragment}

![Imgur](https://i.imgur.com/wTjLplf.png) {.fragment}

--

#### Ngrams and Collocations

```python
import nltk
w = nltk.corpus.brown.words(categories=['romance','adventure'])
list(nltk.ngrams(w, 2))
list(nltk.ngrams(w, 5))

nltk.Text(w).collocations()
```
2-grams and 5-grams {.fragment .current-only data-code-focus=1-4}

Frequent Phrases: Words, that occur frequently together but rarely alone {.fragment .current-only data-code-focus=6}

{.fragment .current-only data-code-focus=1-20}

---

#### Lexicon

--

A collection of words and/or phrases along with associated information such as part of speech and sense definitions

--

In Computational Linguistics

Most popular lexicon is a dictionary

--

#### Simplest Lexicon

```python
import nltk
stopwords = nltk.corpus.stopwords.words('english')
```
stopwords {.fragment .current-only data-code-focus=1-2}

Frequent Phrases: Words, that occur frequently together but rarely alone {.fragment .current-only data-code-focus=6}

{.fragment .current-only data-code-focus=1-20}

--

Exercise

> Find percentage of stopwords in any text corpora

```{.fragment}
text = nltk.corpus.nps_chat.words()
stopwords = nltk.corpus.stopwords.words('english')
content = [w for w in text if w.lower() not in stopwords]
len(content) / len(text)
```


> Remove stopwords and then look at most common words

```{.fragment}
text = nltk.corpus.nps_chat.words()
stopwords = nltk.corpus.stopwords.words('english')
content = [w for w in text if w.lower() not in stopwords]
dist = nltk.FreqDist(nltk.Text(content))
dist.most_common(20)
```

--

#### Word Puzzle

![Imgur](https://i.imgur.com/HVJKoUU.png?1)

```{.fragment}
puzzle_letters = nltk.FreqDist('egivrvonl')
obligatory = 'r'
wordlist = nltk.corpus.words.words()
[w for w in wordlist if len(w) >= 4
                     and obligatory in w
                     and nltk.FreqDist(w) <= puzzle_letters]
```

--

#### Conditional Freq Dist

```python
names = nltk.corpus.names
cfd = nltk.ConditionalFreqDist(
          (fileid, name[-1])
          for fileid in names.fileids()
          for name in names.words(fileid))
cfd.plot()
```

names corpus {.fragment .current-only data-code-focus=1}

{.fragment .current-only data-code-focus=1-10}

---

#### Wordnet

Largest Computational Linguistics Project {.fragment}

![Imgur](https://i.imgur.com/0LQruOP.png) {.fragment}

--

#### Wordnet vs Dictionary

![Imgur](https://i.imgur.com/rebB7WC.png)

--

#### Semantic Relations

![Imgur](https://i.imgur.com/4WaFknO.png)

--

#### Hindi Wordnet

![Imgur](https://i.imgur.com/0L5bkpq.png)

--

![Imgur](https://i.imgur.com/arnuLwG.png)

--

#### Wordnet Applications

- Machine Translation
- Word Sense Disambiguation
- Sentiment Analysis
- Information Retrieval
- MultiWord Expression Detection
- Document structuring and categorization
- Cognitive NLP

--

#### Wordnet getting started

```python
from nltk.corpus import wordnet as wn

wn.synsets('car')
wn.synsets('car')[0].definition()
wn.synsets('car')[0].example()
wn.synsets('car')[0].lemma_names()
wn.synsets('auto')
wn.synsets('machine')
wn.synset('car.n.01')
wn.synset('car.n.02').lemma_names()
```

load wordnet {.fragment .current-only data-code-focus=1}

main unit of wordnet "synonym set" {.fragment .current-only data-code-focus=3}

definition {.fragment .current-only data-code-focus=4}

example sentences {.fragment .current-only data-code-focus=5}

Words that point to the same synset and mean the same thing {.fragment .current-only data-code-focus=6}

Words that have one synset are called unambiguous, otherwise they are ambiguous {.fragment .current-only data-code-focus=7-8}

selecting a synset {.fragment .current-only data-code-focus=9}

The words that mean the second sense of car {.fragment .current-only data-code-focus=10}

{.fragment .current-only data-code-focus=1-10}

--

Exercise

> Print out the list of words that make a synset, definition and example sentences for each synset

```{.fragment}
for syn in wn.synsets('car'):
    print(syn.name())
    print(syn.lemma_names())
    print(f'Def: {syn.definition()}')
    print(f'Ex: {syn.examples()}\n')
```

--

#### Wordnet Lexical relations

```python
from nltk.corpus import wordnet as wn
wn.synsets('cat')

cat = wn.synset('cat.n.01')
cat.definition()
cat.hyponyms()
cat.hypernyms()

cat.hypernym_paths()
cat.path_similarity(wn.synsets('dog.n.01'))

wn.synset('cat.n.01').lowest_common_hypernyms(wn.synset('dog.n.01'))
```

synsets {.fragment .current-only data-code-focus=1-2}

check definition {.fragment .current-only data-code-focus=4-5}

one-level up and down {.fragment .current-only data-code-focus=6-7}

path similarity {.fragment .current-only data-code-focus=9-10}

node of divergence {.fragment .current-only data-code-focus=12}

{.fragment .current-only data-code-focus=1-20}

---

#### Summary

- Corpus {.fragment}
    - Files, words, sents, categories
    - Brown, Gutenberg, Retuers, NPS_Chat, Hindi
- Types and Tokens {.fragment}
    - Percentage
    - Lexical Diversity
- Text Objects {.fragment}
    - Counts, Frequency Distributions, Most Common Words, Hapaxes
    - Concordance, Similar Context, Common Contexts, Dispersion Plots
- Zipf's Law {.fragment}
--

#### Summary

- Ngrams {.fragment}
    - Bigrams, Trigrams
    - Collocations
- Lexicon {.fragment}
    - Difference between Lexicon and corpus, dictionary, stopwords
    - Conditional Frequency Distribution
- Wordnet {.fragment}
    - Difference between wordnet and dictionary
    - Applications
    - Synsets, Lemmas
    - Lexical Relations: Hyponyms, Hypernyms and Paths

--

#### Exercise

> Word Puzzle

> Play with Wordnet

--

Thanks!

All the best!