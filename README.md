# 🧴 Nigerian-Standard Automated Customer Feedback & Engagement Workflow

This repository contains an intelligent n8n workflow designed to automate customer feedback analysis and personalized email responses for a Nigerian business. It uses AI to understand customer sentiment, drafts a culturally appropriate response, and can automatically generate and send a promotional coupon via Gmail if the feedback warrants it.

---

## 🧠 Workflow Summary

This workflow is triggered manually and performs the following:

1.  **Fetches customer feedback data** from a Google Sheet.
2.  **Sets the campaign's tone and target** (configured for a warm, friendly Nigerian style).
3.  **Leverages the DeepSeek AI model** (via OpenRouter) to analyze the sentiment of the product feedback.
4.  **Generates a personalized email response** including a headline, body, and a decision on whether to send a coupon.
5.  **Validates the AI's output** to ensure quality and prevent errors.
6.  **Branches based on the coupon decision:**
    -   **If no coupon:** Builds a standard "thank you" email.
    -   **If coupon needed:** Generates coupon details and builds a promotional email.
7.  **Sends the final, professionally styled HTML email** directly to the customer via Gmail.

---

## 🗂️ Workflow Architecture

```mermaid
graph TD
    A["Manual Trigger: Start Feedback Processing"] --> B["Google Sheets: Fetch Customer Feedback"]
    B --> C["Set: Campaign Parameters (Tone & Target)"]
    C --> D["AI Model: DeepSeek (via OpenRouter)"]
    D --> E["AI Agent: Analyze Sentiment & Draft Response"]
    E --> F["Merge: AI Draft + Customer Data"]
    F --> G{"If: AI Generated Valid Headline & Body?"}
    G -- Yes --> H{"If: Send Coupon? (SendCoupon == true)"}
    G -- No --> I["Stop & Error: Invalid AI Output"]
    H -- No --> J["HTML: Standard Email Template (No Coupon)"]
    J --> K["Merge: Final Standard Email Package"]
    H -- Yes --> L["Set: Generate Coupon Details"]
    L --> M["HTML: Promotional Email Template (With Coupon)"]
    M --> N["Merge: Final Promotional Email Package"]
    K --> O["Gmail: Send Customer Engagement Email"]
    N --> O
```
