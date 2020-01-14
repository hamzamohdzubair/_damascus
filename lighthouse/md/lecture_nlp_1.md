---
theme: beige
transition: slide
slideNumber: true
title: NLP101
logoImg: https://i.imgur.com/Xpd2e0z.jpg
---

# NLP 101

Hamza Mohd. Zubair

---

## Topics

1. Introduction and Basic Concepts {.fragment}
2. Regex {.fragment}
3. Language Models {.fragment}
4. Sentiment Classification {.fragment}
5. Vector Semantics & Embeddings {.fragment}
6. Constituency Grammars {.fragment}
7. Constituency Parsing {.fragment}
8. Dependency Parsing {.fragment}
9. Recurrent Networks {.fragment}

---

## Introduction

--

#### NLP

Natural Language Processing {.fragment}

--

#### Text Processing

All text manipulation techniques and algorithms. {.fragment}

Speech Processing + Text Processing = NLP {.fragment}

--

#### NLU

Natuaral Language Understanding {.fragment}

<span class='fragment'>A subset of NLP</span><span class='fragment'>, more advanced algorithms,</span> <span class='fragment'> focused on semantics.</span>

--

#### Syntax vs Semantics

Grammar vs Meaning {.fragment}

--

#### NLG

Natural Language Generation {.fragment}

Algorithms used for generating natural language utterances {.fragment}

--

Technically

When people say NLP, they mean ... {.fragment}

The technically correct terminology is ... {.fragment}

### Text Understanding {.fragment}

---

## NLP is important

--

### Here's Why

--

