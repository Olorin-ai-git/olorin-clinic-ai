# Olorin Clinic AI: autonomous front desk for aesthetics clinics

**A multi-tenant AI patient-communication platform.** WhatsApp and Telegram bots that answer patients, book real appointments against a real calendar, know when to hand off to staff, and are tested every night by an autonomous AI red-team.

> Live in production with a real aesthetics clinic. *(Client identity withheld.)*

## The problem
Aesthetics clinics lose bookings to slow replies and after-hours silence. A chatbot that improvises is worse than none, though: in a health-adjacent setting, **bookings must be real calendar events, emergencies must always escalate, and the bot must never fabricate patient data.** Proving that continuously is harder than building the bot.

## What it does
- **AI front desk per clinic**: answers questions, books, reschedules and cancels against the clinic's real calendar
- **Safe escalation**: urgent and medical messages always go to a human; staff can take over any conversation
- **Multi-tenant**: each clinic gets its own configuration, channels, staff roles and data isolation
- **Honesty guardrails**: the bot never claims a booking that doesn't exist and never invents patient details
- **Security by default**: role-based access, TOTP 2FA, encryption of sensitive fields at rest

## How it's verified
A **nightly autonomous red-team of 56 AI agents** plays patients (edge cases, adversarial prompts, multilingual conversations) against a QA clone of the system before any regression can reach a real patient. Failures feed an automated fix-and-retest loop.

## Stack
| Layer | Tech |
|---|---|
| Backend | Python 3.12 · FastAPI · SQLAlchemy (async) · PostgreSQL |
| AI | Claude (Anthropic) |
| Channels | WhatsApp · Telegram |
| Frontend | React 19 · TypeScript · Vite · Tailwind |
| Infra | Google Cloud Run · Cloud Build · Firebase Hosting |
| Testing | pytest · Playwright E2E · autonomous red-team harness |

## Built how
Built solo by one engineer directing fleets of AI agents: spec-first plans, test-driven changes, and autonomous QA, part of the [Olorin ecosystem](https://klainert.com).

> This is a showcase repository. The product source code is private.

---
Built by [Gil Klainert](https://github.com/gilco1973) · [klainert.com](https://klainert.com)
