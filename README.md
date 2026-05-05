# Architecture Diagrams

Interactive system architecture documentation.

Deployed automatically to GitHub Pages using [declarative-diagram-builder](https://github.com/Brezzdy/declarative-diagram-builder).

## Systems

| System | Description |
|--------|-------------|
| Multi-Tenant SaaS Platform | Isolated per-client infrastructure with SSO, CRM, docs, and monitoring |
| Escrow Transaction Platform | Secure transaction escrow with dispute resolution and arbitration |
| Return Management SaaS | E-commerce return handling with multi-carrier and refund orchestration |
| Appointment Booking System | Edge-deployed scheduling with real-time availability and conflict detection |
| Workflow Automation Engine | Task distribution and time tracking via messaging bots and spreadsheets |
| Real-Time Voting App | WebSocket-based live voting with in-memory state and consensus |

## Structure

```
diagrams/
├── multi-tenant-saas-platform/
├── escrow-platform/
├── return-management-saas/
├── booking-system/
├── workflow-automation/
└── realtime-voting-app/
```

## Usage

Push to `main` → diagrams auto-deploy to GitHub Pages as interactive HTML with pan/zoom, dark mode, git history, and fullscreen.
