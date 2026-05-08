# University of Southern Florida - AI Automation Workflow 
This portfolio showcases a suite of advanced automation projects that integrate generative AI with low-code platforms to solve complex communication, data-handling, and customer support challenges.  From intelligent intent classification to automated financial tracking, these workflows demonstrate the power of combining orchestration engines with Large Language Models (LLMs) to create seamless, "human-in-the-loop" systems.  

It taught us how to successfully leverage Workflow Automation with respect to Artificial Intelligence(AI).  It also taught us the difference between Traditional Automation and AI Worfklow Automation, as well as when to analyze and recognize what pattern to integrate and when.

I was able to complete Module #5 yesterday and have officially received my certification.  I spent most of my day completing the Automation in Make.com.  There was a significant amount of trouble shooting involved, but I must admit I was happy with the end results.  I cannot say enough about the curriculum.  A part of me was saddened to realize we were already on week 5 and it was coming to a close.  I can definitely see myself taking on more complex scenarios moving forward.

I would definitely recommend the course to any seeking a better understanding of AI Workflow Automation, how it varies from Traditional Automation, and what it brings to industry.

If interested check them out at the following link:
https://upskill.ziplines.com/university-of-south-florida/ai-automation

---

## 📂 Project Summaries

### 1. Module 5: [Enhanced Customer Support Workflow](/Module%205/README.md)
A high-precision, multi-channel AI automation system designed to streamline customer inquiries.
* **Workflow:** Leverages a Telegram interface where **GPT-4 Turbo** extracts Order IDs, names, and emails from raw text. It dynamically routes requests—including order status lookups and shipping tracking via Google Sheets—and triggers internal **Slack** alerts for human escalation.
* **Key Feature:** Advanced intent classification (`order`, `shipping`, `escalation`, `unknown`) to provide context-aware responses or immediate regional support notifications.

### 2. Module 3: [Intelligent Assistant & Intent Classifier](Module%203/Module%203%20-%20Build%20the%20AI%20Workflow%20-%20Part%204%20-%20Novatech%20-%20make_com%20-%20README.md)
A sophisticated multi-path AI assistant built for the healthcare/business tech space.
* **Workflow:** Monitors Telegram messages using a "classify-and-route" architecture. Based on intent, it searches lead databases, sends event invitations via email, or schedules meetings on Google Calendar.
* **Key Feature:** Advanced branched logic and entity extraction (names, locations, dates) using GPT-4o-mini.

### 3. Module 3: [Hacker News to Bluesky Pipeline](Module%203/Module%203%20-%20Build%20the%20AI%20Workflow%20-%20Part%202%20-%20n8n%20-%20README.md)
An automated news curation system that monitors global tech trends.
* **Workflow:** Scrapes top stories from Hacker News, uses AI to distill the most relevant content, and publishes concise summaries to Bluesky.
* **Key Feature:** Implements persistent authentication for the AT Protocol to manage API rate limits efficiently.

### 4. Module 3: [Receipt Tracking & Email Automation](Module%203/Module%203%20-%20Build%20the%20AI%20Workflow%20-%20Part%206%20-%20Receipt%20Tracking%20-%20make_com%20-%20README.md)
An AI-driven system that automates the transition from raw image to ledger.
* **Workflow:** Ingests receipt images via a dedicated Gmail Mailhook, utilizes Computer Vision to extract financial data (tax, subtotal, vendor), and logs structured records into Google Sheets.
* **Key Feature:** High-fidelity vision-to-data extraction using GPT-4o’s multimodal capabilities.

---

## 🧬 Core Logic & Behavior

### Intelligent Classification & Routing
In the **Module 5** and **Module 3 Assistant** workflows, AI acts as the primary "router." System prompts are engineered to parse customer messages into structured JSON, ensuring that inquiries for "Order Status" are handled differently than a request for "Human Help" (Escalation).

### Data Management & Validation
The workflows interface with centralized **Google Sheets** databases to validate order details and retrieve real-time status. In the Module 5 architecture, this includes mapping specific spreadsheet columns to AI-generated customer messages.

### Multi-Channel Communication
These projects demonstrate seamless data flow between disparate platforms:
- **Frontend:** Telegram Bot API for customer interaction.
- **Internal:** Slack API for team notifications and escalations.
- **Social/Web:** Bluesky (AT Protocol) and Gmail.

---

## 🛠 Unified Technology Stack

Across these modules, a diverse set of modern tools and protocols are utilized:

| Category | Technologies Used |
| :--- | :--- |
| **Orchestration** | [Make.com](https://www.make.com/), [n8n](https://n8n.io/) |
| **AI Engines** | OpenAI API (GPT-4 Turbo, GPT-4o, GPT-4o-mini, GPT-4o Vision) |
| **Communication** | Telegram Bot API, Slack API, Gmail, Bluesky (AT Protocol) |
| **Data & Storage** | Google Sheets, Google Drive, JSON Parsing |
| **Productivity** | Google Calendar |

---

## 🚀 How to Build & Run
1. **Import Blueprints:** Import the respective `.json` (Make.com) or `.json` (n8n) files into your dashboards.
2. **Configure Connections:** Authenticate your OpenAI API Keys, Telegram Bot tokens, Slack Workspace, and Google Workspace connections.
3. **Setup Data Structures:** For the **Module 5** workflow, ensure the JSON parser is correctly mapped to the GPT-4 Turbo output fields.
4. **Activate Webhooks:** Enable the scenarios to begin watching for incoming messages or mailhooks.

---
*Note: This master overview consolidates the technical documentation for Modules 3 and 5 into a unified automation strategy.*

