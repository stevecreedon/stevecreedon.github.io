---
layout: post
title: "LDA Overview"
date: 2016-09-07 21:37:00 +0100
categories: lda nlp
---

t resolver.co.uk we need some form of topic discovery from our large corpus of email conversations. I'm not trying to understand LDA analysis in its full scientific or mathematical depth but just how it works so we can attempt to get the best out of it. 

This is my best shot:

## Assumptions

Say we have 1000 documents.

Let's make some huge assumptions:

1. Distributed across these documents we have 10 topics. We don't know the topics and we don't know which document has which of these mystery topics.  

2. Each topic is made up of a bag of words, each word being unique to each topic. In other words:

Topic 'Dirty' has the words 'dirty', 'stained', 'yellowing', 'filthy', 'marked'
Topic 'Rude' has the words 'rude', 'unhelpful', 'unpleasant', 'aggressive'

The meaning of each topic above is obvious but remember at this stage we don't know the topics and we don't know the words in any of the 10 topic's bag of words.

3. Let's make an even bigger assumption that isn't necessary for LDA but I'm going to use it to make this example as clear as possible. Let's assume these topics are evenly distributed and each document only has 1 topic. In other words, in our 1000 documents there are 10 topics, each topic having 100 documents.

## Stage 1.

So remember we believe that there are 10 topics each with 100 documents and each topic is present in only one document. So for any given document the distribution of topics is:

100% topic X and 0% on any of the other topics.

We have no idea what these topics are and what these words are so lets go through the corpus and let's assign each word randomly to our 10 topics.

If we then assign a topic to each document based on words in that topic's bag then this random distribution should give us something like:

10% of the words in each document are assigned to each topic so this first totally random iteration suggests that each of our 10 topics is in each of our 1000 documents covering 10% of the words.

If we move one of the words into another topic that distribution may change slightly. We may go from our totally random 10 topics in each document covering 10% of the words per topic to, say, one of the topics now being 10.01% of the document, one being 9.99%, the rest being 10%. But we have gone one stage closer to our ideal of 100% for one topic and 0% for the others.

In reality this perfect end result will never happen but if, after many thousands of iterations, we have minimised the spread of topics across documents then each bag of words in each topic will represent that topic. We just have to read the words and guess what that pic is.  







