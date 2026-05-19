# Service Issues and Maintenance Notices Tool

A GitHub Copilot skill that lets you add, update, and remove entries on the [CargoWise Service Issues & Maintenance Notices](https://myaccount.cargowise.com/Home/CargoWise/ServiceIssuesMaintenanceNotices.aspx) page — directly from VS Code chat, with no manual browser navigation needed.

---

## What It Does

The skill drives a browser session to manage notices on the CargoWise My Account portal. It handles the full workflow:

- **Add** a new Service Issue or Maintenance Notice (select product area, region, write the title)
- **Update** an existing notice with a new comment or status line
- **Remove** a notice once it is resolved

Before touching the browser, the skill walks you through a short question flow to collect everything it needs (notice type, product area, region, title, dates). 

You will need to log in to MyAccount yourself in the VS Code browser session that launches — credentials are never handled by the agent. Once logged in, the rest is automated.

---

## How It Works

1. You invoke the skill (see below) and describe what you want to do.
2. The skill asks a series of questions (notice type, product area, region, content).
3. It opens the CargoWise My Account portal in the integrated VS Code browser.
4. You log in manually in that browser window.
5. The skill clicks into Edit Mode, fills in the form, and confirms the change with a screenshot.

All changes are **live immediately** — there is no staging environment. The skill always takes a confirmation screenshot and will ask for explicit approval before removing a notice.

---

## Installation

### Option 1 — Clone into your workspace (recommended for teams)

```bash
git clone https://github.com/James-E70/Service-Issues-And-Maintenance-Notices-.git
```

Then open the cloned folder (or add it as a workspace folder) in VS Code. Copilot will automatically discover the skill from the `.github/skills/cargowise-notices/` path.

### Option 2 — Copy the skill folder into an existing workspace

Copy `.github/skills/cargowise-notices/` into the root of your existing VS Code workspace. The folder structure must be preserved:

```
your-workspace/
└── .github/
    └── skills/
        └── cargowise-notices/
            └── SKILL.md
```

### Requirements

- VS Code with the **GitHub Copilot Chat** extension (v0.22+)
- Agent mode enabled in Copilot Chat
- A CargoWise My Account login with permission to edit the Service Issues page

---

## Invoking the Skill

Open GitHub Copilot Chat in **Agent mode** and either:

- Type `/cargowise-notices` to invoke it directly as a slash command, and press Enter, or
- Describe your intent in natural language — Copilot will load the skill automatically when it detects relevant keywords:

> *"Add a new service issue for the UK Customs module"*  
> *"Update the existing maintenance notice for CargoWise Cloud"*  
> *"Remove the resolved service issue for Australia"*

---

## Skill File

The full procedure and question flow are defined in [.github/skills/cargowise-notices/SKILL.md](.github/skills/cargowise-notices/SKILL.md).
