This project uses the LangChain library to create a chatbot clustered on a given PDF file (for example, “Attention is All You Need”). The project is designed to respond to user queries based on the PDF content.

Project Flow:

Data Preparation:

The PDF file is split into smaller chunks via the langchain.text_splitter library. The chunk_size = 1000 is set, which allows you to access information while preserving semantic integrity. This step allows us to work on smaller, manageable units instead of processing large blocks of text.

Creating Embeddings and Vector Database:

The split text chunks are converted into digital vectors via Google Generative AI Embeddings. This helps in capturing information and enabling similarity searches.

The resulting vectors are stored in ChromaDB from the langchain.vectorstores library. ChromaDB is used for efficient vector search and management.

Creating a Retriever:

A Retriever is created to generate relevant information content from ChromaDB. This retriever is used to find the content of the user queries and its content.

Masters and Prompt Engineering:

Gemini API is used as a large language model (LLM).

A prompt template is created to feed the user queries and the retrieved text content to the LLM. This template helps the LLM to generate content and informative answers.

Creating a Question-Answer Chain:

A question-answer chain is created using the RAG (Retrieval Augmented Generation) content. This chain combines the retriever, prompt template and LLM. The user query finds the relevant text content with the Retriever, the prompt template combines it with the query and the LLM generates a response based on this input.

Deployment with Streamlit:

The created chatbot is deployed using the Streamlit library and as a web application. This allows users to easily interact with the chatbot.

![rag_streamlit](https://github.com/user-attachments/assets/62f3638e-081f-4370-a3b6-093fd09fa28b)
