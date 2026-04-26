# Module 3 Playbook Assignment - Novatech Workflow

## Project Overview
This project is an automated order-tracking assistant built on **Make.com**. It allows customers to query their order status directly through **Telegram**. The workflow searches a centralized tracking database in **Google Sheets**, uses **OpenAI (GPT-4o-mini)** to generate a personalized, professional response, and delivers the update instantly to the user.

## Workflow Architecture
The scenario follows a high-efficiency linear path designed for rapid data retrieval and natural language communication:

1.  **Trigger: Telegram (Watch Updates)**
    * Actively monitors a Telegram bot for incoming customer messages (e.g., an Order ID or Email address).
2.  **Database Search: Google Sheets (Filter Rows)**
    * **Target:** "Playbook Assignment Module 5: Tracking Order Document".
    * **Logic:** Searches Column A (Order ID) or Column C (Email) to find a match for the text sent by the user using a "contains (case insensitive)" operator.
3.  **AI Personalization: OpenAI (Create Chat Completion)**
    * **Model:** `gpt-4o-mini`.
    * **Role:** Transforms raw spreadsheet data into a warm, professional customer support message.
4.  **Response: Telegram (Send Reply Message)**
    * Delivers the finalized AI-generated message back to the user.

### Workflow Visualization & Result
The image below illustrates the completed workflow structure in Make.com, showing the end-to-end connection from the Telegram trigger to the final response.

![Final Workflow Screenshot](Project%20Screen%20Shots/04_Module%203%20Playbook_Part_5_FINAL_Workflow.jpg)

#### Live Result in Telegram
Once the workflow is triggered by an order number, it automatically retrieves the data and returns a natural language status update. Below is a live example of the bot responding to a user query:

![Telegram Order Status Response](Project%20Screen%20Shots/03_Module%203%20Playbook_Part_5_Telegram_Response.png)

*As shown, the bot identifies the order, checks the status ("Shipped"), and provides the tracking number and carrier in a friendly tone.*

## Technology Stack
* **Automation Platform:** [Make.com](https://www.make.com/)
* **Artificial Intelligence:** OpenAI API (`gpt-4o-mini`)
* **Messaging Interface:** Telegram Bot API
* **Data Management:** Google Sheets

## Configuration & Setup
1.  **Import Scenario:** Upload the JSON blueprint to your Make.com dashboard.
2.  **API Connections:** Set up connections for Telegram, OpenAI, and Google Sheets.
3.  **Spreadsheet Mapping:** Ensure the "Filter Rows" module is pointed to Spreadsheet ID: `1jfjm6y8hXwnSnd3tuPSsvF-UPdTuiRZNSOCLi984inE`.

---
*Generated for the Novatech Module 3 Playbook Assignment.*