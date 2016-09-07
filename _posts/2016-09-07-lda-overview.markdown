---
layout: post
title: "LDA Overview"
date: 2016-09-07 21:37:00 +0100
categories: lda nlp
---

At [resolver](resolver.co.uk) we need some form of topic discovery from our large corpus of email conversations. Having done some reading and met with [some of the team at Graphaware](http://graphaware.com) it would seem that [Latent Dirichlet allocation](https://en.wikipedia.org/wiki/Latent_Dirichlet_allocation) is an option, I'm going to call it LDA for now.

I'm not going to try and understand LDA in its full scientific or mathematical detail but I'd like to know a little bit about how it works so I can help get the best out of it even while wearing my CTO hat with built-in dark glasses, ear muffs and blinkers for use in emergency. 

I learn by writing things down so let's see where this goes:

## We Know

We have 1000 documents.

## We Assume

To keep things simple we'll make some very simple assumptions:

1. We have 10 topics in these 1000 documents.   
1. Each topic is made up of a bag of words. No two topics have the same word e.g:

    1. If one of the unknown topics was topics was, say, **'Dirty'** we would expect the words in the bag to be 'dirty', 'stained', 'yellowing', 'filthy', 'marked'.
    1. Another topic my be **'Rude'** and would have the words 'rude', 'unhelpful', 'unpleasant', 'aggressive'.

1. Let's make a really big assumption just to make this example as clear as possible - we'd never do this in a real life example. Let's assume these topics are evenly distributed and each document only has 1 topic. In other words, in our 1000 documents there are 10 topics, each topic having 100 documents.

## Getting Started

So we believe that there are 10 topics and each document has only one topic. So for any given document the distribution of topics in that document is:

**100% 0% 0% 0% 0% 0% 0% 0% 0% 0%**

Remember we have no idea what these topics are and what the belonging to these topics are so lets guess by going through the corpus and assigning each word randomly to our mystery 10 topics.

If we then examine each of the words in each document and use the word to assign topics to that document then this random distribution should give us something like:

**10% 10% 10% 10% 10% 10% 10% 10% 10% 10%**

So instead of each topic having 100 documents it has 1000 documents. Instead of each document having 1 topic it has all 10 topics.

## Iterating to the answer

Now we move one of the words into another topic, again at random. We repeat the assignment of topics to each document.

if the random move was a poor one then the distribution of topics stays equally poor. If the move was a good one and the word has increased the number of words with similar meanings in the new topic then we may go from our totally random 10 topics at 10% in each document to, say, one of the topics now being 10.01% of the document, one being 9.99%, the rest being 10%. We have gone one stage closer to our ideal of 100% for one topic and 0% for the others. Repeat this enough times and we'll start to converge on the actual result.

In reality this perfect end result will never happen. For a start, most real documents will have more than one topic and topics won't always be the same size but after many thousands of iterations we would have minimised the distribution of topics across documents so each bag of words in each topic will, mostly, represent that topic. We just have to read the words and guess what that topic is.  







