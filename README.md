# Information Retrievel Model 
Vector space model works based on the idea of similarity. If a particular document is more similar to the query than the other document then first document is considered more relavant to the query. 
Ranking function is defined as the similarity between the query and the document and documents are ranked. 

How to instantiate a vector space model. We need to do three things:
1. define the dimensions (the concept of what a document is);
2. decide how to place documents and queries as vectors in the vector space; and
3. define the similarity between two vectors.

Model represent each document and query by a term vector. Document and Query vectors consists of a number of elements corresponding to the weights of different terms. How to define term weights? Term weights define the importance of each word. Also how to define similarity measure?
If we have |V| terms in our vocabulary, we define a |V |-dimensional space, as eeach word in our vocabulary defines a dimension, thus giving |V | dimensions.

Consider multiple occurrences of a term in a document as opposed to binary representation; I have considered the TF instead of just the absence or presence.
TF (w, d) = count(w, d).
How to distinguish insignificant word from significcant words cause using TF approach would give more importance to Stop Words which are usually more frequent. We can use the global statistics of terms. 

## Inverse document frequency (IDF) 
The document frequency is the count of documents that contain a particular term. Then Inverse the document frequency because we want to reward a word that doesnot occur in many documents. We modify the frequency count by multiplying it by the IDF of the corresponding word. Penalize common words which generally have a low IDF and reward informative words that have a higher IDF.

<img width="240" alt="Screenshot 2024-03-24 at 11 19 06 PM" src="https://github.com/Goat8/vector_space_model/assets/8699044/25c3986d-cd9b-4646-83f6-2a7f228bba04">

M is number of documents
df(w) the total number of documents containing w

To give less score to less informative word take log IDF. 

