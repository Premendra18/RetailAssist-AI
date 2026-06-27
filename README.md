# RetailAssist AI

![Status](https://img.shields.io/badge/Status-Completed-success)
![LLM](https://img.shields.io/badge/LLM-Google%20Gemini-orange)
![Prompt%20Engineering](https://img.shields.io/badge/Focus-Prompt%20Engineering-blue)
![Knowledge%20Base](https://img.shields.io/badge/Knowledge%20Base-JSON-brightgreen)

RetailAssist AI is a prompt-engineered AI retail sales and customer support assistant designed for online consumer electronics stores.

The project demonstrates how Large Language Models (LLMs) can be structured using modular prompts, business rules, and a curated knowledge base to provide reliable, consistent, and explainable customer support.

Unlike a generic chatbot, **NovaAssist** follows predefined workflows for:

* Product Recommendations
* Product Comparisons
* FAQ Support
* Order Tracking
* Human Escalation

The project focuses on **AI Product Design, Prompt Engineering, Knowledge Base Design, Prompt Evaluation, and AI System Behavior** rather than traditional software development.

---

# Problem Statement

Online retail businesses receive thousands of repetitive customer queries every day regarding products, deliveries, returns, warranties, refunds, and order tracking.

Handling these requests manually increases operational costs, response time, and customer support workload.

Generic AI chatbots often hallucinate product information, invent policies, or produce inconsistent answers, making them unreliable for customer-facing retail environments.

---

# Solution

RetailAssist AI addresses this challenge by providing a structured retail assistant called **NovaAssist**.

NovaAssist operates using:

* Structured System Prompt
* Product Knowledge Base
* FAQ Knowledge Base
* Mock Order Database
* Business Rules
* Conversation Workflows

Instead of generating unrestricted responses, NovaAssist answers customer queries only using approved information from the provided knowledge base.

---
# Demo Gallery

The screenshots below showcase NovaAssist handling real customer interactions during evaluation. Each conversation demonstrates a specific capability of the assistant while following predefined business rules and using the structured knowledge base.

---

## 1. Product Recommendation – Requirement Discovery

![Product Recommendation](Screenshots/Product%20Recommendation.png)

NovaAssist begins by understanding the customer's intent instead of recommending products immediately. It asks only the minimum clarification questions required to identify the customer's budget, primary use case, and preferences before making a recommendation.

---

## 2. Product Recommendation – Final Recommendation

![Product Recommended](Screenshots/Product%20Recommended.png)

After collecting the required information, NovaAssist recommends only products that satisfy the customer's mandatory requirements. Recommendations include product specifications, pricing, and a clear explanation of why each product matches the customer's needs.

---

## 3. Product Comparison

![Product Comparison](Screenshots/Product%20Comparison.png)

NovaAssist compares products using only factual information from the product catalog. It highlights objective differences, explains trade-offs, and avoids unsupported claims or marketing language.

---

## 4. Hallucination Prevention

![Hallucination Prevention](Screenshots/iPhone%20Hallucination%20Test.png)

When asked about a product that does not exist in the knowledge base, NovaAssist refuses to fabricate information. Instead, it clearly states that the product is unavailable and recommends valid alternatives from the catalog.

---

## 5. Order Tracking

![Order Tracking](Screenshots/Order%20Tracking.png)

NovaAssist validates the customer's Order ID before retrieving information from the mock order database. This demonstrates secure order handling and adherence to predefined customer support workflows.

---

# Features

## AI-Powered Product Recommendations

* Understands customer intent before recommending products.
* Collects only the minimum information required.
* Applies domain-specific recommendation rules.
* Recommends only products available in the NovaMart catalog.
* Filters products based on mandatory customer requirements.

---

## Product Comparison

* Compares products using factual specifications.
* Explains objective trade-offs.
* Avoids marketing language.
* Never invents specifications.

---

## Customer Support

* Answers FAQs using the structured knowledge base.
* Provides consistent information regarding:

  * Shipping
  * Returns
  * Refunds
  * Warranty
  * Payments

---

## Order Support

* Requires a valid Order ID.
* Retrieves information from the mock order database.
* Simulates order tracking.
* Protects customer information by following predefined workflows.

---

## Human Escalation

* Detects situations requiring human assistance.
* Escalates unsupported requests.
* Avoids making promises beyond defined business rules.

---

## Hallucination Prevention

* Uses only approved knowledge base information.
* Never invents products, policies, specifications, or order details.
* Clearly communicates when information is unavailable.

---
### Tech Stack

| Category           | Technology             |
| ------------------ | ---------------------- |
| AI Platform        | Google AI Studio       |
| LLM                | Google Gemini          |
| Prompt Engineering | Modular System Prompts |
| Knowledge Base     | JSON                   |
| Documentation      | Markdown               |
| Version Control    | Git & GitHub           |

---

# System Architecture

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

# Repository Structure

```text
RetailAssist-AI/
│
├── README.md
│
├── data/
│   ├── products.json
│   ├── faqs.json
│   └── orders.json
│
├── prompts/
│   └── system_prompt.md
│
├── evaluation/
│   ├── test_cases.md
│   └── prompt_iterations.md
│
├── demo/
│   └── sample_conversations.md
│
└── screenshots/
    ├── Product Recommendation.png
    ├── Product Recommended.png
    ├── Product Comparison.png
    ├── iPhone Hallucination Test.png
    └── Ordert Tracking.png
```

---

# Prompt Engineering Approach

RetailAssist AI was designed using an iterative prompt engineering methodology rather than a single monolithic prompt.

## System Prompt

The system prompt defines:

* Assistant identity
* Responsibilities
* Conversation workflow
* Business rules
* Recommendation logic
* Safety guardrails
* Human escalation policy
* Response formatting

---

## Knowledge Base

NovaAssist is constrained using three structured datasets:

* **products.json** — Product catalog
* **faqs.json** — Store policies and FAQs
* **orders.json** — Mock customer order database

This approach minimizes hallucinations and improves response consistency.

---

## Conversation Workflow

For every customer interaction, NovaAssist follows a structured workflow:

1. Identify customer intent.
2. Determine whether sufficient information is available.
3. Ask only the minimum clarification questions when required.
4. Retrieve information from the appropriate knowledge source.
5. Apply business rules and recommendation policies.
6. Generate a structured response.
7. Escalate to a human representative when appropriate.

---

## Hallucination Prevention

NovaAssist is explicitly instructed to:

* Never invent products.
* Never invent specifications.
* Never invent prices.
* Never fabricate order information.
* Never create store policies.
* Clearly state when required information is unavailable.

---

# Evaluation Strategy

NovaAssist was evaluated using structured scenario-based testing.

Evaluation categories included:

* Product Recommendations
* Product Comparisons
* FAQ Responses
* Order Support
* Hallucination Prevention
* Human Escalation
* Out-of-Scope Requests

Prompt behavior was continuously refined using observations collected during testing.

Detailed evaluation reports are available in:

* `evaluation/test_cases.md`
* `evaluation/prompt_iterations.md`

---

# Key Learnings

During development, NovaAssist was improved through multiple prompt iterations driven by structured testing rather than trial and error.

The project demonstrates that reliable AI assistants require more than a well-written prompt—they also require:

* Clearly defined business rules
* Structured knowledge bases
* Controlled conversation workflows
* Systematic evaluation
* Iterative prompt refinement

---

# Future Improvements

Potential enhancements for production deployment include:

* Integration with live inventory APIs
* Live order management APIs
* Retrieval-Augmented Generation (RAG)
* Vector database integration
* Voice-enabled customer support
* Multi-language support
* Customer analytics dashboard
* Real-time inventory synchronization
* CRM and ERP integration

---

# Conclusion

RetailAssist AI demonstrates how prompt engineering, structured knowledge bases, business rules, and iterative evaluation can be combined to build a reliable AI-powered retail assistant.

Rather than functioning as a generic chatbot, NovaAssist follows predefined workflows, uses only approved knowledge sources, and continuously improves through structured prompt refinement—reflecting an AI product engineering approach suitable for real-world customer support systems.

