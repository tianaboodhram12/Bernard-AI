# Bernard AI — Backlog

> Source: Bernard AI Project Plan v0.2 (21 September 2026). This backlog preserves task IDs and scope explicitly supported by the project plan. Where the plan references a task without defining its full task description, the entry is marked **Task detail not specified in Project Plan v0.2** rather than inventing requirements.

## Status model

- **Proposed** — new request awaiting release planning
- **Backlog** — approved work not yet ready
- **Ready** — approved and ready to start
- **In Progress** — actively being implemented
- **Code Review** — PR opened against `staging`
- **Staging** — merged and under staging validation
- **Done** — accepted
- **Deferred** — intentionally moved to a later release

## Delivery windows

| Window | Dates | Purpose |
|---|---|---|
| Build A | 21 Sep–2 Oct 2026 | Contain critical findings, record decisions, book POPIA review, hand over to Claude Code |
| Build B | 5–23 Oct 2026 | Staging/production, migration baseline, hosting, AI adapter, tests, error-reporting check |
| Build C | 26 Oct–13 Nov 2026 | Attestation, consent, recording, AI data minimisation, transcription |
| Build D | 16–20 Nov 2026 | Backups, production providers, disclosure, beta go-live |
| Beta R1 | 23 Nov–4 Dec 2026 | Questionnaire proposals from transcript, evidence queue, first-week monitoring |
| Beta R2 | 7–18 Dec 2026 | Conflict handling, MFA/security hardening, policy tests, limits, POC data disposal |
| Beta R3 | 4–15 Jan 2027 | Code verification, server-side drafting/finalisation gates, honest document analysis |
| Beta R4 | 18–29 Jan 2027 | Citation integrity, house-format export, end-of-beta sign-off |
| v1.1a | 1 Feb–16 Mar 2027 | Monitoring, background jobs, practice drafting model |
| v1.1b | 17 Mar–22 Apr 2027 | Legacy cleanup, stage rules, atomic writes, retention, full-document analysis, accessibility |
| v1.2 | 23 Apr–27 May 2027 | Should/Could features |

## P0 — Build A: decisions and POC containment

| Task | Project-plan-supported scope | Window | Status |
|---|---|---|---|
| P0-T02 | Resolve ASM-06: whether account creation is invitation-only. | Build A | Backlog |
| P0-T03 | Closing task for FR-130, a broken requirement. | Build A | Backlog |
| P0-T04 | Resolve ASM-32 on the lawful basis for using prior client reports to learn style; suspend the style corpus during beta. | Build A | Backlog |
| P0-T05 | Resolve ASM-24 on remediation of personal data in migration history. | Build A | Backlog |
| P0-T06 | Resolve ASM-14 on immutable attestation records; contributes to FR-065. | Build A | Backlog |
| P0-T07 | Confirm launch scope/BRS priorities, POPIA Information Officer, measurable targets, and when real matters may enter beta. | Build A | Backlog |
| P0-T08 | Compare transcription provider options; provider decision needed by mid-October. | Build A | Backlog |

## P1 — Build B: production foundation

| Task | Project-plan-supported scope | Window | Status |
|---|---|---|---|
| P1-T03 | Create clean migration baseline from the 20 POC migrations, excluding rows containing real report file names. | Build B | Backlog |
| P1-T04 | Check maximum durations relevant to long AI/transcription work. | Build B | Backlog |
| P1-T06 | Remove legacy structures: old questionnaire template table, superseded syntheses table and duplicate document types. | Build B | Backlog |
| P1-T07 | Verification pass for functional requirements with caveats, including 'screen not read'. | Build B / Beta R3 verification | Backlog |
| P1-T08 | Create fictional staging seed data; no real personal data in code, migrations, seed files or tests. | Build B | Backlog |
| P1-T09 | Resolve ASM-37: when real matters may enter beta. | Build B | Backlog |

## P2 — Trust, workflow and hardening

| Task | Project-plan-supported scope | Planned window | Status |
|---|---|---|---|
| P2-T01 | Closing task for FR-065/FR-066/FR-067; trust-critical workflow/attestation requirements. | Build A / Build C | Backlog |
| P2-T03 | Workflow gates; example branch name in the plan is `feature/P2-T03-workflow-gates`. Also closes FR-077 and FR-102. | Beta R3 | Backlog |
| P2-T05 | Case/questionnaire relationship and table-row-order work; closes FR-010 and FR-052. | v1.1b | Deferred |
| P2-T06 | Complete consent including guardians for minors; resolves ASM-09 and closes FR-040. | Build C | Backlog |
| P2-T07 | Trust-critical requirement associated with FR-042. Full task detail not specified in Project Plan v0.2. | Build C | Backlog |
| P2-T08 | Trust-critical requirement associated with FR-133. Full task detail not specified in Project Plan v0.2. | Build C | Backlog |
| P2-T09 | Closes FR-021, FR-026 and FR-027; part of server-side workflow hardening. | Beta R3 | Backlog |
| P2-T10 | Closes FR-072 and FR-078. Full task detail not specified in Project Plan v0.2. | Beta R4 | Backlog |
| P2-T11 | Template versioning and sources introduction; closes FR-070 and FR-073. | v1.1a | Deferred |
| P2-T12 | Closes FR-080 and FR-146. Full task detail not specified in Project Plan v0.2. | Beta R4 | Backlog |
| P2-T14 | Retention enforcement and automatic audio deletion; closes FR-047 and FR-132; resolves ASM-22. | v1.1b | Deferred |
| P2-T16 | Contributes to FR-021 and closes FR-149: full-document analysis with opinion priority. | v1.1b | Deferred |

