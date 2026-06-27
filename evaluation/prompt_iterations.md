# Prompt Iteration Log

This document records the iterative improvements made to the NovaAssist system prompt during evaluation.

Rather than treating prompt engineering as a one-time activity, the assistant was continuously refined based on observed behaviour during structured testing.

---

# Version 1.0 – Initial Prompt

### Objective

Build a retail AI assistant capable of:

* Product recommendations
* Product comparisons
* FAQ support
* Order tracking
* Human escalation

using only a structured knowledge base.

---

## Observation

The assistant successfully:

* Recommended products
* Compared products
* Retrieved FAQs
* Tracked mock orders

However, several behavioural improvements were identified during testing.

---

# Iteration 1 – Mandatory Requirement Filtering

### Test Case

Customer requested:

> Lightweight laptop with 16GB RAM for software development.

### Observation

NovaAssist recommended:

* TitanBook Air 14 ✅
* NovaBook Flex 13 ⚠️

NovaBook Flex contained only 8GB RAM and did not satisfy the customer's mandatory requirement.

### Improvement

Updated Product Recommendation Rules:

* Recommend only products satisfying every mandatory customer requirement.
* Do not include partially matching products as recommendations or alternatives.
* If only one product satisfies all requirements, recommend only that product.

### Expected Improvement

Only fully matching products should be recommended.

---

# Iteration 2 – Single Matching Product Rule

### Test Case

Customer requested:

> Smartphone under ₹20,000

### Observation

Only one smartphone satisfied the budget.

Asking clarification questions created unnecessary conversation.

### Improvement

Added rule:

If the customer's request uniquely identifies a single product that satisfies all mandatory requirements, recommend that product directly instead of asking unnecessary clarification questions.

### Expected Improvement

Reduce unnecessary customer interaction.

---

# Iteration 3 – Independent Customer Requests

### Test Case

Running multiple evaluations inside the same conversation.

### Observation

NovaAssist referred to previous messages using phrases such as:

> "As we discussed..."

This caused recommendations to depend on earlier interactions.

### Improvement

Added Conversation Workflow rule:

Treat each new customer request as an independent interaction unless the customer explicitly asks to continue the conversation.

Do not assume previous preferences or previously collected information.

### Expected Improvement

Each customer query is evaluated independently.

---

# Iteration 4 – Clarification Question Optimization

### Test Case

Customer requested:

> Laptop under ₹80,000

### Observation

NovaAssist asked several overlapping questions.

The interaction felt longer than necessary.

### Improvement

Added rules:

* Ask only the minimum number of clarification questions required.
* Avoid overlapping questions.
* Group related questions whenever possible.

### Expected Improvement

Shorter and more natural conversations.

---

# Iteration 5 – Domain-Specific Recommendation Policies

### Test Case

Customer requested:

> Compact laptop for software development.

### Observation

NovaAssist still considered entry-level laptops suitable for software development.

### Improvement

Added recommendation policies for common use cases.

#### Software Development

* Prefer 16GB RAM or higher.
* Prefer Intel Core i5 / Ryzen 5 or higher.
* Avoid recommending entry-level hardware unless explicitly requested.

#### Gaming

* Prefer dedicated GPUs.
* Prefer higher refresh-rate displays.

#### Content Creation

* Prefer higher RAM.
* Prefer larger SSD storage.
* Prefer displays suitable for creative workloads.

### Expected Improvement

Recommendations better match customer intent and professional use cases.

---

# Evaluation Summary

Prompt engineering followed an iterative cycle:

Design Prompt

↓

Evaluate Behaviour

↓

Identify Weaknesses

↓

Refine Prompt

↓

Re-test

↓

Document Improvements

---

## Key Outcomes

After five prompt iterations, NovaAssist demonstrated:

* More natural conversations
* Reduced unnecessary clarification questions
* Better requirement matching
* Stronger hallucination prevention
* Domain-aware recommendations
* Improved consistency across customer interactions

This iterative process reflects how prompt engineering is performed during AI product development rather than treating prompt creation as a one-time task.

