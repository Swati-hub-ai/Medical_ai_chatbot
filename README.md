
# **Interactive Medical Chatbot**

This is an interactive chatbot built using **LangChain** and **Llama3:latest**. It answers questions related to medical topics by leveraging a large language model (LLM) that retrieves relevant information from a locally stored **FAISS** index. The app is designed using **Streamlit** to provide a user-friendly interface for interaction.
![image](https://github.com/user-attachments/assets/c65dcd62-628c-43a4-bf46-b84cd8fee90b)


## **Table of Contents**
1. [Introduction](#introduction)
2. [Requirements](#requirements)
3. [Setup and Installation](#setup-and-installation)
4. [How to Use](#how-to-use)
5. [Customization](#customization)
6. [FAQs](#faqs)
7. [Troubleshooting](#troubleshooting)

---

## **Introduction**
This project provides an interactive chatbot that answers medical questions based on context retrieved from documents stored in a **FAISS** index. The chatbot uses **Llama3:latest** model running locally and is built using **LangChain** for data retrieval and **Streamlit** for the web interface.

---

## **Requirements**

### **Software Requirements:**
- Python 3.8 or higher
- **Streamlit**: For the user interface.
- **LangChain**: For creating the retrieval-based QA system.
- **FAISS**: For efficient document retrieval.
- **Mistral-7B-Instruct Model**: For answering medical questions.
- **Hugging Face Model (Optional)**: If you're using HuggingFace-based models.

### **Libraries:**
Make sure to install the required Python libraries by running:
```bash
pip install -r requirements.txt
```

Contents of `requirements.txt`:
```
streamlit
langchain
faiss-cpu
torch
requests
langchain_huggingface
langchain_community
```

---

## **Setup and Installation**

### 1. **Clone the Repository**

Start by cloning this repository to your local machine:

```bash
git clone https://github.com/your-username/interactive-chatbot.git
cd interactive-chatbot
```

### 2. **Install Python Dependencies**

Create a virtual environment (recommended) and install the dependencies:

```bash
python -m venv venv
source venv/bin/activate  # For macOS/Linux
venv\Scripts\activate  # For Windows
pip install -r requirements.txt
```

### 3. **Download Llama3:latest Model**

If you haven't already, **pull the Llama3:latest model** for local use with Ollama:

```bash
ollama pull mistral
```

Alternatively, you can use other **HuggingFace models** if you prefer. Make sure you update the model name in the code accordingly.

### 4. **Set up FAISS Index**
Make sure your FAISS vector store is available. You can create one using the document corpus you want the chatbot to use.

```bash
python create_faiss_index.py
```

---

## **How to Use**

### 1. **Run the App**

To run the chatbot locally, execute the following command:

```bash
streamlit run chatbot.py
```

This will start a Streamlit server and open the chatbot in your browser.

### 2. **Interact with the Chatbot**

- You will be presented with a friendly interface where you can ask medical questions.
- The chatbot will process your query, retrieve relevant context from the FAISS index, and answer the question using the Mistral-7B-Instruct model.

### 3. **Multiple Questions and Conversation**

You can ask multiple questions in the same session. The chat history will be stored, allowing the assistant to remember previous exchanges during the conversation.

---

## **Customization**

### 1. **Change the Model**

To use a different model (like a HuggingFace model or a different version of the Mistral model), update the `load_llm()` function in `chatbot.py`.

```python
def load_llm(model_name="Llama3:latest"):
    return OllamaLLM(model=model_name)  # Change model name here
```

### 2. **Adjust the Prompt Template**

You can modify the chatbot's behavior by updating the `CUSTOM_PROMPT_TEMPLATE` in the code.

```python
CUSTOM_PROMPT_TEMPLATE = """
Use the pieces of information provided in the context to answer the user's question.
If you don't know the answer, say that you don't know. Don't try to make up an answer. 
Don't provide anything out of the given context.

Context: {context}
Question: {question}

Start the answer directly. No small talk, please.
"""
```

Feel free to modify it to tailor the response to your specific use case.

### 3. **Change FAISS Index Path**

If your FAISS index is located in a different directory, update the `DB_FAISS_PATH`:

```python
DB_FAISS_PATH = "path/to/your/faiss/index"
```

---

## **FAQs**

### **1. Why does the model not respond to certain queries?**

- The model relies on the context provided by the FAISS index. If the query is too specific or not found in the index, the model might respond with "I don't know".
- Ensure the FAISS index contains relevant documents to answer the questions.

### **2. How can I improve the accuracy of the responses?**

- Fine-tune the model on domain-specific data if possible.
- Add more diverse documents to the FAISS index.

---

## **Troubleshooting**

### **1. "Model Not Found" Error**
Ensure the Llama 3 or Mistral model is installed locally. You can check the models available by running:

```bash
ollama list
```

If the model is missing, pull it again with:

```bash
ollama pull mistral
```

### **2. FAISS Index Loading Issues**
If the FAISS index is not loading correctly, verify that the index is properly built and the path is correct.

```bash
python create_faiss_index.py
```

### **3. Streamlit Errors**
If Streamlit is not displaying properly, try restarting the app:

```bash
streamlit run chatbot.py
```

If the problem persists, check the error messages in the console for more details.

---

## **License**
This project is licensed under the MIT License. See the LICENSE file for details.

---

Feel free to make changes and extend the functionality as needed. Let me know if you need further help! 😊

