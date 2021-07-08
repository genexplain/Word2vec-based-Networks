# Word2vec-based-Networks

We generated the following two word2vec embeddings: ‘Embedding_v1’ in which synonymous terms of genes, diseases, and drugs were substituted by their preferred terms from external biomedical databases, and  ‘Embedding_v2’ for which the same preprocessing strategies and the same training process were applied but without replacing synonyms.\
The two generated embeddings are available for download under the following links:\
[Embedding_v1](https://ebiomecon.genexplain.com/download/embedding_v1.bin)\
[Embedding_v2](https://ebiomecon.genexplain.com/download/embedding_v2.bin)


## Sample Code
A sample code to load the model, get the top n similar words, check if a word is in the output model vocabulary, and get a word vector.

## Read an embedding file 
### Prerequisites:
Install gensim to load the word2vec model.

```python 
from gensim.models import KeyedVectors
model = KeyedVectors.load_word2vec_format('embedding.bin', binary=True)
```

## Get the top n similar words ranked by cosine similarity values
```python
similar_words= model.most_similar(word, topn= n)
```

## Check if a word is in the vocabulary of the output model
```python 
if word in model.wv.vocab:
    print('True')
else:
    print('False')
```
    
## Get a word numerical vector of 300 dimensions
```python 
vector= model.wv[word]
```
