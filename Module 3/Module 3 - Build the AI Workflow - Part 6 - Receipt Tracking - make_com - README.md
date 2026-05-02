# Module 3: Build the AI Workflow - Receipt Tracking - Email Automation

## Project Description
This project provides an automated pipeline for tracking expenses. It monitors a specialized email address for receipt attachments, uses AI (GPT-4o) to "read" those receipts, and organizes the data into a Google Sheets spreadsheet. This eliminates manual data entry and provides a real-time overview of spending.

## Workflow Architecture
The system follows a linear data processing pipeline designed for reliability and scalability:

* **Ingestion Tier:** A dedicated Mailhook (Gmail) receives incoming emails and extracts binary image data from attachments.
* **Orchestration Tier:** A Make.com scenario serves as the central hub, iterating through multiple attachments and managing the API handshake with OpenAI.
* **Intelligence Tier:** GPT-4o performs high-fidelity OCR to identify key financial markers and contextually categorizes the expense.
* **Transformation Tier:** A structured data module converts natural language AI output into a strict JSON schema (Date, Vendor, Amounts).
* **Persistence Tier:** The validated data is appended as a new record to a designated Google Sheets ledger.

## Workflow Visualization

### a. Receipt Submission
![00_Receipt_Tracker_GMail_Inbox_Receipts](Project%20Screen%20Shots/00_Receipt_Tracker_GMail_Inbox_Receipts.png)
*Uploaded the Image File by emailing as an attachment to a GMAIL Account, then forwarding to the Make.com MailWebHook for processing.*

### b. Make.com Processing
![01_Receipt_Tracker_Make_Com_Processing_Receipts](Project%20Screen%20Shots/01_Receipt_Tracker_Make_Com_Processing_Receipts.png)
*Displays the processing of the received Email Receipt Attachments within the Make.com environment.*

### c. Final Data in Google Sheets
![02_Receipt_Tracker_Google_Sheets_Added_Receipt_Values](Project%20Screen%20Shots/02_Receipt_Tracker_Google_Sheets_Added_Receipt_Values.png)
*Displays the OpenAI ChatGPT Extraction of Receipt Data into a Google Sheet.*

## Technology Stack
- **Make.com**: The primary automation platform used to connect different services.
- **OpenAI (GPT-4o)**: Used for both Vision-based OCR and transforming raw text into structured JSON data.
- **Google Sheets**: Acts as the final data destination for tracking and reporting.
- **Mailhooks**: Provides a unique email address to trigger the workflow.

## References
- [Make.com Documentation: Getting Started](https://www.make.com/en/help)
- [OpenAI API: Vision Guide](https://platform.openai.com/docs/guides/vision)
- [Google Sheets API Integration](https://www.make.com/en/help/apps/google-sheets)