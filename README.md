# RetailAssist AI

**RetailAssist AI** is a prompt-engineered AI retail sales and customer support assistant designed for online consumer electronics stores.

The project demonstrates how Large Language Models (LLMs) can be structured using modular prompts, business rules, and a curated knowledge base to provide reliable product recommendations and customer support.

Unlike a generic chatbot, RetailAssist AI follows predefined conversation workflows for:

* Product recommendations
* Product comparisons
* FAQ handling
* Order support
* Human escalation

The project focuses on **AI Product Design**, **Prompt Engineering**, **Knowledge Base Design**, and **Prompt Evaluation** rather than traditional software development.

---

## Problem Statement

Online retail businesses receive thousands of repetitive customer queries every day regarding products, deliveries, returns, warranties, refunds, and order tracking.

Handling these queries manually increases response time, operational costs, and workload for customer support teams.

Generic AI chatbots often hallucinate product information or provide inconsistent answers, making them unsuitable for customer-facing retail environments.

---

## Solution

RetailAssist AI addresses this problem by providing a structured AI assistant called **NovaAssist**.

NovaAssist operates using:

* A structured system prompt
* Product knowledge base
* FAQ knowledge base
* Mock order database
* Business rules
* Conversation workflows

---

## Features

### AI-Powered Product Recommendations

* Understands customer intent before making recommendations.
* Asks clarifying questions about budget, preferences, and use case.
* Recommends only products available in the NovaMart catalog.

### Product Comparison

* Compares products using objective specifications.
* Highlights trade-offs instead of subjective opinions.
* Avoids unsupported claims or marketing language.

### Customer Support

* Answers frequently asked questions using the FAQ knowledge base.
* Explains shipping, returns, refunds, warranty, and payment policies.
* Provides consistent responses based on predefined business rules.

### Order Support

* Handles order-related queries using a mock order database.
* Requires a valid Order ID before retrieving order information.
* Simulates order tracking for demonstration purposes.

### Human Escalation

* Escalates conversations that require human intervention.
* Avoids making promises or performing unsupported actions.

### Hallucination Prevention

* Uses only approved information from the knowledge base.
* Clearly states when information is unavailable instead of guessing.

---

## System Architecture

```text
                    Customer
                        │
                        ▼
                NovaAssist AI
                        │
        ┌───────────────┼────────────────┐
        ▼               ▼                ▼
 Product Catalog     FAQ Database     Order Database
(products.json)      (faqs.json)      (orders.json)
        │               │                │
        └───────────────┼────────────────┘
                        ▼
              Business Rules & System Prompt
                        │
                        ▼
                 Customer Response
```

---

## Repository Structure

```
RetailAssist-AI/
│
├── README.md
├── data/
│   ├── products.json
│   ├── faqs.json
│   └── orders.json
│
├── prompts/
│   └── system_prompt.md
│
├── evaluation/
│
└── demo/
```

---

## Prompt Engineering Approach

RetailAssist AI was designed using a structured prompt engineering approach rather than a single monolithic prompt.

### System Prompt

The system prompt establishes NovaAssist's identity, responsibilities, business rules, conversation workflow, response formatting, safety guardrails, and escalation logic.

### Knowledge Base

Instead of relying entirely on the language model's internal knowledge, the assistant is constrained by three structured datasets:

* `products.json` – Product catalog
* `faqs.json` – Store policies and FAQs
* `orders.json` – Mock customer order database

This approach reduces hallucinations and ensures consistent responses.

### Conversation Workflow

For every customer interaction, NovaAssist follows a structured workflow:

1. Identify customer intent.
2. Determine whether additional information is required.
3. Ask clarifying questions when necessary.
4. Retrieve relevant information from the appropriate knowledge source.
5. Generate a structured response.
6. Escalate to a human representative when required.

### Hallucination Prevention

NovaAssist is instructed to:

* Never invent products or specifications.
* Never fabricate order information.
* Never create store policies.
* Clearly state when required information is unavailable.

---

## Evaluation Strategy

The assistant is evaluated using scenario-based testing across multiple customer interactions.

Evaluation categories include:

* Product Recommendations
* Product Comparisons
* FAQ Responses
* Order Support
* Human Escalation
* Hallucination Prevention
* Out-of-Scope Requests

The objective is to verify that NovaAssist follows business rules consistently while providing helpful and reliable responses.


Instead of generating unrestricted responses, NovaAssist follows predefined workflows and responds only using approved information from the provided knowledge base.
