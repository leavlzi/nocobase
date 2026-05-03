# Project Context & Tech Stack

This file documents the core technical stack, environmental constraints, and operational guidelines for this project. Antigravity and other AI agents should refer to this context when generating code, planning architectures, or diagnosing issues to ensure alignment with existing patterns.

## 🛠 Tech Stack Overview

- **Core Framework**: [NocoBase](https://docs.nocobase.com) (A scalability-first, open-source no-code/low-code platform).
- **Architecture**: Monorepo using `yarn` workspaces and `lerna`.
- **Frontend**: React 18, Umi v4 (Webpack based), Ant Design 5 (UI Library).
- **Backend/Language**: Node.js, TypeScript.
- **Database**: PostgreSQL.
- **Package Manager**: Yarn v1.22.x.

## ⚙️ Environment Constraints

- **Node.js**: **v20.x is strictly required** (Specifically defined as `20.14.0` in package.json `volta` config).
  - *Warning*: Running the project on newer Node versions (e.g., v25+) will result in startup crashes due to the deprecation of legacy Node native modules such as `http_parser` (used by Umi dev tools) and `SlowBuffer`.
- **Database Connect**: The system requires the background to be correctly pointer to the PostgreSQL DB `nocobase_crm2` containing the valid schema and user data. Target variables in `.env`:
  - `DB_DIALECT=postgres`
  - `DB_DATABASE=nocobase_crm2`

## 🚀 Running the Project

- **Development startup**: `yarn dev` starts both client and server development instances.
- *Agent Workflow Recommended Startup*: Agents should utilize the `.agents/workflows/start-dev.md` workflow to execute the startup which properly explicitly sets the Node 20 (`/opt/homebrew/opt/node@20/bin`) pathway to bypass potential system version conflicts.

## 📂 Key Directories
- `packages/` - Main workspace containing the plugins, core models, frontend apps, and client-server components.
- `storage/` - File uploads, local logs, and potentially SQLite backup directories.
- `.agents/` - AI Agent instructions, custom scripts, and start workflows.
