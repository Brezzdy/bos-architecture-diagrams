# Architecture Diagrams

Interactive system architecture documentation for all projects.

Deployed automatically to GitHub Pages using [declarative-diagram-builder](https://github.com/Brezzdy/declarative-diagram-builder).

## Projects

| Project | Description | Stack |
|---------|-------------|-------|
| **BOS Platform** | Multi-tenant business operating system with per-client VPS | Docker, Odoo, Authentik, Nextcloud |
| **Escroo** | Escrow transaction platform for Romania | React, Node.js, MongoDB, Stripe |
| **Retur.ro** | Return management SaaS for e-commerce | React, FastAPI, PostgreSQL, Docker |
| **Test Drive Booking** | Dealership test drive scheduling SaaS | React, Cloudflare Workers, D1, KV |
| **Automations** | Task distribution & tracking system | n8n, Telegram Bot, Google Sheets |
| **Scrum Poker** | Real-time planning poker for agile teams | Node.js, Socket.IO, EJS |

## Structure

```
diagrams/
├── bos-platform/        # Business Operating System
├── escroo/              # Escrow Platform
├── retur-ro/            # Return Management SaaS
├── testdrive-booking/   # Test Drive Booking
├── automations/         # n8n Task Automation
└── scrum-poker/         # Planning Poker
```

## Usage

Push to `main` → diagrams auto-deploy to GitHub Pages as interactive HTML with pan/zoom, dark mode, git history, and fullscreen.
