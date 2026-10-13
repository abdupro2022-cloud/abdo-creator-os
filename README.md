# ABDo Creator OS

ABDo Creator OS is a bilingual, responsive AI-powered creative operating system designed for creators, researchers, writers, marketers, and independent entrepreneurs.

## Architecture

- Frontend: React + TypeScript + Vite
- Backend: Express + TypeScript
- Auth/data layer foundation: Supabase-ready schema and local demo persistence
- Persistence: database-first, server-side, with secure integration boundaries
- Security: provider secrets never return to the browser; server-side validation and ownership checks are required

## Primary backend

Supabase is the canonical data and auth backend target. The project includes a SQL schema in `infra/sql/001_init.sql` and environment placeholders in `.env.example` for Supabase configuration. Where live values are not configured, the app runs in honest local/demo mode and clearly states that the integration is not yet connected.

## Local setup

1. Install dependencies: `npm install`
2. Copy `.env.example` to `.env` and configure values.
3. Start backend: `npm run dev:api`
4. Start frontend: `npm run dev:web`

## Environment variables

See `.env.example` for the required placeholders.

## Secure owner bootstrap

The owner bootstrap is intentionally server-side only. Public registration does not auto-assign privileged roles.

## Provider configuration

Provider credentials are encrypted server-side using the configured master key and never returned to the browser. Missing keys disable only the affected provider instead of crashing unrelated features.

## Build and verification

Run:

- `npm run build`
- `npm test`

This project includes a real foundation for auth, roles, projects, content, AI orchestration, skills, moderation, and configuration management, while keeping live external integrations behind honest, server-side boundaries.
