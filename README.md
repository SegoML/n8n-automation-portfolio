# My n8n Automation Portfolio

Hello! I'm Masego, an AI and & ML enthusiast commited to building AI Automated Systems and has a passion for building efficient solutions and automating complex processes.

This repository serves as a portfolio of my work, demonstrating skills in front-end development (React/Next.js), cloud infrastructure (AWS), API integration, and back-end automation with n8n.

---

## Projects

Here is a list of the projects I have built and documented.

| # | Project Name                                                              | Technologies Used                                               |
|---|---------------------------------------------------------------------------|-----------------------------------------------------------------|
| 1 | [Automated Lead Enrichment & Sales Outreach Engine](./projects/01-lead-enrichment-engine) | `n8n`, `Webhook`, `Hunter.io API`, `Slack`, `HubSpot`             |
| 2 | [**Full-Stack Lead Capture App with AWS S3 Integration**](./projects/02-fullstack-lead-capture-app) | `Next.js`, `React`, `AWS S3`, `IAM`, `n8n`, `Slack`, `HubSpot` |


---

## About Me & Contact

I am always looking for new challenges and opportunities to apply my automation and development skills.

*   **LinkedIn:** [Your LinkedIn Profile URL]
*   **Medium:** [Your Medium Profile URL]
Use code with caution.
Markdown
Part 2: Documenting "Project 2" - The README.md
This is the most important part. We need to create a detailed, professional README for this specific project.
Inside the 02-fullstack-lead-capture-app folder, create a new file named README.md.
Paste the following template into this new file. This template is designed to impress.
Generated markdown
# Project 2: Full-Stack Lead Capture & Processing System

This project is a complete, end-to-end solution for capturing and processing new business leads. It features a custom-built web application, secure cloud file storage with AWS S3, and a powerful back-end automation workflow built with n8n.

It solves a critical business problem by automating the entire lifecycle of a new lead—from initial contact on a web form to a fully enriched and actioned record in a CRM, complete with associated project files.

---

### **Live System in Action**

1.  **The Custom Web Form:** A user fills out their details and uploads a project brief.
    ![The Next.js Front-End Form](assets/app-form-success.png)

2.  **Secure File Upload:** The uploaded file is stored securely in a private AWS S3 bucket.
    ![File in AWS S3](assets/s3-upload-success.png)

3.  **Real-Time Sales Notification:** A detailed alert, including a link to the project brief, is instantly sent to the sales team on Slack.
    ![Slack Notification](assets/slack-notification-success.png)

4.  **CRM Record Creation:** A new contact is automatically created in HubSpot with all the enriched data and a link to their project file.
    ![HubSpot Contact Created](assets/hubspot-contact-success.png)

---

### **Technical Architecture**

This project demonstrates a multi-faceted skill set across front-end development, cloud infrastructure, and back-end automation.

![Architecture Diagram](assets/architecture-diagram.png) *(You can create this diagram using a tool like diagrams.net)*

1.  **Front-End Application (`Next.js / React`):** A custom-built, user-facing web form for lead submission and file uploads.
2.  **Secure API Endpoint (`Next.js API Route`):** A server-side function that acts as a secure bridge to AWS. It generates short-lived, "presigned" URLs for file uploads, ensuring AWS secret keys are never exposed to the client-side.
3.  **Cloud File Storage (`AWS S3`):** A private, secure S3 bucket to store all user-submitted documents.
4.  **Identity & Access Management (`AWS IAM`):** A dedicated IAM user with a least-privilege policy, granting it permission *only* to upload files to the specific S3 bucket.
5.  **Automation Engine (`n8n`):** A robust workflow that:
    *   Receives data from the front-end via a webhook.
    *   Enriches the lead's email using the Hunter.io API.
    *   Qualifies the lead using conditional logic.
    *   Sends notifications to Slack.
    *   Creates and updates records in the HubSpot CRM.

---

### **Source Code & Setup**

*   **Application Source Code:** The full source code for the Next.js application can be found in the [`/app-source-code`](./app-source-code) directory.
*   **n8n Workflow:** The automation workflow can be downloaded from [`/workflow.json`](./workflow.json).

To run this project, you would need to:
1.  Set up the AWS S3 bucket and IAM user.
2.  Configure the n8n workflow with your own credentials for Hunter, Slack, and HubSpot.
3.  Set up the Next.js application locally, providing your AWS and n8n details in an `.env.local` file.

Detailed setup instructions are beyond the scope of this README but follow standard deployment procedures for these technologies.