---
name: cargowise-notices
description: 'Manage CargoWise Service Issues and Maintenance Notices. Use when adding a new service issue or maintenance notice, editing or updating an existing notice, or removing a notice from the CargoWise My Account portal at myaccount.cargowise.com/Home/CargoWise/ServiceIssuesMaintenanceNotices.aspx. Handles the full browser-driven workflow including login, edit mode, form completion, and confirmation.'
argument-hint: 'add notice | update notice | remove notice'
---

# CargoWise Service Issues & Maintenance Notices

## Overview

This skill manages entries on the CargoWise Service Issues and Maintenance Notices page:
`https://myaccount.cargowise.com/Home/CargoWise/ServiceIssuesMaintenanceNotices.aspx`

Edits are **live immediately** and visible to all CargoWise clients. Confirm every destructive action before executing.

---

## When to Use

- Adding a new Service Issue or Maintenance Notice
- Adding an update/comment to an existing notice
- Removing an existing notice

---

## Question Flow (Run Before Any Action)

Before touching the browser, collect answers to the following. Ask all questions upfront in a single prompt where possible.

### 1. Action Type
> "What would you like to do?"
- Add a new notice
- Add an update to an existing notice
- Remove an existing notice

### 2. Notice Type (for Add / Update / Remove)
> "Is this a **Service Issue** or a **Maintenance Notice**?"
- **Service Issue** — an unplanned outage, degraded functionality, or ongoing problem
- **Maintenance Notice** — a planned maintenance window or scheduled downtime

### 3. Product Area
> "Which product area does this relate to?"

Common areas (select or type):
- CargoWise Cloud
- Customs
- Forwarding
- Accounting / Finance
- Warehousing
- Portal / eCommerce
- eAdaptor / EDI
- Reporting
- Other (specify)

### 4. Region / Country
> "Which region or country does this affect?"

Examples: Global, Australia, United Kingdom, United States, Europe, Singapore, etc.

### 5. Notice Title / Description (Add only)
> "What is the title/heading for the notice?"

Keep it concise and factual. Example: *"CargoWise Cloud – Degraded Performance Impacting AU Region"*

### 6. Maintenance Dates (Maintenance Notice – Add only)
> "What are the planned maintenance start and end date/time (include timezone)?"

Example: *"Saturday 24 May 2026, 10:00 PM – 2:00 AM AEST"*

### 7. Update Text (Update only)
> "What is the update message to add to the existing notice?"

### 8. Identify the Notice (Update / Remove only)
> "Can you confirm the exact notice title and/or region so I can locate it on the page?"

---

## Procedure

### Step 1 — Navigate to the Page

Open the browser and navigate to:
```
https://myaccount.cargowise.com/Home/CargoWise/ServiceIssuesMaintenanceNotices.aspx
```

Take a screenshot to confirm the page has loaded.

### Step 2 — Log In

If the login page appears:
- Ask the user to enter their credentials directly in the browser window.
- **Never ask for or handle passwords via chat.**
- Wait for the user to confirm they are logged in before proceeding.

### Step 3 — Enter Edit Mode

Click the **"Enter Edit Mode"** link on the page. Take a screenshot to confirm the edit form is visible.

### Step 4A — Add a New Notice

1. From the **Location / Region dropdown**, select the applicable country or region.
2. In the **Issue Title** field, type the notice title. For Maintenance Notices, include the dates in the title or body as agreed in the question flow.
3. Click **"Add new issue"**.
4. Wait for the page to return to `?mode=view`.
5. Take a screenshot to confirm the notice appears under the correct product area and region.

### Step 4B — Add an Update to an Existing Notice

1. In edit mode, scroll to the target notice (identified by title and region from the question flow).
2. Locate the **"Add Update"** textbox below the notice.
3. Type the update text exactly as provided.
4. Submit the update (click the associated submit/add button).
5. Take a screenshot to confirm the update timestamp and text appear correctly.

### Step 4C — Remove a Notice

1. In edit mode, scroll to the target notice (identified by title and region from the question flow).
2. Click the **"Remove Issue"** button for that notice.
3. Confirm the action when prompted.
4. Take a screenshot to confirm the notice no longer appears on the page.

---

## Safety Rules

- Always take a **before** screenshot when removing or modifying an existing notice.
- Always take an **after** screenshot to confirm the change is live.
- Never remove a notice without explicit user confirmation at the time of removal.
- If unsure which notice matches, show a screenshot and ask the user to confirm before acting.
- Changes are **immediately live** — there is no staging or undo button.

---

## Confirmation Message

After completing any action, report back with:
1. What was done (action, notice title, region)
2. Whether a screenshot confirms the change is live
3. Any warnings or anomalies observed
