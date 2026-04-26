# University of Southern Florida - AI Automation Workflow 
## Module 3 - Build the AI Workflow

This portfolio showcases three advanced automation projects that integrate generative AI with low-code platforms to solve real-world communication and data-handling challenges. From social media curation to intelligent customer support, these workflows demonstrate the power of combining orchestration engines with Large Language Models (LLMs).

---

## 📂 Project Summaries

### 1. Hacker News to Bluesky Pipeline (n8n)
An automated news curation system that monitors global tech trends.
* **Workflow:** Scrapes top stories from Hacker News, uses AI to distill the most relevant content, and publishes concise summaries to Bluesky.
* **Key Feature:** Implements persistent authentication for the AT Protocol to manage API rate limits efficiently.

### 2. Intelligent Assistant & Intent Classifier (Make.com)
A sophisticated multi-path AI assistant built for the healthcare/business tech space.
* **Workflow:** Watches for Telegram messages and uses a "classify-and-route" architecture. Based on intent, it searches lead databases, sends event invitations via email, or schedules meetings on Google Calendar.
* **Key Feature:** Advanced branched logic and entity extraction (names, locations, dates) using GPT-4o-mini.

### 3. Automated Order-Tracking Playbook (Make.com)
A specialized customer success automation for order management.
* **Workflow:** Provides an instant query interface for customers via Telegram. It retrieves order data from Google Sheets and generates a warm, personalized status update through AI.
* **Key Feature:** Natural language response generation that transforms raw shipping data into friendly customer communications.

---

## 🛠 Unified Technology Stack

Across these projects, a diverse set of modern tools and protocols are utilized:

| Category | Technologies Used |
| :--- | :--- |
| **Orchestration** | [n8n](https://n8n.io/), [Make.com](https://www.make.com/) |
| **AI Engines** | OpenAI API (GPT-4o, GPT-4o-mini) |
| **Communication** | Telegram Bot API, Gmail, Bluesky (AT Protocol) |
| **Data & Storage** | Google Sheets, HTML/CSS Scraping |
| **Productivity** | Google Calendar, Google Drive |
| **Data Formats** | JSON, Regular Expressions, CSS Selectors, HTML Templates |

---

## 🧬 Core Logic & Behavior

### Generative AI Integration
In every workflow, AI acts as the "brain"—not just for generating text, but for **classification and decision-making**. System prompts are engineered to ensure specific formatting, character limits, and professional tones tailored to the end-user.

### Data Interoperability
These projects demonstrate seamless data flow between disparate platforms:
* Extracting raw data from web pages or spreadsheets.
* Transforming data via AI and JSON parsing.
* Delivering structured results to messaging apps, social media, or productivity suites.

### Secure Setup
All workflows are designed with scalability and security in mind, requiring OAuth or API-key-based authentication for Telegram, OpenAI, and Google Workspace integrations.

---
*Note: This master overview consolidates the technical documentation for individual modules into a unified automation strategy.*
