# Book Recommender

## Types of recommendation systems:

- Collaborative filtering model:

  - Based on feedbacks:
       - explicit feedback(ratings, thumbup/thumdown)
       - implicit feedback(book in shopping cart, numbner of episode watched in a TV show)
  - User-user similarities (people like you, also like "The Hobbit")
  - Item-item similarities (if you like "The Hobbit", you will also "The Lord of Rings")
  - User-item similarities : combined both approaches above and use matrix facotrization -> Best trained with Singular Value decomposition (SVD)

- Content-based model:

  - Similarities are calculated based on content based features (like the genre, duration of the movie)

- Hybrid recommender model:

  - Combined collaborative filtering with content-based
  - Because Hybrid Deep Learning algorithms are non-linear, they are less prone to over-simplify a user’s tastes. They allow us to learn much finer         interactions between users and items.
  - Deep learning models can reveal more complex tastes over cross-domain data (predict a user's taste on music, movies and even dishes!?)

## In this project:

### Clean data: 
  - book data
  - user data
  - rating data
  
### Data analysis - extract insights 
  - explict rating (non-0s) vs. implicit rating (0s)
  - calculate sparsity of the matrix 
  
### Create user-item matrix
  - fillna
  - transpose the matrix
  
### Build recommender
- Collaborative filter: KNN approach
    - Item-based recommender (CF)- find similiar books and recommend to users
    - Use KNN to find k most similar books
    - Default params:
      - metric = 'cosine'
      - algorithm = 'brute'
      - k = 5
- Content based model using Natural Language Process (NLP)
  - content here is the book title
  - NLP steps:
    - remove NonAscii, make words lower cases, remove stop words, punctuations and html links in the title
    - convert book title in to vectors by TfidfVectorizer (bigram)
    - use consine similarity for similarity measurement
    - score the book titles based on similarities and get top k most similar book titles by the given book title.
    
    
