# ChatBot.com API Documentation

This is the **un-official** developer documentation of **ChatBot.com API** by **Athar Kharal, PhD**. It enables you to build, manage, and integrate intelligent chatbot systems. The API provides access to core features including stories, entities, conversations, and user management.

---

## Base URL

All API requests must target the following base URL:

```
https://api.chatbot.com/
```

---

## Quick Start

New here? Follow the 3-step quick start:

1. **[Install and Setup](getting-started/authentication.md)**  
   Learn how to get API keys and authenticate your requests.

2. **Make Your First Call**  
   Use the `POST /entities/query` endpoint to fetch structured data.

3. **Inspect the Response**  
   Understand the JSON structure returned and how to handle it.

→ Read the [Getting Started Guide](getting-started/authentication.md) for a full walkthrough.

---

## Core Concepts

Before diving into the full API reference, get familiar with:

- **[Archives](api/archives.md):** Retrieve past conversation logs using timestamp filters.
- **[Entities](api/entities.md):** Query or update structured elements like intents, slots, or tags.
- **OpenAPI Spec:** The machine-readable contract for all endpoints.

→ See the [API section](#api) and [Reference](#reference) for details.

---

## Capabilities

The API allows you to:

- Automate creation and deployment of chatbot logic.
- Retrieve and analyze chat transcripts.
- Manage user-defined entities.
- Integrate chatbot workflows into external applications.
- Monitor system behavior and diagnose integration issues.

---

## Documentation Structure

The documentation is divided into the following sections:

- **Getting Started** — Authentication model, token acquisition, and initial setup.
- **API** — Endpoint definitions, request syntax, and response schemas.
- **Reference** — OpenAPI specification, status codes, and downloadable tools.
- **Changelog** — Version history and notable changes.

Each section is structured to be concise, reproducible, and implementation-ready.

---

## Authorship and Attribution

This site was developed by **Athar Kharal, PhD**, as part of a professional initiative to model exemplary API documentation workflows using MkDocs, Postman, and automated CI/CD pipelines.

The public GitHub repository is available at:  
[https://github.com/atharkharal/chatbot-api-docs](https://github.com/atharkharal/chatbot-api-docs)

---

## Postman Collection

You can interact with the API through the official Postman Collection, available at the following link:

[https://www.postman.com/chatbotcom/chatbot-com/collection/xs58e89/chatbot-com-api](https://www.postman.com/chatbotcom/chatbot-com/collection/xs58e89/chatbot-com-api)
