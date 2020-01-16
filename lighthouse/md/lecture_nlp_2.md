---
theme: beige
transition: slide
slideNumber: true
enableZoom: true
title: NLP102
logoImg: https://i.imgur.com/Xpd2e0z.jpg
---

# NLP 102

Hamza Mohd. Zubair

---

## NLP Series

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

### What is a regular expression?

Advanced Search Tool {.fragment}

--

### How old is it?

Conceptualised in 1950s {.fragment}

--

Enough Theory Already!

#### Let's practice {.fragment}

### regex101.com {.fragment}

---

## Tutorial 1

--

Try this
```
abc
```

--

Try this
```
cba
```

--

Try this
```
expression
```

--

Try this
```
1950
```

--

Try this
```
1980
```

--

> Both 1950 and 1980

--

Answer
```
19[58]0
```
--

#### Character class

--

Try this
```
19[123]0
```

--

> 1900 to 1990

--

Answer
```
19[0123456789]0
```

--

Try this
```
19\d0
```

--

####  Metasequences

--

Check quick reference

--

> 1920 - 1960

--

Answer
```
19[2-6]0
```

--

Try this
```
regular expression
```
we missed one in third paragraph

--

> regular expression

> Regular expression

--

Answer
```
[Rr]egular expression
```

--

> pin, sin, tin, win

--

Answer
```
[p-w]in
```

--

Do not try
```
abc
```
Guess number of matches

--

Do not try
```
[abc]
```
Guess number of matches

--

> 1900, 1910, 1920, 1970, 1980, 1990

--

Answer
```
19[0-27-9]0
```

--

Try this
```
19[^3-6]0
```

--

Try this
```
19[^3-6a-z ]0
```

--

> Challenge in the third paragraph

--

Answer
```
19\[123\]0
```

--

Answer
```
19\\d0
```

--

> [1][2][3]...

--

Answer
```
\[\d]
```

---

### Summary

--

### []
Character set {.fragment}
Disjunction set {.fragment}

--

### --
Range operator {.fragment}

--

### ^
Negation operator {.fragment}

--

**\d**

Metasequence {.fragment}

--

#### Metasequences

- \d
- \w
- \s

--

#### some characters need to be escaped to match

Metacharacters {.fragment}

.[{()\^$|?*+ {.fragment}


---

## Tutorial 2

--

Try this
```
navratri
```

> Navratri

> Navaratri

--

Answer
```
nava?ratri
```

--

### ?
Quantifier {.fragment}

--

Try this
```
hello
```

--

> Match all spellings of hello

--

Try this
```
hell*o
```

--

Try this
```
hell+o
```

--

#### Quantifiers

Quantifier | Meaning
------|----
? | 0 or 1
* | 0 or more
+ | 1 or more

--

Try this
```
alo{1,20}t
```

--

Try this
```
.
```

--

Find the difference
```
.
```
```
.*
```
--

#### Metasequences

Metasequence | Meaning| Opposite
-------------|-----|----
\d | 0-9 | \D
\w | a-zA-Z | \W
\s | \<space> | \S

Try them
```
\d
\w
\s
```
--

Find the difference
```
.in
```
```
\win
```

--

Find the difference
```
\win
```
```
\bwin
```
```
\bwin\b
```
--

### Anchors

Anchors| Meaning
----|----
\b | word boundary
^ | Beginning of sentence
$ | End of sentence
--

Find the difference
```
\d
```
```
\d+
```
--


---


#### Exercise

> Find all Diwalis

--

Answer
```
[Dd][ei]*(pa)?[wv]a*li*
```

---

### Summary

- Metacharacters
- Metasequences
- Anchors
- Quantifiers
- Groups
- Flags/Modifiers

---

## Anchors

---

## Qurantifiers

---

## Flags


```
/<expression>/<flags>

```

---

#### Thank you!

