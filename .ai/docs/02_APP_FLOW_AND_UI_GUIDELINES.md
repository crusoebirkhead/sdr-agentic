App Flow and UI Guidelines
This document outlines the screen-by-screen user flow for the Inbound SDR Agent application, serving as a text-based wireframe for development.

1. Authentication Flow
   1.1. Login Page (US-001)

Objective: Allow a user to securely access their account.

Components:

Application Logo.

Header: "Welcome Back" or "Log in to your account".

Primary Action: "Sign in with Google" button. This should be the most prominent button on the page.

Secondary Action: A form with:

Email Input Field (placeholder: "you@company.com").

Password Input Field.

"Log In" button.

Footer links for "Forgot Password?" and "Don't have an account? Sign Up".

User Journey:

User lands on the page.

User clicks "Sign in with Google" to initiate the OAuth flow OR enters their email/password and clicks "Log In".

Upon successful authentication, the user is redirected to the main Dashboard.

2. Initial Setup & Configuration Flow
   2.1. Configuration Page (US-002, US-004)

Objective: Guide the user through the one-time setup required to make the agent functional. This page is likely the first thing a new user sees after signing up.

Layout: A single-column layout with distinct sections for each configuration step.

Section 1: Integrations (US-002)

Header: "Connect Your Accounts".

Component: An "Integrations" card.

Content: A row for "Google Account".

State (Not Connected): Shows "Not Connected" status text and a primary "Connect" button.

Action: Clicking "Connect" initiates the Google OAuth flow.

State (Connected): Shows a green "Active" status indicator and a secondary "Disconnect" button.

Section 2: Webhook URL (US-004)

Header: "Connect Your Website".

Component: A "Webhook URL" card.

Content:

Instructional text: "Add this webhook URL to your website's contact form to begin receiving leads."

A read-only input field displaying the unique URL for the user's account.

A "Copy to Clipboard" button next to the field.

Action: Clicking the button copies the URL and shows a success confirmation (e.g., toast notification).

3. Core Application Flow
   3.1. Main Dashboard (US-007)

Objective: Provide the user with a clear, at-a-glance view of the agent's performance and ROI.

Layout: Main content area with a primary navigation sidebar.

Navigation Sidebar:

Links to "Dashboard" and "Configuration".

User profile/logout section at the bottom.

Dashboard Content Area:

Header: "Dashboard".

Component 1: Date Range Filter

A dropdown or segmented control to filter analytics data.

Options: "Last 7 Days", "Last 30 Days".

Component 2: Analytics Grid

A 2x2 responsive grid displaying four key metrics.

Each grid item is a "Metric Card" with a title and a large numerical value.

Cards:

"Total Leads Processed"

"Average Response Time"

"Number of Meetings Booked"

"Reply Rate"