![Imgur](https://i.imgur.com/DhFbwaX.jpg =500x700)

--

Most of **you** work with

#### Structured Data {.fragment}

--

#### But

90% of all data in the world is{.fragment}

### Unstructured Data {.fragment}

--

#### And Most of it is

### TEXT {.fragment}

--

#### Example

News Feeds {.fragment}

Blogs {.fragment}

Social Media Updates {.fragment}

Tweets {.fragment}

Text Messages {.fragment}

Searches {.fragment}

... {.fragment}

--

Important thing about text

> "Text Data is a mess" {.fragment}

-- Someone with NLP experience {.fragment}

---

## Basic Concepts

--

#### Tokens

Words, numbers {.fragment}

any singular unit of NLP {.fragment}

**exercise:** {.fragment}

> This sentence was written in 2019. Yo wassup! {.fragment}

<span class='fragment'> Tokens => </span><span class='fragment'>8</span>

--

#### Types

Unique Tokens {.fragment}

> This sentence was written to be written exactly where it is written {.fragment}

<span class='fragment'> Tokens => </span><span class='fragment'>12</span>
<span class='fragment'> Types => </span><span class='fragment'>10</span>

--

#### Word Sense

> I have a lot of **interest** in NLP {.fragment}

> I got a loan on 8% **interest** {.fragment}

--

#### Parts-of-Speech

![Imgur](https://i.imgur.com/XePkaJZ.png?1) {.fragment}

--

![Imgur](https://i.imgur.com/RoEOuMR.png)

--

![Imgur](https://i.imgur.com/QCExtuz.png =800x600)

--

#### Lemma

**Grammatical Root** of a word {.fragment}

with the same **word sense** {.fragment}

and the same **part-of-speech** {.fragment}

**exercise:** {.fragment}

> Who wrote the writing where it is written {.fragment}

<span class='fragment'> Tokens => </span><span class='fragment'>8</span>
<span class='fragment'> Types => </span><span class='fragment'>8</span>
<span class='fragment'> Lemma => </span><span class='fragment'>7</span>
<span class='fragment'> Word Family => </span><span class='fragment'>6</span>

--

**exercise:**

> I came I saw I concordanced, I come I see a concordance {.fragment}

![Imgur](https://i.imgur.com/a8yVb6Q.png?1) {.fragment}

--

#### Utterance

A sentence in speech processing. {.fragment}

> "I do uh main- mainly business data processing" {.fragment}

**examples:** {.fragment}

transcripted telephone conversations {.fragment}

song lyrics {.fragment}

movie subtitles {.fragment}

--

#### Disfluencies

sounds that break the flow {.fragment}

1. fragments {.fragment}
2. fillers {.fragment}

--

### Language Issues

Most advanced tools work only for {.fragment}

**English** {.fragment}

Next best in line are ... {.fragment}

<span class='fragment'>Chinese</span> <span class='fragment'>, Spanish</span><span class='fragment'>, Arabic</span>

1. Non-ASCII characters {.fragment}
2. latinised words {.fragment}
3. Vernaculars {.fragment}

**example:** {.fragment}

AAVE (African American Vernacular English) {.fragment}

<span class='fragment'>iont =></span><span class='fragment'>I don't</span>

<span class='fragment'>talmbout =></span><span class='fragment'>talking about</span>

--

#### Code switching

> "dost tha or rahega... dont worry ... but dherya rakhe" {.fragment}

--

#### Corpus

A computer-readable collection of text or speech {.fragment}

pl: Corpora {.fragment}

--

#### Examples of Large Corpora

![Imgur](https://i.imgur.com/lIGIefc.png?1) {.fragment}

--

#### Stopwords

List of common words like {.fragment}

<span class='fragment'>is, are, i, me, myself, you, he, she,</span> <span class='fragment'>his, her, it, this, that, are, was, be,</span> <span class='fragment'>have, had, at, of, in, because, about, of, on, here, there ...</span>

~ **Function Words** {.fragment}

(articles, pronouns, prepositions) {.fragment}

---

## Basic Techniques

#### (Preprocessing)

1. Segmentation {.fragment}
2. Tokenization {.fragment}
3. Normalization {.fragment}

---

### Segmentation

Breaking text into sentences. {.fragment}

--

> This is a paragraph. How do you think you will divide this? Put on your thinking hat guys! We are four sentences.

--

> This is also a paragraph. Don't be a Mr. Potato Head. The movie Monsters Inc. is awesome. This is also four sentences ;-D

--

### Tokenization

Breaking up into tokens {.fragment}

--

### Normalization

Bringing all words into a standard format. {.fragment}

1. Lemmatization {.fragment}
2. Stemming {.fragment}

--

#### Lemmatization

Breaking up into Lemmas {.fragment}

--

#### Stemming

![Imgur](https://i.imgur.com/5xsvA4n.png)

--

#### Case Folding

Convert all to lower case or all to upper case {.fragment}

---

## Minimum Edit Distance

minimum number of editing operations {.fragment}

(insertion, deletion, substitution) {.fragment}

needed to transform one string into another {.fragment}

Also called **Levenshtein** Distance {.fragment}

--

#### Used in

Spelling Corrections {.fragment}

Coreference {.fragment}

--

example:

**cartesin consulting** {.fragment}

EDIT Distance (**cartesian**) = 1 {.fragment}

--

example:

College President Manmohan {.fragment}

Engineering College President Manmohan {.fragment}

--

#### OPERATIONS

I
D
S {.fragment}

--

**exercise:**

MONEY -> MONKEY {.fragment}

--

**exercise:**

EXCITED -> EXCITE {.fragment}

--

**exercise:**

MILLION -> BILLLION {.fragment}

--

**exercise:**

RELEVANT -> ELEPHANT {.fragment}

--

**exercise:**

INTENTION -> EXECUTION {.fragment}

--

**answer:**

![Imgur](https://i.imgur.com/OK6Yl5v.png) {.fragment}

--

#### Alignment

Correspondence between substrings

--

#### Algorithms for MED

- Tree Searching
- Dynamic Programming
  - Viterbi Algorithm
  - CKY

---

## Thank you

#### Link
https://hamzamohdzubair.github.io/lighthouse/html/lecture_nlp_1#/
