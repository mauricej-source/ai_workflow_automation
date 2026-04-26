# Module 2 - First Automation Workflow: Hacker News to Bluesky

An automated n8n pipeline that monitors tech trends on Hacker News, uses generative AI to distill the most relevant stories, and publishes curated summaries to Bluesky.

## 🚀 Workflow in Action

The following snapshots illustrate the end-to-end execution of the automation.

### 1. Execution Phase
When the workflow is triggered, it systematically progresses through data ingestion, AI processing, and authentication checks.
![Workflow Processing](Project%20Screen%20Shots/Module_3_Build_the_AI_Workflow_Part_2_Processing_Screenshot.png)

### 2. Successful Completion
Upon successful execution, all nodes (from scraping to posting) indicate a completed status, confirming that the data has been transformed and transmitted correctly.
![Workflow Successfully Completed](Project%20Screen%20Shots/Module_3_Build_the_AI_Workflow_Part_2_SuccessfullyCompleted.png)

### 3. Final Output (Bluesky)
The end result is a professionally formatted post on Bluesky, featuring curated titles and URLs delivered in real-time.
![BlueSky Post Screenshot](Project%20Screen%20Shots/Module_3_Build_the_AI_Workflow_Part_2_BlueSky_Screenshot.jpg)

---

## 🛠 Tech Stack

* **Orchestration:** [n8n](https://n8n.io/)
* **AI Engine:** [OpenAI API](https://openai.com/) (GPT-4o/5-mini)
* **Data Source:** [Hacker News](https://news.ycombinator.com/)
* **Platform:** [Bluesky](https://bsky.app/) (AT Protocol)

## 🧬 Workflow Behavior & Logic

### Data Ingestion
The workflow begins by scraping the Hacker News front page. It uses CSS selectors to isolate story titles and links, which are then split into individual items for processing.

### AI Transformation
The **AI Agent** takes the raw HTML data and, guided by a specialized system prompt, selects the top items and formats them into a concise list. It specifically manages:
* **Conciseness:** Ensuring the final string stays under the 300-character limit.
* **Formatting:** Inserting necessary newlines (`\n`) and separators (` => `) for readability.

### Persistent Authentication
To avoid Bluesky's rate limits, the workflow implements a smart session management system:
1.  **Token Check:** It first attempts to retrieve an existing `accessJwt` from the workflow's internal static data.
2.  **Conditional Login:** A login request to the AT Protocol server is only performed if a valid token is not found.
3.  **Token Storage:** New tokens are cached to be reused in subsequent runs.

### Posting to AT Protocol
The final **HTTP Request** node sends a structured JSON payload to the `createRecord` endpoint. It uses dynamic expressions to safely wrap the AI-generated text, ensuring that special characters and line breaks do not invalidate the JSON structure.

## ⚙️ Setup
1.  Import the provided `.json` workflow into n8n.
2.  Configure your **OpenAI** credentials.
3.  Add your **Bluesky** handle and **App Password** in the session creation nodes.

---
*Note: Always redact sensitive credentials before sharing your workflow JSON publicly.*
