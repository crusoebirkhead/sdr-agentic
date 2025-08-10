I need a web application with a secure dashboard. The frontend will use React with Vite, authentication will be handled by Supabase, and styling will use Tailwind CSS with ShadCN components. The main features are: 1. A configuration page for users to input API keys and connect their Google account. 2. A dashboard to display basic analytics on lead engagement. 3. A display for a unique webhook URL for the user to copy. Start by creating a detailed, step-by-step implementation plan and save it as PLAN.md for our future reference.

PROMPT-001 (Ref: US-001)
Context
This prompt is for building the user authentication entry point, as defined in user story US-001. The design should be clean and minimalist, inspired by the

login.png mood board image.

Task
Create the main login page component.

Guidelines
Use React, Vite, and Tailwind CSS.

The page must have a clean, centered layout with significant white space.

The typography must follow the design system: Montserrat for all UI text.

Prominently display a "Sign up with Google" button as the primary call to action.

Below the Google button, include a standard form with 'Email' and 'Password' fields using ShadCN input components.

Include a primary 'Log In' button (as defined in 03_FRONTEND_DESIGN_SYSTEM.md) for the form submission.

Constraints
Do not implement the authentication logic with Supabase in this step; this is a UI-only task.

The email/password 'Log In' button should be disabled until both fields are populated.

PROMPT-002 (Ref: US-002)
Context
This prompt is for creating the UI to connect a user's Google account on the Configuration page, as per user story US-002. The component should be clean and clear, similar to the

settings.jpg and user-profile.png mood board images.

Task
Create the "Integrations" component to be placed on the main Configuration page.

Guidelines
The component should be a distinct card, styled according to 03_FRONTEND_DESIGN_SYSTEM.md.

The card should have a title: "Integrations".

Inside the card, display a row for "Google Account". This row should contain the Google logo, the text "Google Account", a status indicator, and a button.

When not connected, the status indicator should read "Not Connected" and the button should be a primary style that says "Connect".

When connected (controlled by a prop), the status indicator should show a green icon and the text "Active". The button should change to a secondary or outline style and say "Disconnect".

Constraints
This is a UI-only task. Do not implement the Google OAuth flow logic.

The connection status must be controlled via a component prop (e.g., isConnected).

PROMPT-003 (Ref: US-004)
Context
This prompt is for creating the component to display the unique webhook URL to the user on the Configuration page, as specified in US-004.

Task
Build the "Webhook URL" display component.

Guidelines
Create a card component styled according to 03_FRONTEND_DESIGN_SYSTEM.md.

The card title should be "Your Inbound Webhook URL".

Use a read-only ShadCN input field to display the URL. The font for the URL itself must be Source Code Pro.

Place a "Copy to Clipboard" button, including an icon, next to the input field.

When the button is clicked, the URL should be copied to the user's clipboard, and a temporary success message (e.g., a toast notification saying "Copied!") should appear.

Constraints
The webhook URL will be passed into the component as a prop. Do not generate or hardcode the URL in this component.

PROMPT-004 (Ref: US-007)
Context
This prompt is for building the main analytics dashboard UI to display key performance metrics, as per US-007. The design should feature clean, clear data cards inspired by the

SaaS.jpg mood board image.

Task
Build the main analytics dashboard page component.

Guidelines
The page should have a main header: "Dashboard", using Montserrat font.

At the top of the page, include a date range filter using a ShadCN Select or a similar component. Options should include "Last 7 Days" and "Last 30 Days".

Below the filter, create a responsive grid (e.g., 2x2 on desktop, single column on mobile).

The grid will contain four metric cards, each styled according to 03_FRONTEND_DESIGN_SYSTEM.md.

Each card must have a title and a large, bold metric value. The four cards are:

"Total Leads Processed"

"Average Response Time"

"Number of Meetings Booked"

"Reply Rate"

Constraints
This is a UI-only task. The data for the metric cards will be passed in via props. Do not implement any data-fetching logic.
