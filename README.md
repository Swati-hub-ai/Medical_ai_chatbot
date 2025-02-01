# **Interactive Medical Chatbot**

This is an interactive chatbot built using **LangChain** and **Llama3:latest**. It answers questions related to medical topics by leveraging a large language model (LLM) that retrieves relevant information from a locally stored **FAISS** index. The app is designed using **Streamlit** to provide a user-friendly interface for interaction.

Welcome to the **Interactive Medical Chatbot** powered by **LangChain** and the **Llama3:latest model**. This chatbot helps answer medical questions by retrieving relevant information from the **FAISS index**.

![image](https://github.com/user-attachments/assets/4002df95-881e-4322-bfd6-57833e864858)


## Features
- **Conversational UI**: Ask medical questions and receive intelligent responses.
- **Medical Context**: Utilizes a knowledge base for accurate information.
- **Offline**: Runs completely offline with locally installed models.

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
This project provides an interactive chatbot that answers medical questions based on context retrieved from documents stored in a **FAISS** index. The chatbot uses **Mistral-7B-Instruct** model running locally and is built using **LangChain** for data retrieval and **Streamlit** for the web interface.

---

## **Requirements**

### **Software Requirements:**
- Python 3.8 or higher
- **Streamlit**: For the user interface.
- **LangChain**: For creating the retrieval-based QA system.
- **FAISS**: For efficient document retrieval.
- **Llama3:latest Model**: For answering medical questions.
- **Hugging Face Model (Optional)**: If you're using HuggingFace-based models.

### **Libraries:**
Make sure to install the required Python libraries by running:
```bash
pip install -r requirements.txt
