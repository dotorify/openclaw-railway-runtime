# Control API (for external UI)

This runtime exposes a small control API for managing `openclaw.json` without shell/SSH.

## Auth

All `/control/*` endpoints require:

- `OPENCLAW_CONTROL_TOKEN` env var to be set
- Request header: `Authorization: Bearer <token>`

## Endpoints

- `GET /control/status`
- `GET /control/config/summary`
- `GET /control/config` (masked)
- `POST /control/validate` body: `{ "patch": { ... } }`
- `PATCH /control/config` body: `{ "patch": { ... } }`
- `POST /control/apply` (restarts gateway)

## Legacy setup UI

This repo is designed to be controlled by an external UI service.

- `/setup` and `/tui` are only registered when `ENABLE_LEGACY_SETUP=true`.
- Default: disabled.
