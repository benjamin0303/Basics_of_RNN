## word2vec

word2vec is a method to represent how each word is related to other words.

It is a neural network that learns the relationships of words given a corpus. It is a method based on inference.

Let there be a sentence like below.


- you ? goodbye and I say hello.

We want to predict the word that goes into the blank: ?.

The simplist way is to predict the blank only with the neighboring words. 
"you" and "goodbye" in this case. These neighboring words are called as "context".


### CBOW (Continuous Bag Of Words)

Continuous bag of words is a neural network model under wond2vec. It takes one-hot encoded corpus as an input and has a hidden layer, produces one-hot encoded vector as an output.

<!-- ![CBOW diagram](images/CBOW.png) This is how to make comment in HTML -->
<img src="images/CBOW.png" alt="CBOW diagram" width="500"/>

This diagram shows the structure of CBOW. Here, we put 4 neighboring words to predict the blank. 2 before, and 2 afterwards. Each $w_{n-2}$ to $w_{n+2}$ are one-hot encoded vector for the word they represent. Also, the predicted output $w_{n}$ is the one-hot encoded vector.

Say the corpus has 100 distinct words. Then all $w_{n-2}$ to $w_{n+2}$ are 100-length vectors. They get multiplied with the weight_in matrix and become the hidden layer (length h). Therefore, the weight_in matrix has a shape of (100, h).
$w_{n-2}$ to $w_{n+2}$ share this Weight_in matrix.
