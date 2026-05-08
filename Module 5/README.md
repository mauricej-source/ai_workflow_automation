# Module 5 - Enhanced Module 3 Customer Support Workflow

## Project Description
This project implements an intelligent, multi-channel AI automation workflow designed to streamline customer support inquiries. By leveraging **Telegram** as the primary interface, the system uses **GPT-4 Turbo** for high-precision data extraction and intent classification. The workflow dynamically routes requests—ranging from order status and shipping tracking to human escalation—ensuring customers receive immediate, context-aware responses while notifying internal teams via **Slack** when manual intervention is required.

## Application Behavior
The application follows a structured logic path to process customer messages into actionable data.

### 1. Workflow Architecture
The system is triggered by a Telegram webhook. Incoming messages are processed by an OpenAI GPT-4 Turbo model that extracts the Order ID, Customer Name, and Email, while classifying the intent into categories like `order`, `shipping`, `escalation`, or `unknown`.

![00_Module_5_Workflow](screenshots/00_Module_5_Workflow.png)
*Figure 1: Overall Architecture of the Workflow.*

### 2. Data Management & Validation
The system interfaces with a centralized Google Sheets database to validate order details and retrieve real-time shipping information.

![02_Module_5_Workflow_Google_Sheets](screenshots/02_Module_5_Workflow_Google_Sheets.png)
*Figure 2: Google Sheets Data used for testing and performance.*

### 3. Automated Order & Shipping Updates
* **Order Status Path:** If classified as an "order" inquiry, the system retrieves the status from Google Sheets, generates a personalized response using AI, and replies to the customer via the **ConnerMcCleod Telegram Bot**.

![03_Module_5_Workflow_Order_Status](screenshots/03_Module_5_Workflow_Order_Status.png)
*Figure 3: Order Status redirection to Telegram Chatbot.*

* **Shipping & Unknown Queries:** For shipping requests, the bot provides tracking numbers and carriers. If the intent is unclear, the system provides a helpful "unknown" response guiding the user on how to format their query.

![04_Module_5_Workflow_Shipping_Unknown_Escalation](screenshots/04_Module_5_Workflow_Shipping_Unknown_Escalation.png)
*Figure 4: Shipping Status, Escalation, and Unknown Workflow Paths.*

### 4. Support Escalation
When a customer requests a "person," "human," or "escalation," the workflow triggers an internal alert. A notification is sent to the **Regional Agent Support Team** via Slack to ensure a swift follow-up.

![05_Module_5_Workflow_Escalation](screenshots/05_Module_5_Workflow_Escalation.png)
*Figure 5: Escalation Notification to Regional Agent Support Team.*

## Application Help
The system provides a built-in guidance mechanism. If the AI cannot confidently classify a request, it automatically replies to the user with:
- Instructions on how to provide an **Order ID**.
- Keywords to use for faster processing (e.g., 'order', 'shipping').
- Instructions for requesting human assistance (e.g., 'help', 'support', 'escalation').

## Project Stack of Technology
- **Orchestration:** Make.com (formerly Integromat)
- **Communication (Frontend):** Telegram Bot API
- **Artificial Intelligence:** OpenAI GPT-4 Turbo (Structured Data Extraction) & GPT-4o-mini (Message Generation)
- **Database:** Google Sheets
- **Internal Communications:** Slack API
- **Data Format:** JSON (Custom Data Structures & Schema Mapping)

## How to Build & Run the Project
1.  **Import Blueprint:** Download the `make_com.blueprint.json` file and import it into your Make.com dashboard.
2.  **Configure Connections:**
    -   **Telegram:** Link your Telegram Bot token.
    -   **OpenAI:** Authenticate with your OpenAI API Key.
    -   **Google Sheets:** Select the "Order Tracking Status Document" spreadsheet.
    -   **Slack:** Connect to the workspace and channel designated for internal support.
3.  **Setup Data Structure:** Ensure the JSON parser (Module 18) is correctly mapped to the GPT-4 Turbo output.
4.  **Activate Webhook:** Enable the scenario to start watching for Telegram updates.

## Reference Materials Required to Understand the Project
- **Make.com Help Center:** Understanding Scenarios, Routers, and Filter logic.
- **OpenAI API Documentation:** Best practices for JSON mode and system prompting.
- **Telegram Bot API Documentation:** Managing webhooks and chat interactions.
- **JSON Data Structures:** Familiarity with mapping specific fields (classification, order_id, email).
