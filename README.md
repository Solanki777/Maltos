<div align="center">

# Maltos

**An AI collaborative meeting platform where role-specific agents and people solve problems together.**

![React](https://img.shields.io/badge/frontend-React%20%2B%20TypeScript-3B82F6)
![FastAPI](https://img.shields.io/badge/backend-FastAPI-3B82F6)
![PostgreSQL](https://img.shields.io/badge/database-PostgreSQL-3B82F6)

</div>

> **Draft status:** This README was drafted from the project brief, without access to the source code.
> Every item marked `TODO(verify)` must be checked against the repository before publishing.
> Nothing below has been confirmed as implemented unless it says so.

---

## Table of Contents

1. [Overview](#overview)
2. [Key Features](#key-features)
3. [Screenshots](#screenshots)
4. [How Maltos Works](#how-maltos-works)
5. [Architecture](#architecture)
6. [Technology Stack](#technology-stack)
7. [Project Structure](#project-structure)
8. [Prerequisites](#prerequisites)
9. [Installation and Setup](#installation-and-setup)
10. [Environment Variables](#environment-variables)
11. [Database Setup and Migrations](#database-setup-and-migrations)
12. [Running Locally](#running-locally)
13. [Demo Mode and Real AI Providers](#demo-mode-and-real-ai-providers)
14. [API and WebSocket Reference](#api-and-websocket-reference)
15. [Orchestration, Permissions, and Memory](#orchestration-permissions-and-memory)
16. [Testing and Verification](#testing-and-verification)
17. [Security and Privacy](#security-and-privacy)
18. [Limitations and Known Issues](#limitations-and-known-issues)
19. [Roadmap](#roadmap)
20. [Contributing](#contributing)
21. [Reporting Bugs](#reporting-bugs)
22. [License](#license)
23. [Author and Contact](#author-and-contact)

---

## Overview

Maltos is a meeting room for AI agents and people. You define a problem, add agents with specialized roles (for example a researcher, a critic, or a planner), and let them discuss it in a shared room. Human participants can join, direct questions at specific agents, and control who speaks and when.

A meeting is meant to end with something usable: a transcript, a conclusion, the points on which participants disagreed, and a list of action items.

## Key Features

Status legend: **Implemented** (verified in code), **In progress**, **Planned**.

| Capability | Status |
| --- | --- |
| Create a meeting with a defined goal | TODO(verify) |
| Add agents with specialized roles | TODO(verify) |
| Shared live discussion in a meeting room | TODO(verify) |
| Speaking permissions and agent turn control | TODO(verify) |
| Ask a specific agent a question | TODO(verify) |
| Pause, resume, and end a meeting | TODO(verify) |
| Persistent transcripts and meeting memory | TODO(verify) |
| Conclusions, disagreements, and action items | TODO(verify) |
| Authentication and authorization | Planned unless found in code |

## Screenshots

<!-- TODO: Add real screenshots only. Suggested location: docs/screenshots/ -->

No screenshots have been added yet.

## How Maltos Works

```mermaid
flowchart LR
    A[Create meeting and goal] --> B[Add agents and participants]
    B --> C[Start discussion]
    C --> D{Who speaks next?}
    D -->|Agent turn| E[Agent responds]
    D -->|Human turn| F[Participant posts message]
    E --> G[Transcript and memory updated]
    F --> G
    G --> D
    G --> H[Pause / resume / end]
    H --> I[Conclusion, disagreements, action items]
```

`TODO(verify)`: confirm this flow matches the real turn logic and adjust the diagram.

## Architecture

The intended layering, per the project brief:

```mermaid
flowchart TD
    UI[React + TypeScript frontend] --> API[FastAPI backend]
    API --> ENGINE[Meeting API and permission engine]
    ENGINE --> ORCH[AI orchestration layer]
    ORCH --> PROV[AI provider adapters]
    API --> DB[(PostgreSQL)]
    API -. live updates .-> WS[WebSockets]
    WS -.-> UI
```

`TODO(verify)`: remove or rename any layer that does not exist in the source. Do not document services that are not implemented.

## Technology Stack

| Layer | Technology | Verified |
| --- | --- | --- |
| Frontend | React, TypeScript | TODO(verify) |
| Backend | FastAPI (Python) | TODO(verify) |
| Database | PostgreSQL | TODO(verify) |
| Realtime | WebSockets | TODO(verify) |
| AI providers | TODO: list real adapters | TODO(verify) |
| Migrations | TODO: name the tool, if any | TODO(verify) |

## Project Structure

<!-- TODO: replace with the real tree, for example from `tree -L 3 -I "node_modules|.venv|__pycache__"` -->

```text
maltos/
├── frontend/    # TODO(verify)
├── backend/     # TODO(verify)
├── .env.example # TODO(verify)
└── README.md
```

## Prerequisites

TODO(verify) against `package.json`, the Python dependency file, and any Docker config:

- Node.js and a package manager (version: TODO)
- Python (version: TODO)
- PostgreSQL (version: TODO)
- Git
- Optional: Docker and Docker Compose, only if a compose file exists

## Installation and Setup

Replace the placeholders with the repository's real values.

```powershell
# Clone
git clone <your-repo-url> maltos
cd maltos

# Frontend dependencies
cd <frontend-dir>
<package-manager> install
cd ..

# Backend virtual environment (Windows PowerShell)
cd <backend-dir>
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r <requirements-file>
```

On macOS or Linux, activate the environment with `source .venv/bin/activate`.

## Environment Variables

Copy `.env.example` to `.env` and fill in values. Never commit `.env` or real keys.

```powershell
Copy-Item .env.example .env
```

<!-- TODO: replace every row with variables found in .env.example and the code -->

| Variable | Purpose | Required | Example placeholder |
| --- | --- | --- | --- |
| `TODO_DATABASE_URL` | PostgreSQL connection string | TODO | `postgresql://user:password@localhost:5432/dbname` |
| `TODO_AI_PROVIDER_KEY` | API key for the real AI provider | Only in real-provider mode | `your-api-key-here` |
| `TODO_DEMO_MODE` | Toggles demo mode, if implemented | TODO | `true` |

## Database Setup and Migrations

TODO(verify): document how PostgreSQL is started (local install or Docker), how the database is created, and the real migration command (for example Alembic, if used).

## Running Locally

```powershell
# Terminal 1: backend
<backend-start-command>

# Terminal 2: frontend
<frontend-start-command>
```

TODO(verify): add the real commands and default ports.

## Demo Mode and Real AI Providers

TODO(verify): state whether both modes exist.

| | Demo mode | Real provider mode |
| --- | --- | --- |
| Agent replies | TODO | Generated by the configured AI provider |
| API key needed | TODO | Yes |
| Cost | TODO | Depends on the provider |

## API and WebSocket Reference

<!-- TODO: build these tables from the real route files. FastAPI usually serves interactive docs; confirm the URL before documenting it. -->

| Method | Path | Description |
| --- | --- | --- |
| TODO | TODO | TODO |

**WebSocket:** TODO(verify) endpoint path, message formats, and event types.

## Orchestration, Permissions, and Memory

TODO(verify) each of the following against the code before keeping it:

- **Orchestration:** how the next speaker is chosen and how agent turns are triggered.
- **Permissions:** what controls whether an agent or participant may speak.
- **Memory:** what is stored, whether memory is shared or private per agent, and how it is passed back to agents.
- **Conclusions:** how conclusions, disagreements, and action items are generated and stored.

## Testing and Verification

```powershell
# Backend
<backend-test-command>

# Frontend
<frontend-test-command>
```

TODO(verify): add the real commands. Do not publish coverage figures unless you have measured them.

## Security and Privacy

- Keep API keys and database credentials in `.env`, which must stay out of version control.
- Meeting transcripts may contain sensitive information, and with a real AI provider that text is sent to the provider.
- Authentication and authorization are planned, not assumed. Until they exist, do not expose the app to untrusted networks.
- TODO(verify): add details on CORS, input validation, and data retention.

## Limitations and Known Issues

TODO: list real limitations after review. Until verified, do not describe Maltos as production-ready.

## Roadmap

Check an item only after verifying it in the code.

- [ ] Responsive meeting dashboard
- [ ] Meeting and agent management
- [ ] Persistent meeting history
- [ ] Real-time chat and speaking queue
- [ ] Single-agent AI integration
- [ ] Multi-agent orchestration
- [ ] Shared and private agent memory
- [ ] Meeting conclusions and action items
- [ ] Automated tests and failure handling
- [ ] Docker-based deployment
- [ ] Authentication and authorization
- [ ] Optional semantic memory search

## Contributing

1. Fork the repository and create a feature branch.
2. Make focused changes and add or update tests where applicable.
3. Run the test commands above before opening a pull request.
4. Describe what changed and why in the pull request.

## Reporting Bugs

Open a GitHub issue with:

- What you expected and what happened
- Steps to reproduce
- Operating system, Node.js and Python versions
- Whether you were in demo mode or real provider mode
- Relevant logs, with any secrets removed

## License

TODO: no license has been selected. Add a `LICENSE` file and name it here, or remove this section.

## Author and Contact

TODO: add author name and links supplied by the project owner.
