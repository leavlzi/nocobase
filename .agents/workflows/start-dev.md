---
description: Start NocoBase Development Server
---

# NocoBase Start Development Server Workflow

This workflow encapsulates the necessary environment setup to start the NocoBase project correctly, addressing specific Node.js and database requirements.

## Prerequisites

1. **Node.js**: The project requires **Node.js v20.x**. Using Node.js v25+ will cause runtime start failures (e.g., `SlowBuffer` deprecation inside `buffer-equal-constant-time` and `http_parser` issues).
2. **Database**: The valid CRM data imported by the user resides in the PostgreSQL database named `nocobase_crm2`. Ensure the `.env` file contains `DB_DATABASE=nocobase_crm2`.

## Step-by-Step Execution

// turbo-all
```bash
# Export the Homebrew Node 20 path so it takes precedence over newer system nodes
export PATH="/opt/homebrew/opt/node@20/bin:$PATH"

# Run the development server
yarn dev
```
