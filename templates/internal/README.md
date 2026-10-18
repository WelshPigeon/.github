<!--
TEMPLATE: Pigeon Studios internal project README (Discord bots, services, website, tools).
Replace every placeholder in double curly braces, delete sections that don't apply, and delete this comment.
-->

# {{PROJECT_NAME}}

> **Private and confidential.** Pigeon Studios internal project. See [LICENSE.md](LICENSE.md).

{{SHORT_DESCRIPTION}}

| | |
|---|---|
| **Status** | Live / In development / Retired |
| **Owner** | @WelshPigeon |
| **Runs on** | {{HOST}} <!-- e.g. GravelHost, Render, Hostinger --> |
| **Deploys** | Automatically from `main` via {{CI}} <!-- GitHub Actions / GitLab CI --> |
| **Used by** | {{WHO}} <!-- e.g. LSPD Discord, Pigeon Studios Discord, customers --> |

## Contents

- [What it does](#what-it-does)
- [How it works](#how-it-works)
- [Requirements](#requirements)
- [Running it locally](#running-it-locally)
- [Environment variables](#environment-variables)
- [Commands](#commands)
- [Project layout](#project-layout)
- [Deploying](#deploying)
- [Operations](#operations)
- [Data and privacy](#data-and-privacy)
- [Troubleshooting](#troubleshooting)

## What it does

<!-- The features, from the user's point of view. -->

-

## How it works

<!-- A short architecture overview: entry point, main modules, external services, database, scheduled jobs. A diagram helps. -->

```
Discord ──▶ index.js ──▶ handlers/ ──▶ commands/ ──▶ services/ ──▶ database / external APIs
```

## Requirements

- Node.js {{NODE_VERSION}} <!-- match package.json "engines" -->
- {{DATABASE}} <!-- e.g. MySQL 8, SQLite, none -->
- A Discord application and bot token from the [Discord Developer Portal](https://discord.com/developers/applications), with these intents: {{INTENTS}}

## Running it locally

```bash
git clone {{CLONE_URL}}
cd {{PROJECT_FOLDER}}
npm ci
cp .env.example .env    # then fill in .env with development values
npm run register        # registers slash commands with your test server
npm start
```

Use a **separate test bot and test Discord server** for development. Never point a local copy at the live bot token or live database.

## Environment variables

Every variable is listed in `.env.example` with placeholder values. Real values live in `.env` locally and in {{CI}} secrets for deployment. Never commit them.

| Variable | Required | What it's for |
|---|---|---|
| `DISCORD_TOKEN` | Yes | Bot token |
| `CLIENT_ID` | Yes | Application ID, for registering commands |
| `GUILD_ID` | Yes | The Discord server the bot runs in |
| `…` | | |

## Commands

| Command | Who can use it | What it does |
|---|---|---|
| `/command` | | |

## Project layout

| Path | What's there |
|---|---|
| `index.js` | Entry point |
| `commands/` | Slash commands |
| `events/` | Discord event handlers |
| `services/` | Business logic and external APIs |
| `utility/` | Shared helpers |
| `.github/workflows/` | CI and deployment |

## Deploying

Merging to `main` deploys automatically. The workflow:

1. installs dependencies with `npm ci`;
2. uploads the build to {{HOST}}; and
3. restarts the bot.

Secrets needed by the workflow: {{CI_SECRETS}} <!-- e.g. SFTP_HOST, SFTP_USER, SFTP_PASSWORD -->

To roll back, re-run the deploy workflow on the previous release tag.

## Operations

- **Logs:** {{WHERE_LOGS}}
- **Restart:** {{HOW_RESTART}}
- **Backups:** {{BACKUPS}}
- **Monitoring:** {{MONITORING}}
- **If the token leaks:** reset it in the Discord Developer Portal, update the CI secret and the host's environment, and redeploy.

## Data and privacy

<!-- What personal data the bot stores (Discord IDs, usernames, messages, applications), where, for how long, and who can see it.
     Must match the Privacy Policy: https://pigeonstudios.co.uk/legal/privacy/ -->

| Data | Why | Where it's stored | Kept for |
|---|---|---|---|
| Discord user IDs | | | |

## Troubleshooting

**The bot is online but commands don't appear.**
Run `npm run register` and wait a minute; check `CLIENT_ID` and `GUILD_ID`.

<!-- Add real problems and fixes. -->

---

© {{YEAR}} Pigeon Studios. Private and confidential.
