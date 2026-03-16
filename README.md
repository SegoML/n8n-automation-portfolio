# n8n Automation Portfolio
### Masego Letsoko · Automation Developer & Systems Integrator

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Masego_Letsoko-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/masego-letsoko-6271a6171/)
[![Email](https://img.shields.io/badge/Email-masegoletsoko8@gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:masegoletsoko8@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-SegoML-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/SegoML)

---

## About This Repository

This portfolio documents end-to-end automation systems I've designed and built using **n8n**, **REST APIs**, **webhooks**, and cloud infrastructure. Each project solves a real business problem — connecting multiple platforms, eliminating manual processes, and building reliable, scalable workflows.

My background spans **legal tech**, **AI platforms**, and **sales & marketing operations**, with production automation systems running on AWS Lambda and n8n in live client environments.

---

## Projects

| # | Project | Stack | Problem Solved |
|---|---------|-------|----------------|
| 1 | [Automated Lead Enrichment & Sales Outreach Engine](#project-1) | `n8n` `Webhooks` `Hunter.io` `HubSpot` `Slack` | Automates lead qualification and CRM entry end-to-end |
| 2 | [Full-Stack Lead Capture App with AWS S3 Integration](#project-2) | `Next.js` `React` `AWS S3` `IAM` `n8n` `HubSpot` `Slack` | Captures leads + files, routes to CRM with zero manual handling |

---

## Project 1

### Automated Lead Enrichment & Sales Outreach Engine

**The Problem:** Sales teams waste hours manually researching leads, copying data between tools, and sending follow-up messages. This workflow eliminates all of it.

**How It Works:**

```
Webhook Trigger → Data Extraction → Hunter.io Email Enrichment
       ↓
Conditional Logic (qualify / disqualify)
       ↓
HubSpot CRM (create/update contact) → Slack Notification
```

**Workflow Steps:**

1. **Webhook Trigger** — Receives lead data from a web form or external source
2. **Data Transformation** — Cleans and structures the incoming payload using JavaScript
3. **Email Enrichment** — Queries the Hunter.io API to verify and enrich the lead's email and company data
4. **Lead Qualification** — Applies conditional logic to route qualified vs. unqualified leads down separate paths
5. **CRM Update** — Creates or updates the contact record in HubSpot with all enriched data
6. **Team Notification** — Sends a formatted Slack message to the sales channel with lead details and a direct CRM link

**Key Techniques:**
- REST API integration with authentication headers
- Webhook payload parsing and field mapping
- Conditional branching in n8n
- Error handling and fallback paths

---

## Project 2

### Full-Stack Lead Capture App with AWS S3 Integration

**The Problem:** Capturing leads who also need to submit project files (briefs, specs, documents) — while keeping cloud credentials secure and ensuring every submission lands in the CRM automatically.

**Architecture:**

```
Next.js Form (React)
       ↓
Next.js API Route (generates presigned S3 URL — keeps AWS keys server-side)
       ↓
AWS S3 (private bucket, IAM least-privilege policy)
       ↓
n8n Webhook (receives form data + S3 file reference)
       ↓
Hunter.io Enrichment → HubSpot Contact Created → Slack Alert
```

**Components:**

| Layer | Technology | Purpose |
|-------|-----------|---------|
| Frontend | Next.js / React | Custom lead capture form with file upload |
| Secure Upload | Next.js API Route + Presigned URL | Keeps AWS credentials server-side only |
| File Storage | AWS S3 + IAM | Private, secure document storage with least-privilege access |
| Automation | n8n | Orchestrates enrichment, CRM entry, and notifications |
| CRM | HubSpot | Contact creation with file reference attached |
| Notifications | Slack | Real-time sales team alerts |

**Security Practices Applied:**
- AWS IAM user scoped to a single S3 bucket with write-only permissions
- Presigned URLs expire after a short window — never expose AWS keys to the client
- Environment variables used throughout; no secrets in source code

**Source Code:** [`/app-source-code/n8n-lead-app`](./app-source-code/n8n-lead-app)

---

## Production Experience

Beyond these portfolio projects, I've built and currently maintain production automation systems for a US-based legal tech client:

- **Casey AI Intake Platform** — An event-driven automation architecture on AWS spanning five Lambda functions, integrating Amazon Lex, Bedrock, Polly, SES, DynamoDB, SmartAdvocate CRM, and DocuBee e-signature. Handles bilingual (English/Spanish) legal intake end-to-end with zero manual processing.
- **Conversion Tracking Pipeline** — Server-side event routing via Lambda to Google Ads and Meta Pixel, enabling accurate marketing attribution without client-side dependencies.

---

## Tech Stack

![n8n](https://img.shields.io/badge/n8n-EA4B71?style=flat-square&logo=n8n&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazon-aws&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=node.js&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![HubSpot](https://img.shields.io/badge/HubSpot-FF7A59?style=flat-square&logo=hubspot&logoColor=white)

**Automation & Integration:** n8n · AWS Lambda · Webhooks · REST APIs · OAuth  
**Languages:** JavaScript (Node.js) · Python · SQL  
**Cloud:** AWS (Lambda, S3, IAM, SES, DynamoDB, Lex, Bedrock, Polly)  
**CRM & MarTech:** HubSpot · SmartAdvocate · Meta Pixel · Google Ads  
**Frontend:** React · Next.js · Netlify  

---

## About Me

I'm a South Africa-based automation developer and systems integrator with a background in software engineering (ALX Africa), law (LLB, UNISA), and data science (DataCamp). I build automation systems that connect enterprise platforms, eliminate manual work, and scale operations — working remotely with clients across the US and Africa.

I also run **GVVA** ([gv-va.com](https://gv-va.com)), an automation studio offering AI integrations, workflow design, and custom software development.

**Open to:** Remote automation developer roles · Contract engagements · Integration projects

---

*📍 Johannesburg, South Africa · Available remotely (GMT+2)*
