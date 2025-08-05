### Document Purpose

This document provides a screen-by-screen user journey for the core features defined in the 01_PRODUCT_REQUIREMENTS.md. It specifies the components, data, and user actions on each screen to ensure a shared understanding of the intended user experience.

### User Journey 1: First-Time User Onboarding & Setup

This journey describes the critical path for a new user, "Maria," from her first login to successfully configuring the agent.

Screen 1.1: Login Page
User Story Ref: US-001

Description: The entry point for any user trying to access the application.

Components:

App Logo: Centered at the top.

Page Header (h1): "Log In to Your Agent Dashboard"

Form Container: A card-style container for the form fields.

Email Input:

Label: "Email Address"

Placeholder: "you@company.com"

Data: User's email address.

Password Input:

Label: "Password"

Placeholder: "••••••••••"

Data: User's password.

Primary Button:

Label: "Log In"

State: Disabled until both email and password fields are validly populated.

Actions:

User enters their credentials.

User clicks "Log In," which triggers the authentication process. Upon success, they are redirected to Screen 1.2.

Screen 1.2: Initial Setup / Welcome Screen
User Story Ref: Implied need post-login for a new user.

Description: A simple, welcoming interstitial screen that orients a new user and guides them into the mandatory setup process.

Components:

Welcome Header (h1): "Welcome, Maria!"

Instructional Text (p): "Let's get your Inbound SDR Agent configured. You'll need to connect your Google account and provide a few API keys to get started."

Primary Button:

Label: "Start Setup"

Actions:

User clicks "Start Setup," which navigates them directly to the Settings page (Screen 1.3).

Screen 1.3: Settings Page - Integrations
User Story Ref: US-002, US-003

Description: The core configuration screen where the user connects all necessary third-party services. This screen is accessed via a "Settings" link in the persistent left-hand navigation.

Components:

Page Header (h1): "Settings"

Section Header (h2): "Integrations"

Google Account Card:

Icon: Google logo.

Label: "Google Account"

Description: "Connect your Gmail and Google Calendar to allow the agent to send emails and book meetings on your behalf."

Status Indicator: Text label. Default state: "Not Connected." Success state: "Connected" (in green).

Button:

Default state: Primary button with label "Connect".

Success state: Secondary/Destructive button with label "Disconnect".

API Keys Card:

Icon: Key icon.

Label: "API Keys"

Description: "Provide API keys from the following services to enable lead enrichment and AI personalization."

OpenAI API Key Input:

Label: "OpenAI API Key"

Input Type: Password (to mask the key).

Helper Text: "Find your key in your OpenAI account settings."

Apify API Key Input:

Label: "Apify API Key"

Input Type: Password.

Helper Text: "Find your key in your Apify account console."

Primary Button:

Label: "Save API Keys"

Actions:

User clicks the "Connect" button for Google, which initiates the Google OAuth flow in a new window/tab. Upon successful return, the UI updates to the "Connected" state.

User pastes their API keys into the respective input fields.

User clicks "Save API Keys." The system validates and saves the keys. A success toast notification appears. If a key is invalid, the corresponding input field gets a red border and an error message appears below it.

User Journey 2: Viewing the Dashboard & Monitoring Performance
This journey describes the primary interaction for a returning user who has completed the setup.

Screen 2.1: Dashboard - Empty State
User Story Ref: US-004, US-007

Description: The screen a user sees after setup is complete but before the first lead has been processed by the automation. The goal is to provide the user with the next crucial step.

Components:

Page Header (h1): "Dashboard"

Webhook URL Card:

Header (h2): "Your Inbound Webhook URL"

Instructional Text (p): "This is the final step. Copy this unique URL and paste it into your website's contact form settings to begin receiving leads."

Read-only Input Field: Displays the full webhook URL.

Icon Button: A "Copy" icon that, on click, copies the URL to the user's clipboard and shows a temporary "Copied!" confirmation message.

Analytics Section:

Header (h2): "Analytics"

Empty State Message: A container with an icon and text: "No data to display yet. Once your first lead is processed via the webhook, your metrics will appear here."

Actions:

User clicks the "Copy" icon to get their webhook URL.

Screen 2.2: Dashboard - Active State
User Story Ref: US-004, US-007

Description: The main dashboard view once the system is active and processing leads. It provides at-a-glance metrics on performance.

Components:

Page Header (h1): "Dashboard"

Webhook URL Card: This card persists on the dashboard for easy reference.

Analytics Section:

Header (h2): "Analytics"

Date Range Filter: A dropdown allowing the user to select a time period (e.g., Last 7 Days, Last 30 Days, Quarter to Date).

Metric Card Grid: A responsive grid containing four distinct cards:

Total Leads Processed: Title and a large numeric value.

Average Response Time: Title and a value (e.g., "4m 15s").

Meetings Booked: Title and a large numeric value.

Reply Rate: Title and a percentage value (e.g., "28%").

Actions:

User selects a different date range from the filter, which re-fetches and updates the data in the metric cards.
