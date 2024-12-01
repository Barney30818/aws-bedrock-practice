# Introduction

In this practice, I'll try to learn the basics of embeddings. I used [Amazon Titan Embeddings](https://aws.amazon.com/bedrock/titan/)  to help find the relative similarity of text content.

**Embeddings** capture the meaning of a piece of text in a series of numbers called a **vector**. We can then use these vectors to determine how similar pieces of text are to each other.

We can use a vector database to store these embeddings and perform fast similarity searches. Embeddings paired with a vector database are a core component of retrieval-augmented generation, a key pattern that we will learn more about in later labs.

In the practice below, we will compare the similarity of meaning between various pieces of text, including some translations.

------------

This code means:
- Compare embeddings and display lists to show how similar or different the various texts are.

  - A similarity value of 1 means exactly the same.
  - The smaller the similarity, the less similar are the embeddings.
```python
for e1 in items:
    print(f"Closest matches for '{e1.text}'")
    print ("----------------")
    cosine_comparisons = []
    
    for e2 in items:
        similarity_score = calculate_similarity(e1.embedding, e2.embedding)
        
        cosine_comparisons.append(ComparisonResult(e2.text, similarity_score)) #save the comparisons to a list
        
    cosine_comparisons.sort(key=lambda x: x.similarity, reverse=True) # list the closest matches first
    
    for c in cosine_comparisons:
        print("%.6f" % c.similarity, "\t", c.text)
    
    print()
```