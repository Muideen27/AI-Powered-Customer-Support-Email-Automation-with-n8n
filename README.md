# AI-Powered-Customer-Support-Email-Automation-with-n8n

An intelligent end-to-end customer support email automation workflow built using n8n, Gmail, OpenAI-compatible LLMs, Pinecone Vector Database, and Retrieval-Augmented Generation (RAG).

This project automatically classifies incoming emails, retrieves relevant support knowledge from a vector database, drafts professional customer support responses, and introduces a human-in-the-loop approval layer before responses are sent.

---

# Project Overview

This workflow automates customer support triage and response drafting using AI while maintaining human oversight for quality assurance.

The system:

* Monitors incoming Gmail messages
* Detects whether emails are customer-support related
* Retrieves relevant company policies and FAQs using Pinecone Vector Store
* Generates professional AI-powered draft responses
* Saves replies as Gmail drafts
* Sends review notifications to a human operator
* Automatically labels non-support emails

---

# Workflow Architecture

```text
Gmail Trigger
    ↓
Edit Fields / Preprocessing
    ↓
Customer Support Classification
    ↓
IF Customer Support?
    ├── TRUE
    │      ↓
    │ Customer Support AI Agent
    │      ↓
    │ Pinecone Vector Store Retrieval
    │      ↓
    │ Gmail Draft Creation
    │      ↓
    │ Human Review Notification
    │
    └── FALSE
           ↓
      Gmail Labeling
```

---

# Key Features

## AI Customer Support Agent

* Automatically drafts professional customer support responses
* Uses company documentation for policy-aware responses
* Maintains empathetic and professional tone

## Retrieval-Augmented Generation (RAG)

* Uses Pinecone Vector Database
* Retrieves FAQs, policies, and support documentation
* Reduces hallucinations in generated responses

## Human-in-the-Loop Approval

* AI creates Gmail drafts only
* Human reviewer receives notification
* Manual approval before sending

## Intelligent Email Classification

* Distinguishes customer support emails from unrelated emails
* Automatically labels non-support emails

## Gmail Integration

* Gmail Trigger
* Draft Creation
* Email Notifications
* Label Management

---

# Technologies Used

| Technology        | Purpose                 |
| ----------------- | ----------------------- |
| n8n               | Workflow automation     |
| Gmail API         | Email integration       |
| OpenAI / Gemini   | LLM generation          |
| Pinecone          | Vector database         |
| OpenAI Embeddings | Semantic search         |
| RAG Architecture  | Context-aware responses |

---

# Project Structure

```text
project-root/
│
├── workflows/
│   ├── customer-support-workflow.json
│   └── pinecone-ingestion-workflow.json
│
├── docs/
│   ├── support-policies.pdf
│   ├── faq.txt
│   └── knowledge-base/
│
├── screenshots/
│   ├── workflow-overview.png
│   ├── customer-support-flow.png
│   └── pinecone-ingestion.png
│
├── README.md
├── .gitignore
└── requirements.md
```

---

# Required Files To Add

## 1. Main Workflow Export

Export your complete n8n workflow:

```text
workflows/customer-support-workflow.json
```

This should contain:

* Gmail Trigger
* AI Agent
* Pinecone Integration
* Draft Creation
* Notification Flow
* Non-support Label Flow

---

## 2. Pinecone Ingestion Workflow

Export your Pinecone ingestion pipeline:

```text
workflows/pinecone-ingestion-workflow.json
```

This workflow includes:

* File Download
* Data Loader
* Embeddings Generation
* Pinecone Upsert

---

## 3. Knowledge Base Documents

Add sample support documents:

```text
docs/
```

Examples:

* Refund policies
* Shipping policies
* FAQ documents
* Subscription rules

DO NOT upload sensitive company data.

---

## 4. Screenshots

Add workflow screenshots:

```text
screenshots/
```

Recommended screenshots:

* Main workflow
* Pinecone ingestion flow
* Draft creation flow
* Human review notification flow

---

# Environment Variables

Create credentials in n8n for:

## Gmail OAuth2

Required for:

* Gmail Trigger
* Draft Creation
* Notifications
* Labeling

## Pinecone API Key

Required for vector search and retrieval.

## OpenAI / Gemini API Key

Required for:

* LLM generation
* Embeddings

---

# Human-in-the-Loop Design

This project intentionally avoids fully autonomous email sending.

Instead:

1. AI drafts the response
2. Gmail saves the response as a draft
3. Human reviewer receives notification
4. Human manually reviews and sends

This architecture improves:

* reliability
* trust
* compliance
* quality control

---

# Example Use Cases

* Customer support automation
* Email triage systems
* AI-assisted help desks
* FAQ automation
* Internal support systems
* RAG-powered customer service workflows

---

# Future Improvements

Potential enhancements:

* Confidence scoring
* Sentiment analysis
* Multi-label classification
* Slack notifications
* Auto-ticket generation
* CRM integration
* Analytics dashboard
* Multi-language support

---

# Setup Instructions

## 1. Clone Repository

```bash
git clone https://github.com/Muideen27/AI-Powered-Customer-Support-Email-Automation-with-n8n
```

---

## 2. Import Workflow into n8n

Import:

```text
workflows/customer-support-workflow.json
```

and

```text
workflows/pinecone-ingestion-workflow.json
```

---

## 3. Configure Credentials

Set up:

* Gmail OAuth2
* OpenAI/Gemini API
* Pinecone API

---

## 4. Upload Knowledge Base

Run the Pinecone ingestion workflow to embed support documentation.

---

## 5. Execute Workflow

Activate the workflow and monitor incoming support emails.

---

# Security Notes

* Never commit API keys
* Never upload sensitive customer data
* Use environment variables or n8n credentials
* Remove confidential support documents before publishing

---

# Portfolio Value

This project demonstrates:

* AI workflow orchestration
* RAG implementation
* LLM integration
* Email automation
* Human-in-the-loop systems
* Vector databases
* Enterprise workflow design
* AI-assisted customer operations

---

# License

MIT License

---

# Author

Muideen Ilori

AI Automation Engineer | Workflow Automation | LLM Applications | RAG Systems
