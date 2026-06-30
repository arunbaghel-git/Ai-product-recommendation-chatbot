# System Architecture

## Overview

This project is an AI-powered Shopify product recommendation system built using **Shopify**, **n8n**, **OpenAI**, **Gadget GraphQL**, and a custom **Shopify chat widget**.

The chatbot synchronizes product data from Shopify, indexes it into an in-memory vector store, and uses Retrieval-Augmented Generation (RAG) to provide context-aware product recommendations based on customer queries.

---

# High-Level Architecture

```text
                           Shopify Store
                                 │
                                 ▼
                    Gadget App (Installed)
                                 │
          ┌──────────────────────┼──────────────────────┐
          │                      │                      │
          ▼                      ▼                      ▼
  Product Synchronization   Customer Leads      Chat Conversations
          │                      │                      │
          └──────────────────────┼──────────────────────┘
                                 │
                          Gadget GraphQL API
                                 │
                                 ▼
                         n8n AI Workflow
                                 │
          ┌──────────────────────┼──────────────────────┐
          │                      │                      │
          ▼                      ▼                      ▼
 Product Processing     OpenAI Embeddings      Vector Store
                                 │
                                 ▼
                           AI Agent (RAG)
                                 │
                                 ▼
                     Shopify Chat Widget
                                 │
                                 ▼
                             Customer
```

---

# System Components

## Shopify Store

The Shopify store serves as the customer-facing storefront where users interact with the chatbot.

Responsibilities include:

* Displaying products
* Hosting the chat widget
* Collecting customer messages
* Collecting customer lead information

---

## Gadget Application

The Gadget application acts as the backend for the chatbot.

Responsibilities include:

* Synchronizing Shopify product data
* Providing GraphQL APIs
* Storing customer leads
* Logging chat conversations

Since the Gadget app is installed on the Shopify store, merchants can directly view customer leads and conversation history from the Gadget application's admin interface without accessing the underlying database.

---

## n8n Workflow

n8n orchestrates the AI workflow.

Responsibilities include:

* Fetching product data
* Cleaning and transforming product information
* Generating embeddings
* Populating the vector store
* Handling AI chat requests
* Logging conversations
* Processing lead submissions

---

## OpenAI

OpenAI powers the AI capabilities of the chatbot.

Used for:

* Text embeddings
* Semantic search
* Natural language understanding
* Response generation

---

## In-Memory Vector Store

The vector database stores embedded product information for semantic retrieval.

Indexed product fields include:

* Product Title
* Product Subtitle
* Problems
* Zodiac Sign
* Price
* Availability
* Product URL
* Image URL

---

## Shopify Chat Widget

A custom Shopify widget provides the customer interface.

Features include:

* Lead capture
* AI chat
* Product recommendation cards
* Session management
* Responsive design

---

# Workflow

## Product Synchronization

1. The reload webhook is triggered.
2. n8n requests product data from Gadget GraphQL.
3. Product information is cleaned and transformed.
4. OpenAI generates vector embeddings.
5. Product documents are indexed into the vector store.

---

## Customer Conversation

1. Customer opens the Shopify chat widget.
2. Customer submits lead information.
3. Lead details are saved through Gadget.
4. Customer sends a message.
5. The AI Agent receives the request.
6. Relevant products are retrieved from the vector store.
7. OpenAI generates the response using RAG.
8. Chat conversation is stored in Gadget.
9. Product recommendations are returned to the chat widget.

---

# Merchant Experience

Store administrators can access the Gadget application directly from their Shopify store to:

* View captured customer leads
* View chat conversation history
* Monitor chatbot interactions
* Access synchronized product data

No direct database access is required, as all information is available through the Gadget application's interface.

---

# Design Principles

The architecture is designed around the following principles:

* Retrieval-Augmented Generation (RAG)
* Semantic vector search
* API-first architecture
* Modular workflow design
* Separation of frontend and backend
* Reusable components
* Low-code automation with n8n

---

# Technology Stack

| Component           | Technology                    |
| ------------------- | ----------------------------- |
| Storefront          | Shopify                       |
| Backend             | Gadget                        |
| Workflow Automation | n8n                           |
| AI Model            | OpenAI                        |
| Vector Storage      | n8n In-Memory Vector Store    |
| Communication       | GraphQL & REST APIs           |
| Frontend            | Liquid, HTML, CSS, JavaScript |

---

# Benefits

* AI-powered product recommendations
* Fast semantic product search
* Modular architecture
* Easy Shopify integration
* Low-code workflow automation
* Centralized customer lead management
* Conversation history available from the Gadget application
* Easily extensible for future AI capabilities
