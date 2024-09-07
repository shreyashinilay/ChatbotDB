
## Equipment Retrieval System Using Sentence Embeddings and FAISS

### Overview
This project demonstrates how to efficiently search and retrieve equipment information from an Excel database using natural language queries. The system leverages **Sentence Transformers** to generate embeddings for each equipment entry and uses **FAISS** (Facebook AI Similarity Search) for fast vector-based retrieval. 

### Features
1. **Data Ingestion**: 
   - Reads equipment data from an Excel file (`equipments.xlsx`).
   - Each row of data is converted into text chunks.

2. **Embeddings Creation**: 
   - Embeddings for the text chunks are generated using the `SentenceTransformer` model (`all-MiniLM-L6-v2`).
   - Embeddings are stored as a NumPy array for efficient computation.

3. **Vector Indexing**: 
   - A FAISS index is created to perform fast similarity searches on the embeddings.
   - The index is saved in a binary format (`faiss_index.bin`) for later use.

4. **Metadata Storage**: 
   - Metadata, including the text chunks and their corresponding IDs, is stored in a pickle file (`metadata.pkl`).

5. **Query and Retrieval**:
   - A user-provided question (e.g., "List all equipment in Telemetry.") is embedded and searched within the FAISS index.
   - The top-k most relevant chunks are retrieved and displayed as the result.

6. **Response Generation (Optional)**:
   - Integration with Google's Gemini LLM (`gemini-1.5-pro-latest`) for generating a more detailed response based on the retrieved results.
   - The model can output responses in a Markdown format, making it easy to read and display.

### Dependencies
- `pandas`: For handling Excel data.
- `numpy`: For array manipulations and embedding storage.
- `sentence-transformers`: For generating embeddings of text data.
- `faiss`: For performing fast similarity searches.
- `pickle`: For saving and loading metadata.
- `google-generativeai`: For LLM integration and response generation.

### Setup and Usage
1. Install the required Python packages:
   ```bash
   pip install pandas numpy sentence-transformers faiss-cpu pickle google-generativeai
   ```
2. Ensure the `equipments.xlsx` file is in the correct format (with appropriate columns for equipment details).
3. Run the script to index and retrieve data based on user queries.
4. Optionally, integrate Google's LLM for generating detailed responses based on search results.

### Example Usage
- Load and preprocess equipment data from Excel.
- Generate embeddings and create a FAISS index.
- Query the system with a natural language question.
- Retrieve relevant equipment data and generate a detailed response.

---

This description provides an overview of the script's functionality, dependencies, and setup instructions for users looking to implement or extend the code.
