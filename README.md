# Google Sheets MCP

A Google Sheets MCP that works as you. Let Claude, ChatGPT or any AI agent read tabs, write cells, clear ranges and add tabs in your own Chrome, with no Cloud project or OAuth setup.

- Product: Reduck MCP
- Updated: 2026-11-20

![One integration, every website](https://docs.reduck.ai/overview/one-integration-every-website.png)

[Reduck MCP](https://docs.reduck.ai) gives your agent reusable browser scripts for the sites that have no API. They run in your own Chrome, through the Reduck extension, where you are already signed in: no credentials exposed, and no bot detection.

**Get started:** [docs.reduck.ai](https://docs.reduck.ai)

## Overview

Reduck lets Claude and ChatGPT read and edit your Google Sheets as you, with no Google Cloud project.

Founders and sales teams keep their leads and pipelines in Google Sheets. Operations and finance people update a tracker or a report there every week. Many of them use an AI agent to find the leads or draft the report, and they want the agent to put the result in the sheet itself and keep it up to date. Without a connection to Google Sheets, the agent gives back text, and a person copies it into the sheet by hand.

## Why it's hard

Every usual route to a Google Sheets MCP starts in Google Cloud. Google's own Sheets MCP server is in Developer Preview and needs a Cloud project, two APIs, an OAuth consent screen and a client ID. Open-source servers ask for the same OAuth credentials or a service account. Hosted connector platforms skip that setup by holding the OAuth tokens for you, so your access to the sheet runs through their service. Apps Script web apps work, but you write and deploy the script yourself.

## How Reduck does it

Reduck is an MCP server whose Google Sheets scripts run in your own Chrome, where you are already signed in to Google. Your agent works on exactly the sheets you can open, as you, and sees the same thing you see. There is no Cloud project, no OAuth app and no token held by anyone else. A write answers only once Google has saved it, and when the sheet refuses a value the run stops with the sheet's own message.

## What your agent does

- Read a whole tab as rows and columns
- Write a block of values from any cell, with formulas and number parsing like typing
- Clear a range, keeping the formatting
- List the tabs of a spreadsheet, add, rename or delete one
- Create a new spreadsheet, rename it, or export it as xlsx, csv, pdf and more

## Ways to give an AI agent your Google Sheets

| | Google's Sheets MCP | Hosted connector (Composio, StackOne) | Apps Script web app | Reduck |
|---|---|---|---|---|
| Google Cloud project | Yes | No | No | No |
| OAuth app or service account | Yes | Managed for you | No | No |
| Who holds the access | You | The platform | Your script | You, in your browser |
| Writes cells | Yes | Yes | What you code | Yes |
| Keeps your dropdown rules | Not documented | Not documented | What you code | Yes, refused values stop the run |
| Status | Developer Preview | Generally available | Your own code | Generally available |

## Who it's for

- Founders and sales teams who keep leads and pipelines in Google Sheets
- Operations and finance people who update a tracker or a report every week
- Developers who want an agent to write to a sheet without a Cloud project

## FAQ

### Is there an official Google Sheets MCP server?

Yes. Google offers a remote Sheets MCP server in Developer Preview. It needs a Google Cloud project, the Sheets and Sheets MCP APIs turned on, an OAuth consent screen and a client ID. Reduck needs none of that, because its Sheets scripts run in your own signed-in Chrome.

### Do I need a Google Cloud project, an OAuth app or a service account?

No. There is nothing to create in Google Cloud and no key to store. You stay signed in to Google in Chrome, and the Reduck extension runs each script there, as you.

### Can the agent write, or only read?

Both. It reads a tab, writes a block of cells, clears a range, adds, renames and deletes tabs, creates a spreadsheet and exports one. Reading changes nothing; every script that changes the sheet is marked as a write, so your agent can ask you first.

### Does it respect my dropdowns and data validation?

Yes. A value is entered the way you would type it, so the sheet's own rules apply. A value a dropdown does not allow is refused, the run stops and reports the sheet's own message, and the dropdown stays in place.

### How are values written?

Like the Sheets API's values.update with user-entered input. A missing value leaves the cell as it is, an empty one clears it, and anything else is parsed as if typed, so "=SUM(A1:A3)" becomes a formula and a number becomes a number. Start a value with an apostrophe to keep it as text.

### Does it work with ChatGPT, Claude and Cursor?

Yes. Reduck connects to ChatGPT, Claude, Claude Code, Codex, Cursor and any other MCP client, and to a terminal through the Reduck CLI. You ask in plain words and the agent picks the Sheets scripts it needs.

### Claude can already edit Google Sheets. Why use this?

Claude's own Google Workspace connector edits Sheets inside Claude. Reduck's scripts are the same wherever you call them from, ChatGPT, Codex, Cursor, a CLI or your own agent, and they combine with scripts for other sites, such as reading leads from LinkedIn and writing them to a sheet in one run.

### Is it as fast as the API?

No. The scripts use the Sheets editor like a person would, so a block of a few rows takes several seconds rather than milliseconds. For bulk jobs of thousands of rows a service account with the Sheets API is faster; for an agent that updates a sheet as part of its work, this is set up in a minute.

Source: https://reduck.ai/use-cases/google-sheets-mcp
