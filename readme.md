The submission code file, *hybrid-search.ipynb*, implements a document retrieval system using a hybrid search approach. Although we achieved strong performance, the execution time significantly exceeded the 10-minute limit. Consequently, we retained only the BM25-based retrieval code (as the final executable code) and commented out the rest.

The *no chunk codes* directory contains all the code files that do not employ a chunking strategy. In these files, we encode the documents as a whole and perform retrieval using cosine similarity as the baseline approach.

The *chunk codes* directory includes code files that implement a chunking strategy, with the following components:
- **Truncate**: The corpus.json file is split into smaller chunks to facilitate efficient processing.
- **Embedding**: The chunked documents are encoded using various methods.
- **Retrieval**: Documents are retrieved using multiple methods, generating a submission file.

Due to memory constraints, some code sections save intermediate results as files, adding overhead from file input/output operations. For instance, during similarity computations, we often divide the 2000 queries into 20 groups. Each group undergoes separate similarity calculations, and the results are subsequently merged to create the final output.
