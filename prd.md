Product Requirements Document: The Inbound SDR Agent (MVP)
Overview
This document outlines the product requirements for the Minimum Viable Product (MVP) of the Inbound SDR Agent. This system is designed to solve a critical business problem: high-intent inbound leads generated from a company's website often go cold due to slow and impersonal follow-up processes.

The Inbound SDR Agent is an autonomous system that instantly engages, enriches, personalizes, and manages conversations with these leads by leveraging a pre-built n8n automation workflow. The purpose of this MVP is to provide a simple front-end interface for users to configure the necessary credentials and monitor the performance of this automation.

Goals and objectives
Goal
To validate the core value proposition of increasing lead conversion by providing a simple, configurable interface for the autonomous Inbound SDR Agent automation.

Objectives
O-1: Reduce Lead Response Time: Decrease the average response time for a new inbound web lead from the industry standard of hours to under five minutes.

O-2: Increase Meeting Conversion: Increase the meeting booking rate from qualified inbound leads by 40% within the first quarter of implementation.

O-3: Improve Sales Efficiency: Reduce the time SDRs spend on manual lead research and initial follow-up by at least 50%.

O-4: Launch Quickly: Deliver a functional and secure MVP front-end for configuration and monitoring within one development cycle.

Scope
In scope for V1
Configuration Front-End: A simple web interface for users to set up and manage the automation.

Secure Credential Management: The ability for users to securely connect their Google accounts (via OAuth) and input necessary API keys (e.g., OpenAI).

Webhook Display: The front-end will display the unique webhook URL that users must add to their website's contact form to trigger the automation.

Fully Autonomous Engagement: All lead enrichment, personalization, and conversation management will be handled by the n8n automation without any human review steps within the application.

Basic Analytics Dashboard: A dashboard displaying core success metrics sourced from the automation's outputs.

Out of scope for V1
Human-in-the-Loop Features: There will be no interface for reviewing, editing, or approving AI-generated messages. The system is fully autonomous.

Proactive Engagement: The system will not engage users based on website behavior. It will only act on explicit form submissions.

Multi-Channel Support: V1 is limited to email conversations only.

Advanced CRM Integration: No deep, bi-directional CRM sync.

Advanced Workflow Customization: Users will not be able to edit the n8n automation logic from the front-end.

User personas
Maria, the marketing manager
Role: Head of Marketing at a B2B SaaS company.

Goal: To maximize the ROI from her marketing campaigns and deliver a high volume of qualified leads to the sales team.

Pain Points: She spends a significant budget to generate leads but feels many are wasted because of a leaky funnel and slow sales follow-up.

Needs: A "set it and forget it" system that ensures every lead is engaged effectively. She requires a clear dashboard with metrics to prove the system's impact.

Sam, the sales development representative (SDR)
Role: SDR responsible for qualifying inbound leads and booking meetings.

Goal: To meet or exceed his monthly quota for qualified meetings booked.

Pain Points: The repetitive, time-consuming nature of researching each lead and crafting a first email.

Needs: A tool that works in the background to warm up leads and book meetings directly on his calendar, allowing him to focus his time on already-scheduled calls with engaged prospects.

Functional requirements
User stories and acceptance criteria
Requirement ID User Story Acceptance Criteria
Authentication & Setup
US-001 As an Admin (Maria), I want to log in to the system dashboard securely so that I can manage configurations and view data without unauthorized access. - The system provides a login page with username and password fields.

- Authentication is successful with valid credentials.
- An error message is displayed for invalid credentials.
- All user session data is handled securely.
  US-002 As an Admin (Maria), I want to connect my Gmail and Google Calendar accounts via OAuth so that the agent can send emails and book meetings on my team's behalf. - The UI provides a clear button to initiate Google OAuth.
- After successful authentication, the connection status is displayed as "Active."
- The system securely stores and refreshes the necessary authentication tokens for the n8n backend.
  US-004 As an Admin (Maria), I want to be shown the unique webhook URL for my account so I can configure my website's contact form to trigger the automation. - The dashboard prominently displays a unique, copyable webhook URL.
- A "Copy to Clipboard" button is provided.
  Lead Processing & Engagement (Handled by n8n)
  US-005 As the System, when a new lead is received from the webhook, I want to trigger the enrichment and personalization process automatically so the lead receives a timely, relevant response. - The n8n workflow correctly parses all lead data from the webhook payload.
- The enrichment and email generation sequence is initiated within 60 seconds.
- If the webhook payload is malformed, the n8n workflow logs an error.
  US-006 As the System, when a lead replies to an email, I want to use the pre-defined n8n logic to classify their intent and trigger the appropriate automated response or action. - The n8n workflow accurately classifies replies into categories: "Pricing," "Use Case Question," "Meeting Request," etc.
- The correct automated response is sent, or the meeting booking process is initiated, based on the classification.
  Analytics
  US-007 As a Manager (Maria), I want to view a dashboard with key performance metrics so I can understand the system's ROI. - The dashboard displays: Total Leads Processed, Average Response Time, Number of Meetings Booked, and Reply Rate.
- Data can be filtered by date range (e.g., Last 7 Days, Last 30 Days).

Export to Sheets
Non-functional requirements
Performance: The front-end application must load in under 3 seconds. The underlying n8n automation must process and respond to leads in under 5 minutes.

Reliability: The front-end must maintain a 99.9% uptime. The system's effectiveness is dependent on the uptime of the n8n instance and its third-party APIs.

Security: All sensitive data, including API keys and lead information, must be encrypted both at rest and in transit. Access to the system dashboard must be protected by authentication.

Usability: The front-end interface must be simple and intuitive, allowing a non-technical user (like Maria) to complete the entire setup process in under 15 minutes.

Assumptions and constraints
Assumptions
Customers will have a website with a form that can be configured to send data to a webhook.

Customers will have the necessary permissions and ability to provide API keys and grant OAuth access for required services (Google Suite, LLM provider, etc.).

The primary language for lead communication will be English for the MVP.

Constraints
The system's logic is entirely dependent on the pre-built n8n workflows. Any changes to the core logic require editing the n8n automation directly, not through the front-end.

The system's performance and data accuracy are dependent on the reliability, speed, and terms of service of third-party APIs.

The initial release is constrained to email as the sole communication channel.

Success metrics
Primary Metric:

Meetings Booked Rate: The percentage of new inbound leads that result in a qualified meeting booked by the agent. (Target: Achieve a rate of 25% or higher).

Secondary Metrics:

Average Lead Response Time: The time from webhook submission to the initial email being sent. (Target: < 5 minutes).

Setup Completion Rate: The percentage of new users who successfully complete the setup process (connecting accounts and API keys). (Target: > 90%).
