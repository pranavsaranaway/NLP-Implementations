## 🔍 What is Semantic Search and How Do We Do It?

Semantic search is a modern approach to information retrieval that matches the **meaning** of a user’s query with relevant documents, rather than relying on exact keyword matches. It works by converting both the query and the documents into high-dimensional **embeddings** using a pretrained transformer model. These embeddings represent semantic meaning, allowing us to retrieve results that are contextually relevant, even if they don’t contain the same words.

### 🛠️ How It Works in This Implementation

1. **Dataset**: We start with a dataset of GitHub issues containing titles, bodies, and comments.
2. **Preprocessing**: We filter, clean, and flatten the data to isolate meaningful comments.
3. **Embedding**: We use a transformer model (`multi-qa-mpnet-base-dot-v1`) to generate embeddings for each text entry.
4. **Indexing**: We build a FAISS index using these embeddings for efficient nearest-neighbor search.
5. **Querying**: A user can enter a natural language question, which we also embed and compare against the index to retrieve semantically similar issues.

This approach enables flexible, intuitive searching across technical discussions—even when terminology or phrasing differs from the query.
