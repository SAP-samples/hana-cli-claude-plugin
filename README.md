# hana-cli — Claude Code Plugin

[![MCP Registry](https://img.shields.io/badge/MCP_Registry-hana--cli-blue)](https://registry.modelcontextprotocol.io/?q=hana-cli)
[![npm](https://img.shields.io/npm/v/hana-cli)](https://www.npmjs.com/package/hana-cli)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![REUSE status](https://api.reuse.software/badge/github.com/SAP-samples/hana-cli-claude-plugin)](https://api.reuse.software/info/github.com/SAP-samples/hana-cli-claude-plugin)

**150+ SAP HANA database tools as AI-powered MCP tools for Claude Code.**

This plugin connects Claude Code to SAP HANA Cloud and on-premise databases, giving your AI assistant direct access to schema exploration, data import/export, performance monitoring, security audits, backup management, and much more.

## Install

In Claude Code, run:

```
/plugin install https://github.com/SAP-samples/hana-cli-claude-plugin
```

Or install manually by adding this to your project's `.mcp.json`:

```json
{
  "hana-cli": {
    "command": "npx",
    "args": ["-y", "-p", "hana-cli", "hana-cli-mcp"]
  }
}
```

## What You Get

| Category | Tools | Examples |
|----------|-------|---------|
| **Schema exploration** | 20+ | List tables, views, procedures, functions, schemas |
| **Object inspection** | 10+ | Inspect table columns, view definitions, procedure parameters |
| **Data tools** | 15+ | Import CSV/Excel/JSON, export data, profile data quality, validate data |
| **Performance monitoring** | 15+ | Expensive statements, memory analysis, blocking sessions, deadlocks |
| **Security** | 10+ | Users, roles, privilege analysis, security scans, audit logs |
| **Backup & recovery** | 5+ | Create backups, check status, list backups, restore |
| **System admin** | 10+ | Health checks, system info, diagnostics, INI configuration |
| **Developer tools** | 15+ | CDS generation, code templates, test data generation, HDI containers |
| **Discovery & help** | 15+ | Search commands, examples, troubleshooting, guided workflows |

**166 total MCP tools** — covering virtually every SAP HANA administration and development task.

## Prerequisites

- **Node.js** 20.19.0 or later
- **SAP HANA** database (Cloud or on-premise) with connection credentials

## Database Connection

The plugin connects to your SAP HANA database using standard connection methods. Configure credentials via any of these (checked in order):

1. `default-env-admin.json` — admin connections
2. `.cdsrc-private.json` — SAP CAP dynamic binding
3. `.env` / `VCAP_SERVICES` — environment variables
4. `default-env.json` — default connection file
5. `~/.hana-cli/default.json` — global default

Use the `hana-cli connect` command to set up credentials interactively:

```bash
npx hana-cli connect
```

Or use the `__projectContext` parameter on any tool call to specify connection details dynamically.

## Example Usage

Once installed, just ask Claude:

- *"What tables are in my HANA database?"*
- *"Show me the most expensive SQL statements"*
- *"Export the PRODUCTS table to CSV"*
- *"Run a health check on my database"*
- *"Find duplicate records in the ORDERS table"*
- *"Profile the data quality of CUSTOMERS"*
- *"What users have excessive privileges?"*

## Documentation

- [hana-cli documentation](https://github.com/SAP-samples/hana-developer-cli-tool-example)
- [MCP Registry listing](https://registry.modelcontextprotocol.io/?q=hana-cli)
- [SAP HANA Cloud documentation](https://help.sap.com/docs/hana-cloud)

## License

Copyright (c) 2026 SAP SE or an SAP affiliate company. All rights reserved.
This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.

## Repository Governance

This repository is part of the [SAP-samples](https://github.com/SAP-samples) GitHub
organisation. Administrative access is granted at the organisation level (SAP OSPO,
SAP-samples maintainers, automation bots) and is not managed per-repository. There
are zero direct collaborators on this repository.

The `main` branch is protected by a repository ruleset:

- Pull requests required (no direct pushes)
- Linear history required
- Force-pushes blocked
- Branch deletion blocked

## Contributing

This plugin wraps [hana-cli](https://github.com/SAP-samples/hana-developer-cli-tool-example), an open-source SAP sample project. Issues and contributions are welcome at the [main repository](https://github.com/SAP-samples/hana-developer-cli-tool-example/issues).
