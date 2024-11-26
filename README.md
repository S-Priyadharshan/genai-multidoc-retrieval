## Design and Implementation of a Multidocument Retrieval Agent Using LlamaIndex
Developed By: Priyadharshan S
Register Number: 212223240127
### AIM:
To design and implement a multidocument retrieval agent using LlamaIndex to extract and synthesize information from multiple research articles, and to evaluate its performance by testing it with diverse queries, analyzing its ability to deliver concise, relevant, and accurate responses.

### PROBLEM STATEMENT:
The rapid growth of research articles across various domains, especially in scientific and academic fields, has made it increasingly difficult to extract relevant information from a single document. With multiple research papers available on similar topics, the need for an efficient system that can synthesize and retrieve concise, accurate, and relevant information from multiple documents has become essential. Existing search and retrieval systems often provide a wealth of information but fail to extract the most pertinent details from multiple sources in a coherent manner.

### DESIGN STEPS:

#### STEP 1:
Install LlamaIndex: First, ensure that LlamaIndex (formerly GPT Index) is installed in your Python environment.

#### STEP 2:
Load Multiple Documents: Load a set of research articles (text files, PDFs, or any other documents) into the system.

#### STEP 3:
Indexing: Use LlamaIndex to create an index that can be queried for information extraction.

### PROGRAM:

```python
from llama_index import GPTSimpleVectorIndex, Document
from langchain.llms import OpenAI

def load_documents(file_paths):
    documents = []
    for file_path in file_paths:
        with open(file_path, 'r') as file:
            documents.append(Document(text=file.read()))
    return documents

def create_index(documents):
    index = GPTSimpleVectorIndex(documents)
    return index

def query_agent(index, query):
    response = index.query(query)
    return response

file_paths = ['article1.txt', 'article2.txt', 'article3.txt']
documents = load_documents(file_paths)
index = create_index(documents)

query = "What are the key findings in the research?"
response = query_agent(index, query)
print(response)

```

### OUTPUT:
![image](https://github.com/user-attachments/assets/ab3d0bbc-9f22-4104-82f7-3ee0c8f8d935)

### RESULT:
The program successfully implements a multidocument retrieval agent. It loads multiple research articles, creates an index using LlamaIndex, and allows for querying. The system synthesizes information from multiple sources and provides relevant and precise responses.
