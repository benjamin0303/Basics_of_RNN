## word2vec

word2vec is a method to represent how each word is related to other words.

It is a neural network that learns the relationships of words given a corpus. It is a method based on inference.

Let there be a sentence like below.


- you ? goodbye and I say hello.

We want to predict the word that goes into the blank: ?

The simplist way is to predict the blank only with the neighboring words. 
"you" and "goodbye" in this case. These neighboring words are called as "context".


### CBOW (Continuous Bag Of Words)

Continuous Bag of Words (CBOW) is a neural network model under the word2vec framework. It takes a one-hot encoded corpus as input, has a hidden layer, and produces a one-hot encoded vector as output.

<img src="images/CBOW.png" alt="CBOW diagram" width="500"/>

The diagram above illustrates the structure of the CBOW model. In this model, we use four neighboring words to predict the target word: two preceding and two following words. Each of the words $w_{n-2}$ to $w_{n+2}$ is represented as a one-hot encoded vector. The predicted output $w_{n}$ is also a one-hot encoded vector.

Assuming the corpus contains 100 distinct words, each vector $w_{n-2}$ to $w_{n+2}$ will be a 100-dimensional vector. These vectors are multiplied by the weight_in matrix, resulting in the hidden layer vectors. Consequently, the weight_in matrix has a shape of (100, h). All input vectors $w_{n-2}$ to $w_{n+2}$ share this weight_in matrix.

By multiplying the four input vectors with the weight_in matrix, we obtain four h-dimensional vectors. These vectors are then summed (or averaged) to form a single h-dimensional vector. This vector is subsequently multiplied by the weight_out matrix, producing a 100-dimensional vector that represents the target word $w_{n}$. Therefore, the weight_out matrix has a shape of (h, 100).

