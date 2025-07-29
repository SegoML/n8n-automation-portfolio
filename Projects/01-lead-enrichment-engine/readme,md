# Project 1: Automated Lead Enrichment & Sales Outreach Engine

This workflow automates the entire process of qualifying, enriching, and actioning new sales leads in real-time, turning a 15-minute manual task into a 5-second automated process.



### The Business Problem
When a new lead signs up via a website form, sales teams spend significant manual effort researching the lead to see if they're a good fit. They look up the company, find its size and industry, and then manually enter this data into a CRM before sending the first notification. This delay can lead to lost opportunities and wastes valuable sales time.

### The Automated Solution
This n8n workflow instantly captures new leads from a webhook, enriches them with company data using the Hunter.io API, qualifies them based on business rules, and then simultaneously notifies the sales team on Slack and creates a perfectly detailed contact in HubSpot.


### Technologies Used
*   **n8n:** The core automation platform.
*   **Webhook:** To capture incoming lead data in real-time.
*   **Hunter.io API:** To enrich a lead's email with company data (name, domain, etc.).
*   **IF Node:** To apply conditional logic and qualify leads.
*   **Slack:** To send instant notifications to the sales team.
*   **HubSpot:** To create and update contact records in the CRM.

---

### Key Results & Business Impact
*   **Productivity:** Saves an estimated 10-15 minutes of manual research and data entry *per lead*.
*   **Speed-to-Lead:** Reduces lead response time from hours to seconds, dramatically increasing the chances of engaging a prospect.
*   **Data Quality:** Ensures the CRM is populated with consistent, accurate, and rich data.
*   **Focus:** Allows the sales team to focus only on pre-qualified leads.

---

### How to Use This Workflow
1.  Download the `workflow.json` file from this folder.
2.  In your n8n instance, select "Import from File" and choose the downloaded file.
3.  You will need to create your own credentials for Hunter.io, Slack, and HubSpot and re-connect them in the respective nodes.
4.  Activate the workflow.