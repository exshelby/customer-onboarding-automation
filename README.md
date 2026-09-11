# Automated AI Customer Onboarding Workflow (n8n + Notion + Gemini)

An automated customer onboarding pipeline built in n8n. The system captures new client intake submissions, generates a customized 3-step time-to-first-value (TTFV) onboarding checklist via Google Gemini, and synchronizes real-time client records into Notion.

## System Architecture
* **Trigger:** n8n Intake Form
* **Intelligence Layer:** Google Gemini (LLM Chain via Google AI Studio)
* **Operational Database:** Notion API (Relational CRM Table)

## Workflow Overview
1. **Intake:** The customer submits their name, work email, and company name via the onboarding form.
2. **Contextual Evaluation:** The Basic LLM Chain prompts Gemini to evaluate the customer's company and formulate tailored first-touch milestones.
3. **CRM Sync:** The page is created in Notion with status `Not Started`, assigned CSM, execution timestamp, and the tailored onboarding steps.

## Repository Contents
* `workflow-customer-onboarding.json`: Raw n8n export file (ready to import).

## How to Run Locally
1. Open n8n (`http://localhost:5678`).
2. Click the top-right `...` menu and select **Import from File**.
3. Choose `workflow-customer-onboarding.json`.
4. Connect your Google Gemini API key and Notion Integration credentials.
5. Set the workflow to **Published**.
