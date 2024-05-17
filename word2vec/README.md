### word2vec

word2vec is a method to represent how each word is related to other words.

It is a neural network that learns the relationships of words given a corpus. It is a method based on inference.

Let there be a sentence like below.


- you ? goodbye and I ay hello.

We want to predict the word that goes into the blank (? in this case).
The simplist way is to predict the blank only with the neighboriinnng words. "you" and "goodbye" in this case. These neighboring words are called as "context".


