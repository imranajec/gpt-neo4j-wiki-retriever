# gpt-neo4j-wiki-retriever


This project creates a knowledge base for Sachin Tendulkar using Wikipedia data, Neo4j for graph databases, Langchain and OpenAI's GPT-3.5 Turbo for language understanding. The system can answer detailed questions about Sachin Tendulkar, maintaining context over a conversation.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Features](#features)
- [How It Works](#how-it-works)
- [Limitations](#limitations)
- [Contributing](#contributing)
- [License](#license)

## Installation

To set up the environment and run the project, follow these steps:

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/imranajec/gpt-neo4j-wiki-retriver.git
   cd gpt-neo4j-wiki-retriver
```

 
1. **Install Dependencies:** 

Make sure you have Python installed. Then, install the required packages:

```bash
pip install --upgrade langchain langchain-community langchain-openai langchain-experimental neo4j wikipedia tiktoken yfiles_jupyter_graphs
```
## Usage 
1. **Open the Jupyter Notebook:** 

Open `Sachin_Tendulkar_Knowledge_Base.ipynb` in Jupyter Notebook or Jupyter Lab. 
2. **Run the Notebook:** 

Execute the cells step-by-step to set up the environment, load data, preprocess it, initialize models, and run the knowledge base. 
3. **Query the Knowledge Base:** 

Use the provided `ChatSession` class to ask questions about Sachin Tendulkar and get accurate, context-aware responses.
## Features 
- **Entity Extraction:**  Uses GPT-3.5 Turbo to extract entities from user queries. 
- **Question Condensation:**  Rephrases follow-up questions to maintain context. 
- **Graph Database:**  Utilizes Neo4j for structured data storage and retrieval. 
- **Hybrid Search:**  Combines structured and unstructured data for comprehensive answers. 
- **Context Management:**  Maintains chat history to provide contextually accurate responses. 
- **Keyword Retrieval:**  Performs keyword-based search against the structured graph database. 
- **Full-Text Generation:**  Uses GPT-3.5 Turbo to generate comprehensive answers from unstructured data.
## How It Works 
1. **Data Loading:**  Loads Wikipedia data related to Sachin Tendulkar. 
2. **Data Preprocessing:**  Splits the data into manageable chunks using a text splitter. 
3. **Graph Transformation:**  Converts text data into graph format and loads it into Neo4j. 
4. **Keyword Retrieval:** 
- Uses a full-text index in Neo4j to perform keyword-based searches, retrieving relevant nodes and their relationships. 
- **Full-Text Index:**  A special type of index that allows for efficient searching of text within nodes and relationships in Neo4j. 
- **What is Gained:**  The full-text query identifies nodes in the graph database that contain the specified keywords. 
5. **Cypher Query:** 
- Utilizes the results of the full-text query to retrieve detailed information about the relationships between the identified nodes and other nodes in the graph. 
- **What is Gained:**  The Cypher query retrieves relationships between the nodes, such as connections like "Sachin Tendulkar -> played for -> Mumbai Indians", providing contextual information about the entities. 
6. **Vector Search on Documents:** 
- Uses vector embeddings to search through unstructured text data for relevant content. 
- **OpenAI Embeddings:**  Uses GPT-3.5 Turbo to convert text documents into vector embeddings. 
7. **Hybrid Search:**  Combines keyword retrieval from the graph database and vector search from document embeddings to provide comprehensive answers. 
8. **Question Handling:**  Uses GPT-3.5 Turbo to handle user queries and manage chat history. 
9. **Response Generation:**  Retrieves relevant information from the graph database and uses GPT-3.5 Turbo to generate accurate and comprehensive answers, combining both structured and unstructured data.
## Limitations 
- **Dependency on Wikipedia:**  The knowledge base is limited to the information available on Wikipedia. 
- **API Limits:**  Frequent use of OpenAI API can be costly and subject to rate limits. 
- **Performance:**  Response times may vary depending on the complexity of queries and data size.



## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
