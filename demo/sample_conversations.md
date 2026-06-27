# NovaAssist Demo Conversations

This document showcases representative customer interactions with NovaAssist.

The conversations were generated during prompt evaluation and demonstrate how the assistant follows structured business rules, retrieves information from the knowledge base, and avoids hallucinations.

---

# Conversation 1 – Product Recommendation

### Customer

> I need a laptop under ₹80,000.

### NovaAssist

To help me find the most suitable laptop under ₹80,000 from our catalog, could you please share a few details about how you plan to use it?

1. **Primary Use Case:** What will be your main use case for the laptop (e.g., general office work, software development, creative editing, or student studies)?
2. **Screen Size & Portability:** Do you prefer a highly compact and lightweight laptop (13-inch or 14-inch screen) for travel, or would you prefer a larger display?

Once you let me know your preferences, I will recommend the best options from our inventory.
### Customer

> Software development.
>
> Compact.

### NovaAssist

Based on your preference for a compact laptop for software development under ₹80,000, we have one product in our catalog that meets your specifications:

### TitanBook Air 14 (NM-LP-201)
* **Price:** ₹74,999
* **Key Features:**
  * 14-inch QHD IPS Display
  * Intel Core i5 13th Gen Processor
  * 16GB LPDDR5 RAM / 512GB SSD
  * Up to 12 Hours Battery Life
  * Weight: 1.25 kg
  * 1 Year Onsite Warranty
  * **Stock Status:** In Stock
* **Reason for Recommendation:** This model is suited for programming and software development within your budget. It features a compact 14-inch display and is lightweight at just 1.25 kg, making it highly portable. Crucially, the 16GB of LPDDR5 RAM and the 13th Gen Intel Core i5 processor provide the necessary performance for software development environments, multitasking, and compiling code. 

*(Note: We also carry the NovaBook Flex 13 at ₹49,999, but we do not recommend it for your use case as its 8GB RAM and Core i3 processor do not meet the standard performance requirements for software development.)*
Please let me know if you would like to know more about this laptop or if you have any other questions!

---

### What this demonstrates

* Intent recognition
* Minimal clarification questions
* Domain-specific recommendation rules
* Requirement-based filtering

---

# Conversation 2 – Product Comparison

### Customer

> Compare TitanBook Air 14 and AeroGlide Pro 16.

### NovaAssist

Here is an objective comparison of the **TitanBook Air 14** and the **AeroGlide Pro 16** based on their specifications in our catalog:

### Specifications Comparison

| Feature | TitanBook Air 14 (NM-LP-201) | AeroGlide Pro 16 (NM-LP-202) |
| :--- | :--- | :--- |
| **Price** | ₹74,999 | ₹139,999 |
| **Rating** | 4.6 | 4.8 |
| **Display** | 14-inch QHD IPS | 16-inch Mini-LED 165Hz |
| **Processor** | Intel Core i5 13th Gen | Intel Core i7 13th Gen |
| **Graphics (GPU)** | Integrated (Not specified in catalog) | Dedicated NVIDIA RTX 4060 |
| **RAM** | 16GB LPDDR5 | 32GB |
| **Storage** | 512GB SSD | 1TB NVMe SSD |
| **Battery Life** | Up to 12 Hours | Not specified in catalog |
| **Weight** | 1.25 kg | 2.1 kg |
| **Keyboard** | Standard (Not specified in catalog) | RGB Backlit Keyboard |
| **Camera** | Not specified in catalog | Not specified in catalog |
| **Warranty** | 1 Year Onsite Warranty | 2 Years Accidental Damage Protection |
| **Stock Status** | In Stock | In Stock |

---

### Key Trade-Offs

* **Portability and Battery vs. Power and Performance:** The **TitanBook Air 14** is significantly lighter (1.25 kg compared to 2.1 kg) and offers a specified battery life of up to 12 hours, making it highly portable. On the other hand, the **AeroGlide Pro 16** offers double the RAM (32GB), double the storage (1TB SSD), a more powerful Core i7 processor, and a dedicated NVIDIA RTX 4060 GPU, which is suitable for gaming, video editing, or heavy rendering.
* **Display Difference:** The **TitanBook Air 14** has a 14-inch QHD display. The **AeroGlide Pro 16** features a larger 16-inch Mini-LED display with a high 165Hz refresh rate, providing smoother visuals and different display technology.
* **Price and Protection:** The **TitanBook Air 14** is a more budget-friendly option at ₹74,999 and comes with a 1-year onsite warranty. The **AeroGlide Pro 16** is priced higher at ₹139,999 but includes a longer 2-year warranty that covers accidental damage.

Please let me know if you would like to know more about either of these laptops!

---

### What this demonstrates

* Objective product comparison
* Trade-off explanation
* Hallucination prevention
* Structured response formatting

---

# Conversation 3 – Hallucination Prevention

### Customer

> I want to buy an iPhone 16 Pro Max.

### NovaAssist

The iPhone 16 Pro Max is not available in the NovaMart product catalog.

However, we currently offer these premium alternatives:

* Zenith Pro Max
* Prime Fold X

Please let me know if you'd like to compare these models.

---

### What this demonstrates

* Hallucination prevention
* Catalog-constrained recommendations
* Helpful alternative suggestions

---

# Conversation 4 – Order Tracking

### Customer

> Where is my order?

### NovaAssist

Could you please provide your Order ID?

### Customer

> #NM-99999

### NovaAssist

I couldn't find that Order ID in our system.

Please verify the Order ID from your invoice or confirmation email.

If the issue persists, I can help summarize the issue and connect you with a human support representative.

---

### What this demonstrates

* Order validation
* Privacy-aware workflow
* Human escalation support

---

# Demo Summary

The conversations above demonstrate NovaAssist's core capabilities:

* AI-powered product recommendations
* Objective product comparisons
* FAQ and policy retrieval
* Secure order support
* Hallucination prevention
* Structured conversation workflow
* Prompt-engineered decision making
