# Policy-Document-RAG-System--Finance-Bill
This RAG System allows users to ask questions and retrieve the most relevant sections from a pdf like that of the finance bill.

## IMPLEMENTATION OVERVIEW 

### Key Features

  1.	PDF Text Extraction
	•	Converts PDFs into plain text using PyPDF.
	•	Necessary because PDFs are designed for human readability, not machine processing.

  2.	Text Chunking
	•	Splits documents into ~800-word chunks.
	•	Purpose: Embedding models perform better on focused sections.
	•	Overlap: Preserves context across chunk boundaries (not used here but recommended).

  3.	Embedding Generation
	•	Uses BAAI/bge-small-en-v1.5 to convert chunks into semantic vectors.
	•	Embeddings capture meaning, enabling semantic search that understands intent beyond keywords.

  4.	ChromaDB Storage
	•	Stores embeddings, chunk text, and metadata in a persistent collection.
	•	Metadata ensures traceability and allows filtering.
	•	Persistence avoids recomputation for each query, improving efficiency.

  5.	Querying & Retrieval
	•	User queries are embedded and compared to chunk embeddings using cosine similarity.
	•	Returns top-N relevant chunks with similarity scores.
	•	Lower cosine distance indicates higher semantic relevance.
	•	Example query: “What does the Finance Bill say about taxes?”

⸻
### Why It Works

  •	Chunking: Focused sections improve embedding precision.
	•	Embeddings: Capture semantic meaning for context-aware search.
	•	Metadata: Tracks sources and supports reliable filtering.
	•	Persistent storage: Makes retrieval fast and production-ready.
	•	Similarity score: Quantifies relevance; lower cosine distance = better match.

⸻
### Quick Workflow

  1.	Extract text from PDFs.
	2.	Chunk text into manageable sections.
	3.	Generate embeddings for each chunk.
	4.	Store chunks, embeddings, and metadata in ChromaDB.
	5.	Query the system and retrieve the top relevant sections.

⸻
### Use Cases

  •	Extract taxation sections from Finance Bills.
	•	Search the Constitution for rights and limitations.
	•	Query Parliamentary Acts for regulatory clauses.
	•	Knowledge management for organizations with large policy archives.

⸻

### Key Advantages

  •	Efficient retrieval: Chunking + embeddings ensures precise semantic search.
	•	Persistent and traceable: Metadata and ChromaDB storage make the system production-ready.
	•	Flexible: Works with any policy or legal PDF document.

⸻

### Project Setup

  1.	Install required libraries: pip install sentence-transformers groq numpy python-dotenv chromadb pypdf
  2.	Place your PDFs in the project directory.
	3.	Run the extraction, chunking, embedding, and storage scripts.
	4.	Query the system to retrieve instant, relevant results.

⸻
### Conclusion

This project demonstrates how structured embeddings and semantic search can transform static legal documents into a searchable, intelligent knowledge base, making policy research faster, more accurate, and production ready.
























