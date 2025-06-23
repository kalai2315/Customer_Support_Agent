**Multilingual Customer Support Agent (LangChain + Gemini)**

This project implements a multilingual customer support agent using LangChain and Google Gemini. The agent can automatically detect the customer's language, translate their message to English, generate a resolution response, and then translate the response back to the customer's original language.

**Overview**

The system consists of four sequential processing steps:

**Language Detection**

Detect the language of the original customer message.

**Translation to English**

Translate the customer's message into English, if it's not already in English.

**Resolution Generation**

Generate a support response in English based on the translated message.

**Translation to Customer's Language**

Translate the English response back to the original customer language, if needed.

**Chain Architecture**

Each step is implemented as a LangChain component using prompt templates, the Gemini model, and a string parser. The chains are executed in a sequential pipeline.


Input: orig_message

       ↓
       
[Chain 1] → orig_language

       ↓
       
[Chain 2] → tran_message

       ↓
       
[Chain 3] → tran_response

       ↓
       
[Chain 4] → final_response

**Setup Instructions**

1. Install Required Packages

   pip install langchain langchain-google-genai google-generativeai
   
3. Configure API Key

   import os
   
   from getpass import getpass

   os.environ["GOOGLE_API_KEY"] = getpass("Enter your Google API Key: ")

**Model Initialization**

from langchain_google_genai import ChatGoogleGenerativeAI

llm = ChatGoogleGenerativeAI(model="gemini-pro", temperature=0.3)

**Technologies Used**

Python 3.8+

LangChain

Google Gemini (Generative AI)
