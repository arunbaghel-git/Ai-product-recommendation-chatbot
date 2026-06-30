# AI Product Recommendation Chatbot

An AI-powered product recommendation chatbot for Shopify built using **n8n**, **OpenAI**, **Gadget**, and a custom **chat widget**.

The system synchronizes product data, indexes it into an in-memory vector store, and uses Retrieval-Augmented Generation (RAG) to provide context-aware product recommendations. Customer leads and conversations are stored in Gadget and can be viewed through the Gadget application.

# note: It can be embedded in any website Shopify, WordPress, React apps, or plain HTML pages. i used it for shopify store
---

## Features

- AI-powered product recommendations
- Retrieval-Augmented Generation (RAG)
- Semantic vector search
- product synchronization
- Customer lead capture
- Conversation history logging
- Multilingual support (English, Hindi, Hinglish)
- Custom chat widget
- Modular architecture

---

## Tech Stack

| Component | Technology |
|-----------|------------|
| Storefront | Shopify or Any Other|
| AI Workflow | n8n |
| AI Models | OpenAI |
| Backend | Gadget |
| APIs | GraphQL & REST |
| Frontend | Liquid, HTML, CSS, JavaScript |
| Containerization | Docker |

---

## Repository Structure

```text
AI-powered-product-recommendation-chatbot/
│
├── docker/                 # Docker configuration
├── docs/                   # Project documentation
│   └── architecture.md
├── n8n/                    # n8n workflow
│   ├── chatbot-ai-agent.json
│   └── README.md
├── screenshots/            # Project screenshots
├── chat-widget/    # Chat widget
│   ├── chatbot-widget.html // user any extention according to usecase
│   └── README.md
├── .gitignore
├── .env.example
└── README.md
```

> **Note:** The Gadget backend is hosted on the Gadget platform and is not included in this repository. It provides GraphQL APIs, stores customer leads, and maintains conversation history.

---

## Project Components

### n8n

- Product synchronization
- AI workflow orchestration
- OpenAI integration
- Vector search
- Chat processing

### Chat Widget

- Floating chat interface
- Lead capture
- Product recommendation cards
- Customer interaction

### Docker

Provides a simple local environment for running n8n.

### Documentation

Contains architecture and project documentation.

---

## System Architecture

See the detailed architecture documentation:

**docs/architecture.md**

---

## Getting Started

1. Clone this repository.
2. Start the Docker environment.
3. Import the n8n workflow.
4. Configure the required credentials.
5. Install the chat widget.
6. Connect your Gadget backend.

Refer to the README files inside each component for detailed setup instructions.

---

## Screenshots

Project screenshots can be found in the `screenshots/` directory.

---

## Security

This repository does **not** include:

- API Keys
- Access Tokens
- Credentials
- Environment Secrets

Use your own credentials when configuring the project.

---

## License

This project is provided for learning and portfolio purposes.
