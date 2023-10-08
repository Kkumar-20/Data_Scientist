# What are Word Embeddings?
- It is an approach for representing words and documents. Word Embedding or Word Vector is a numeric vector input that represents a word in a lower-dimensional space. It allows words with similar meanings to have a similar representation. They can also approximate meaning. A word vector with 50 values can represent 50 unique features.

Features: Anything that relates words to one another. E.g.: Age, Sports, Fitness, Employed, etc. Each word vector has values corresponding to these features.

# Two different approaches to get Word Embeddings:

1) Word2Vec:
In Word2Vec every word is assigned a vector. We start with either a random vector or one-hot vector.

One-Hot vector: A representation where only one bit in a vector is 1.If there are 500 words in the corpus then the vector length will be 500. After assigning vectors to each word we take a window size and iterate through the entire corpus. While we do this there are two neural embedding methods which are used:

1.1) Continuous Bag of Words(CBOW)
In this model what we do is we try to fit the neighboring words in the window to the central word.



1.2) Skip Gram
In this model, we try to make the central word closer to the neighboring words. It is the complete opposite of the CBOW model. It is shown that this method produces more meaningful embeddings.
