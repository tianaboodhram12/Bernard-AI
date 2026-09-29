# Bernard AI

Project delivery repository for Bernard AI — from proof of concept to production.

## Project

Bernard AI supports an industrial psychologist in preparing Road Accident Fund medico-legal reports by analysing expert reports, recording interviews, capturing the biographical questionnaire, locking it under the psychologist's sign-off, and drafting the report.

The project plan defines a fixed delivery window: Build from 21 September to 20 November 2026, beta from 23 November 2026 to 29 January 2027, and launch on 29 January 2027.

## Delivery approach

- `main` — production
- `staging` — staging environment
- `feature/*` — task branches

For each task:

1. Create the task branch from `staging`.
2. Implement and commit the task in stages.
3. Test locally against the definition of done.
4. Open a pull request into `staging` referencing the task ID.
5. Merge and test in staging.
6. Update `BACKLOG.md`.

## Delivery windows

| Window | Dates | Purpose |
|---|---|---|
| Build A | 21 Sep–2 Oct 2026 | Contain critical findings, decisions, POPIA review, handover |
| Build B | 5–23 Oct 2026 | Foundation: environments, migrations, hosting, AI adapter, tests |
| Build C | 26 Oct–13 Nov 2026 | Trust-critical hardening and interview transcription |
| Build D | 16–20 Nov 2026 | Beta readiness and go-live |
| Beta R1 | 23 Nov–4 Dec 2026 | Questionnaire proposals and first-week monitoring |
| Beta R2 | 7–18 Dec 2026 | Conflict handling and security hardening |
| Beta R3 | 4–15 Jan 2027 | Verification and server-side workflow gates |
| Beta R4 | 18–29 Jan 2027 | Citation integrity, export and launch sign-off |
| v1.1a | 1 Feb–16 Mar 2027 | Practice drafting model and monitoring/background jobs |
| v1.1b | 17 Mar–22 Apr 2027 | Remaining hardening |
| v1.2 | 23 Apr–27 May 2027 | Should/Could features |

## Security and data handling

This repository must not contain real plaintiff/patient personal information, real report data, migration rows containing personal data, seed data with real matters, or the REPORT MASTER. Staging uses fictional data only.

See [`docs/project-plan.md`](docs/project-plan.md) for the project-plan summary.
