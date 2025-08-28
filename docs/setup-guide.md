# 🛠️ Setup Guide for Customer Feedback Engagement Workflow

Welcome! This guide walks you through setting up the workflow using [n8n](https://n8n.io), even if you're new to automation.

---

## 📦 Prerequisites

- Node.js ≥ 18
- n8n installed globally (`npm install -g n8n`)
- Google Sheets access
- Gmail account with OAuth2 credentials
- OpenRouter API key

---

## 🚀 Step-by-Step Setup

### 1. Clone the Repository

```bash
git clone https://github.com/CryptoLab-service/Customer-Feedback-Engagement-Workflow.git
cd Customer-Feedback-Engagement-Workflow
```

### 2. Configure Environment Variables
Copy the template and fill in your credentials:

```bash
cp .env.example .env
```
Update ```.env``` with your Gmail and OpenRouter keys.

### 3. Launch n8n

```bash
n8n start
```
Access the editor at [http://localhost:5678](http://localhost:5678)

### 4. Import the Workflow
* Open n8n
* Click **Import Workflow**
* Select ```workflow.json``` from the repo

### 5. Connect Your Google Sheet
Ensure your sheet matches the format in ```sample-data/customer-feedback-sheet.csv``` from the repo

### 6. Test the Flow
Trigger the workflow manually or set up a schedule. You should receive a personalized email response with optional coupons.

---

### Done!
You’re now ready to engage customers with AI-powered feedback responses.

```bash

---

## 🖼️ `assets/logo.svg`

Here’s a minimal SVG logo optimized for email headers:

```svg
<svg width="180" height="40" viewBox="0 0 180 40" xmlns="http://www.w3.org/2000/svg">
  <text x="0" y="28" font-family="Segoe UI, sans-serif" font-size="28" fill="#e67e22">TJ Essentials</text>
</svg>
```
