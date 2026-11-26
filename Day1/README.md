Sweet Crumbs Home Bakery AI Assistant

About the Project

This project is a simple AI chatbot developed for Sweet Crumbs Home Bakery. It answers customer questions related to bakery orders, cake availability and basic bakery information. The chatbot uses a Large Language Model (LLM) through Groq and LangChain.

Objective

The main objective of this project is to create a chatbot that provides helpful and polite responses to bakery customers while following the given business rules.

Technologies Used

Python

LangChain

Groq API

Google Colab

GPT-OSS 120B

Llama Prompt Guard
Implementation

1. Installing and Importing Libraries

First, the required LangChain Groq library is installed and imported. It is used to connect the notebook with Groq models.

2. API Key Setup

The Groq API key is accessed using Google Colab Secrets. This helps to keep the API key secure instead of directly writing it in the code.

3. Initializing the LLM

The ChatGroq model is initialized using the openai/gpt-oss-120b model. Temperature is set to 0 to make the responses more consistent.

4. Creating the System Prompt

A system prompt is created to define the chatbot's role and behavior. It includes the following rules:

It acts as an assistant for Sweet Crumbs Home Bakery.

Cakes are prepared based on customer orders.

Orders require at least 24 hours' notice.

Eggless cakes are available.

It should not promise delivery times.

It should give polite and short answers within 60 words.

5. Creating the Chatbot Function

A function named ask() is created. It takes the customer's question, sends it to the LLM along with the system instructions and returns the generated answer.

6. Testing the Chatbot

The chatbot is tested with a question asking whether an order can be received tomorrow. It responds by explaining the 24-hour notice requirement and avoids promising a specific delivery time.

7. Prompt Guard Testing

The Groq client is used to call the Llama Prompt Guard model. A sample prompt containing an instruction to ignore previous instructions is given to the model, and it returns a safety score.

How to Run

Open the notebook in Google Colab.

Install the required library.

Add your Groq API key in Colab Secrets with the name GROQ_API_KEY.

Run all the notebook cells.

Use the ask() function to ask questions to the chatbot.

Example:

print(ask("Can I get my order tomorrow?"))

Output

The chatbot gives a polite response explaining that cakes are made to order, orders require 24 hours' notice, and delivery times cannot be guaranteed.

The Prompt Guard model also returns a score for the sample prompt.

Conclusion

This project demonstrates how an LLM can be used to create a simple chatbot for answering customer queries. It also demonstrates the use of Prompt Guard for checking prompts for potential safety issues. The project can be further improved by adding more FAQs and integrating prompt safety checking into the chatbot itself.
