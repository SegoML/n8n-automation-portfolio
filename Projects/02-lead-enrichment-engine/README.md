# Project 2: Full-Stack Lead Capture & AI Classification System

This project is a complete, end-to-end solution for capturing, qualifying, and processing new business leads. It features a custom-built web application (Next.js/React), secure cloud file storage (AWS S3), and a powerful back-end automation workflow (n8n) enhanced with AI-driven intent analysis (Google Gemini).

It solves a critical business problem by automating the entire lifecycle of a new lead—from initial contact on a web form to a fully enriched, analyzed, and actioned record in a CRM, complete with associated project files. This system transforms a slow, manual 15-minute task into an intelligent, 5-second automated process.

---

### **Live System in Action**

The workflow is a seamless, multi-stage process that demonstrates a full range of technical capabilities:

1.  **The Custom Web Form:** A user fills out their details and uploads a project brief document via a clean, professional web interface.
    ![The Next.js Front-End Form](assets/app-form-success.png)

2.  **Secure Cloud Storage:** The user's document is securely uploaded to a private AWS S3 bucket, accessible only via authenticated requests.
    ![File in AWS S3](assets/s3-upload-success.png)

3.  **Intelligent, Real-Time Notification:** An alert is instantly sent to the sales team's Slack channel. This message is enriched with company data and, crucially, an **AI-assessed intent classification** to help the team prioritize their outreach.
    ![Slack Notification with AI Intent](assets/slack-notification-success.png)

4.  **Permanent CRM Record:** A new, detailed contact is automatically created in HubSpot. This record includes all the lead's information and a permanent link to their project brief stored in S3.
    ![HubSpot Contact Created](assets/hubspot-contact-success.png)

---

### **Technical Architecture**

This project demonstrates a multi-faceted skill set across front-end development, secure cloud infrastructure, and intelligent back-end automation.

![Architecture Diagram](assets/architecture-diagram.png) *(Optional: You can create this diagram using a tool like diagrams.net)*

1.  **Front-End Application (`Next.js / React`):** A custom-built, user-facing web application for lead submission and file uploads.
2.  **Secure API Endpoint (`Next.js API Route`):** A server-side function that acts as a secure bridge to AWS. It generates short-lived, "presigned" URLs for file uploads, ensuring AWS secret keys are never exposed to the client-side browser.
3.  **Cloud File Storage (`AWS S3`):** A **private and secure** S3 bucket configured to store all user-submitted documents.
4.  **Identity & Access Management (`AWS IAM`):** A dedicated IAM user with a meticulously crafted, **least-privilege policy**. This policy grants it the absolute minimum permissions required: `s3:PutObject` for the web app to upload files, and `s3:GetObject`, `s3:ListBucket`, and `s3:GetBucketLocation` for the n8n workflow to securely download them.
5.  **Automation Engine (`n8n`):** A robust, logically ordered workflow that:
    *   Receives data from the front-end via a webhook.
    *   **Qualifies the lead** using an `IF` node to check for a business email (via Hunter.io API enrichment), preventing wasted resources on unqualified leads.
    *   **Securely downloads** the associated project file from the private S3 bucket using the official AWS S3 node and authenticated credentials.
    *   **Analyzes the document's content using the Google Gemini API** to perform an "intent classification," labeling the lead as High, Medium, or Low intent.
    *   Sends a comprehensive, multi-source notification to Slack.
    *   Creates and updates contact records in the HubSpot CRM.

---

### **Overcoming Challenges & Key Learnings**

This project was a deep dive into real-world development and debugging. Key challenges that were overcome include:
*   **Solving React Hydration Errors:** Debugged and resolved client-side mismatches caused by browser extensions and antivirus software by implementing the `suppressHydrationWarning` prop correctly.
*   **Debugging API Routing:** Troubleshooted and fixed `404 Not Found` and `405 Method Not Allowed` errors by correcting the Next.js API route file structure and implementing a CORS preflight handler.
*   **Mastering IAM Policies:** Methodically debugged a series of `403 Forbidden / Access Denied` errors from AWS by building a precise, least-privilege IAM policy, learning the distinction between permissions on buckets versus objects (`s3:ListBucket` vs. `s3:GetObject`).
*   **Correcting API Data Structures:** Resolved API errors from Google Gemini by adding a data transformation step (`Extract from File`) to ensure the payload matched the expected format.

---

### **Source Code & Setup**

*   **Application Source Code:** The full source code for the Next.js application can be found in the [`/app-source-code`](./app-source-code) directory.
*   **n8n Workflow:** The automation workflow can be downloaded from [`/workflow.json`](./workflow.json).

To run this project, you would need to set up the AWS S3 bucket and IAM user, configure the n8n workflow with your own API credentials, and set up the Next.js application with an `.env.local` file.
