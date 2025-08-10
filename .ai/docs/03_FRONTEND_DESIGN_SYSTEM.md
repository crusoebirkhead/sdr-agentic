Frontend Design System
This document provides the canonical design rules for all standard UI components, ensuring a consistent and high-quality user experience. All styles should be implemented using Tailwind CSS and ShadCN components where applicable.

1. Colors
   Background: slate-50 (Almost White)

Foreground/Text: slate-900 (Near Black)

Subtle Text/Borders: slate-400 (Gray)

Primary Accent: blue-600 (A professional, strong blue)

Primary Accent (Hover): blue-700

Success/Active: green-500

Error/Destructive: red-500

2. Typography
   Headers (h1, h2): Font: Montserrat, Weight: 700 (Bold)

Body Text: Font: Montserrat, Weight: 400 (Regular)

Data/Code: Font: Source Code Pro, Weight: 500 (Medium)

3. Core Components
   Button
   Primary Button (e.g., "Log In", "Connect")

Default: Background: blue-600, Text: white, Font: Montserrat, Rounded corners (rounded-lg).

Hover: Background: blue-700.

Disabled: Background: slate-200, Text: slate-500, Cursor: not-allowed.

Secondary/Outline Button (e.g., "Disconnect")

Default: Border: 1px solid slate-400, Text: slate-900, Background: transparent.

Hover: Background: slate-100.

Input Field (ShadCN)
Default: Border: 1px solid slate-400, Background: white, Rounded corners (rounded-lg).

Focus: Border color changes to blue-600, a subtle blue ring/shadow appears (ring-2 ring-blue-200).

Read-Only: Background: slate-100, Border: slate-300.

Card (e.g., Metric Cards, Config Cards)
Default: Background: white, Border: 1px solid slate-200, Rounded corners (rounded-xl), Soft shadow (shadow-md).

Padding: Generous internal padding (e.g., p-6).

Header: Montserrat, Bold, slate-900.

Content: Montserrat, Regular, slate-600.

Status Indicator
Active/Success: A small circle (w-2 h-2) with background green-500, next to the text "Active" in green-600.

Not Connected/Inactive: A small circle with background slate-400, next to the text "Not Connected" in slate-500.

4. Hero Image Concept
   Concept: To avoid generic stock photos, the login page or an empty dashboard state could feature a unique, abstract visual.

Description: A clean, minimalist 3D rendering of interconnected nodes and data streams, rendered in our primary color palette (shades of blue and gray). The visual should represent the flow of data being automated—from lead capture (a sphere) through processing nodes to an outcome (a calendar icon). The lighting should be soft and professional. This creates a unique brand asset that visually explains the product's purpose.
