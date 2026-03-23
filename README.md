# mad-agentic.io

Agent Workspace / Control Center landing page for GitHub Pages.

## Structure

- `index.html`: main landing page markup
- `styles/main.css`: dark control-center visual system, responsive layout, dashboard cards, timeline, and guardrail styling
- `scripts/main.js`: workspace panel tab switching and reveal-on-scroll behavior
- `CNAME`: custom domain binding for GitHub Pages

## Included Sections

- Hero with dashboard mockup
- Workspace signal cards for Agent Runs, Tool Calls, Memory, and Approval Flow
- Agent activity timeline
- Multi-agent orchestration cards
- Use-case cards for Engineering, Support, Operations, and Growth
- GitHub Products section with quickstart guidance
- Security, audit, and guardrail section
- Documentation CTA linked to `README.md`

## GitHub Products Guide

### 1) ProxyAPI.MAD

- Repository: https://github.com/mad-agentic/ProxyAPI.MAD
- Purpose: Admin dashboard plus proxy backend for AI CLI tools, compatible with OpenAI/Gemini/Claude/Codex.
- Main modules:
  - `proxyapi_core/`: Go backend (proxy + management API)
  - `frontend/`: React + Vite + TypeScript dashboard

### Quick Start (Windows)

From repository root:

- Run `run-dev.bat` to start backend (`http://localhost:8317`) and frontend (`http://localhost:5173`)
- Or run `run-real.bat` for backend-only mode

### Manual Setup (All OS)

1. Backend config
	- `cd proxyapi_core`
	- `cp config.example.yaml config.yaml`
	- Update `config.yaml`:
	  - `api-keys`
	  - `remote-management.secret-key`
	  - `usage-statistics-enabled: true`

2. Run backend
	- `cd proxyapi_core && go run ./cmd/server`

3. Run frontend
	- `cd frontend && npm install && npm run dev`

### Production Notes

- Build frontend: `cd frontend && npm run build`
- Output: `frontend/dist/`
- Security: do not commit real secret config files; do not commit runtime directories (`logs/`, `auths/`, `temp/`, `conv/`).

### Template for next products

When adding a new repository, keep this format:

1. Repository and product goal
2. Core structure (backend/frontend/services)
3. Quick start by OS
4. Manual setup commands
5. Build/Deploy notes
6. Security checklist before publishing

## Editing

Open `index.html` to change copy, panel content, and section order.

Adjust colors, spacing, responsive behavior, and dashboard styling in `styles/main.css`.

Update tab behavior and reveal interactions in `scripts/main.js`.

## Deployment

This repo is set up for GitHub Pages and uses the existing `CNAME` file for `mad-agentic.online`.

The site is zero-build, so publishing the static files from the repo root is sufficient.