# SignalFlow 101 — Splunk Observability Cloud Workshop

**Workshop:** .conf26 · DEV1942 · 60 minutes  
**Repo:** https://github.com/PKing70/signalflow101-conf26

## Overview

This project is the Replit environment for the SignalFlow 101 workshop. Participants write Python that talks directly to the Splunk Observability Cloud SignalFlow API — sending latency metrics, investigating a fleet-wide anomaly, and computing an Apdex score.

## Required Secrets

Set these in **Tools > Secrets** (never in code or chat):

| Secret | Description |
|---|---|
| `SPLUNK_REALM` | Workshop realm, e.g. `us1` |
| `SPLUNK_INGEST_TOKEN` | Ingest token secret (from O11y Settings > Access Tokens) |
| `SPLUNK_API_TOKEN` | API token secret (from your O11y user profile) |
| `PARTICIPANT_ID` | Your assigned alias, e.g. `participant-042` |

## How to Run

Use the named workflows (Cmd+K / Ctrl+K → search "Workflows"):

| Workflow | Command | What it does |
|---|---|---|
| `0 - Check setup` | `python workshop.py check` | Verifies packages and secrets |
| `1 - Start API` | `python workshop.py serve` | Starts FastAPI on port 8000 |
| `2 - Send latency metrics` | `python workshop.py send` | Measures API and sends metrics to O11y |
| `3 - View fleet latency` | `python workshop.py fleet` | Runs SignalFlow fleet query |
| `4 - Compute Apdex` | `python workshop.py apdex` | Runs SignalFlow Apdex query |
| `In-room - API + sender` | `python workshop.py serve && python workshop.py send` | API + sender together |

**Recommended flow:** Run `0 - Check setup` first. Then `1 - Start API`, open Preview at `/hello`, then `2 - Send latency metrics`.

See [docs/REPLIT.md](docs/REPLIT.md) for the full walkthrough and troubleshooting tips.

## Project Structure

- `exercises/` — in-workshop exercise scripts (exercise1–3)
- `takehome/` — self-paced post-workshop exercises
- `workshop_api.py` — the FastAPI service participants measure
- `apdex.py` — reusable Apdex SignalFlow program builder
- `config.py` — loads credentials from Replit Secrets or `.env`
- `workshop.py` — CLI that backs all the named workflows
- `docs/EXERCISE_GUIDE.md` — step-by-step exercise guide

## User Preferences

<!-- Add any preferences here -->