## P3 — Transcription and practice drafting model

| Task | Project-plan-supported scope | Planned window | Status |
|---|---|---|---|
| P3-T01 | Asynchronous transcription provider jobs; closes FR-045. | Build C | Backlog |
| P3-T02 | Questionnaire proposal capability; closes FR-061. The plan says proposals arrive in Beta R1. | Beta R1 | Backlog |
| P3-T03 | Questionnaire proposal-related requirement; closes FR-055. | Beta R1 | Backlog |
| P3-T04 | Questionnaire/transcript evidence capability; closes FR-056 and FR-063. | Beta R2 | Backlog |
| P3-T05 | Report types; contributes to FR-140. | v1.1a | Deferred |
| P3-T06 | Scenario panel; closes FR-141. | v1.1a | Deferred |
| P3-T07 | Standard paragraph library; contributes to FR-142. | v1.1a | Deferred |
| P3-T08 | Drafting from the anonymised library; contributes to FR-142 and is part of leakage mitigation. | v1.1a | Deferred |
| P3-T09 | Remuneration scale tables; closes FR-143 and resolves ASM-31. | v1.1a | Deferred |

## P4 — Beta R4 / launch validation

| Task | Project-plan-supported scope | Planned window | Status |
|---|---|---|---|
| P4-T01 | Report-type work contributing to FR-140. | v1.1a | Deferred |
| P4-T02 | Report-type work contributing to FR-140. | v1.1a | Deferred |
| P4-T06 | Leakage check for details from other matters appearing in a draft. | Beta R4 | Backlog |

## P5 — Post-launch platform and operational hardening

| Task | Project-plan-supported scope | Planned window | Status |
|---|---|---|---|
| P5-T01 | Background jobs for long AI work, with progress, timeouts and recovery. | v1.1a | Deferred |
| P5-T02 | Monitor AI provider usage/cost ceiling. | v1.1a / operational | Backlog |
| P5-T04 | Production point-in-time recovery consideration for Supabase. | Operational | Backlog |
| P5-T06 | Contributes to FR-130. Full task detail not specified in Project Plan v0.2. | Build A | Backlog |
| P5-T07 | Book and complete independent POPIA/legal review before real matters; fallback to fictional beta matters if incomplete. | Build D / before beta | Backlog |
| P5-T08 | End-of-beta acceptance/sign-off against BRS acceptance criteria AC-01 to AC-30. | Beta R4 | Backlog |

## P6 — POC disposal / migration

| Task | Project-plan-supported scope | Planned window | Status |
|---|---|---|---|
| P6-T02 | Before launch, re-enter or move real POC data using a reviewed script, then dispose of POC data. Lovable POC is frozen after handover. | Beta R2 | Backlog |

## Deferred Must requirements

These requirements are explicitly planned after launch:

- FR-010 — Case and questionnaire created together — P2-T05 — v1.1b
- FR-047 — Automatic audio deletion at retention expiry — P2-T14 — v1.1b
- FR-052 — Table row removal keeps order — P2-T05 — v1.1b
- FR-070 — One template version per report — P2-T11 — v1.1a
- FR-073 — Sources introduction reflects the record — P2-T11 — v1.1a
- FR-132 — Retention enforced — P2-T14 — v1.1b
- FR-140 — Report types — P3-T05, P4-T01, P4-T02 — v1.1a
- FR-141 — Scenario panel — P3-T06 — v1.1a
- FR-142 — Standard paragraph library — P3-T07, P3-T08 — v1.1a
- FR-143 — Remuneration scale tables — P3-T09 — v1.1a
- FR-149 — Full-document analysis with opinion priority — P2-T16 — v1.1b

## Out of scope

- OCR for scanned documents
- Sending reports or invoices by email
- Quantifying loss of earnings
- Learning style from other clients' reports

## Working rules

1. New requests enter this backlog as **Proposed**.
2. During beta, release planning happens every two weeks; scope is not added in the middle of an active task.
3. Every task is implemented from a branch created from `staging`.
4. PRs target `staging` and reference the task ID.
5. Test locally against the definition of done, then test on staging before production.
6. Update the task status in this file after merge.
7. Staging contains fictional data only. Never commit real personal data, migrations containing real data, seed data or the REPORT MASTER.
8. Acceptance criteria AC-01 to AC-30 form the test script.
