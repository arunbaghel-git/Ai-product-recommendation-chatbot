# AI Product Recommendation Chatbot (n8n)

An AI-powered product recommendation chatbot built using **n8n**, **OpenAI**, and **Gadget GraphQL**.

The workflow synchronizes Shopify products, indexes them in an in-memory vector store, and uses Retrieval-Augmented Generation (RAG) to provide context-aware product recommendations.

---

## Features

- AI-powered product recommendations
- Retrieval-Augmented Generation (RAG)
- In-memory vector search
- Shopify product synchronization
- Lead capture
- Conversation logging
- Multilingual support (English, Hindi, Hinglish)
- REST webhook APIs

---

## Technologies

- n8n
- OpenAI
- Gadget GraphQL
- Shopify
- JavaScript

---

## Workflow

1. Fetch product data from Shopify through Gadget GraphQL.
2. Clean and index product data into an in-memory vector store.
3. Generate embeddings using OpenAI.
4. Retrieve relevant products based on customer queries.
5. Save customer leads and chat conversations.

---

## Webhook Endpoints

| Endpoint | Purpose |
|----------|---------|
| `POST /chat` | AI chat |
| `POST /reload-data` | Reload product data into the vector store |
| `POST /capture-lead` | Save customer details |

---

## Requirements

- n8n
- OpenAI API Key
- Gadget backend
- Shopify store

---

---
## Configuration

Before running the workflow, create the following credentials in n8n:

### 1. OpenAI API

Create an **OpenAI** credential in n8n and add your OpenAI API key.

Used by:
- OpenAI Chat Model
- OpenAI Embeddings

### 2. HTTP Header Authentication

Create an **HTTP Header Auth** credential with the following header:

Header Name:
Authorization

Header Value:
Bearer YOUR_GADGET_API_KEY

This credential is used by the Gadget GraphQL HTTP Request nodes.

### 3. Update the GraphQL Endpoint

Replace the placeholder endpoint with your own Gadget GraphQL endpoint if necessary.

Example:

https://your-app.gadget.app/api/graphql

---

## Notes

- Product data is stored in an in-memory vector store.
- Conversations are logged through Gadget.
- Credentials and API keys are not included in this repository.