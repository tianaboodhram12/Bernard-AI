# Bernard AI — Project Plan

**Project Plan:** from proof of concept to production  
**Version:** 0.2  
**Date:** 21 September 2026  
**Prepared for:** Bernard Oosthuizen Incorporated

> This document is a GitHub working summary of the approved Project Plan v0.2. It is a delivery plan, not a statement of legal compliance.

## 1. Objective

Move Bernard AI from the existing Lovable proof of concept to a production system that can safely support real matters, with interview transcription added before beta and a two-month beta before launch.

## 2. Key dates

- **Build:** 21 September–20 November 2026
- **Beta:** 23 November 2026–29 January 2027
- **Launch:** 29 January 2027
- **v1.1a:** 1 February–16 March 2027
- **v1.1b:** 17 March–22 April 2027
- **v1.2:** 23 April–27 May 2027

## 3. What changes for Bernard

| Date | Capability / outcome |
|---|---|
| 2 Oct 2026 | POC contained: sign-up closed, disclosure corrected, sign-offs locked |
| 23 Nov 2026 | Production beta: record interviews, transcripts, analysis, attestation, drafting and export |
| 7 Dec 2026 | Questionnaire answers proposed from transcript and linked to recording moments |
| 18 Dec 2026 | Conflict resolution and two-factor authentication |
| 15 Jan 2027 | Server refuses drafting before attestation/finalisation requirements are satisfied; incomplete analysis is visible |
| 29 Jan 2027 | Citation integrity, house-format export and launch sign-off |
| Feb 2027 onward | Practice-approved paragraph/scenario drafting and remuneration tables in v1.1a |

## 4. Scope at beta start

- Four critical findings contained
- Public sign-up closed and disclosure accurate
- Separate staging and production systems owned on the practice side
- Tamper-evident attestation
- Complete consent, including guardians for minors
- Loss-proof recording
- Minimal data sent to AI
- Interview transcription with speaker labels through an agreed provider and signed operator agreement

## 5. Beta scope

- Questionnaire proposals and conflict handling
- Security hardening
- Server-enforced drafting and finalisation rules
- Citation integrity
- House-format export

The existing POC drafting approach is used during beta with the style corpus switched off. The practice's scenario-based drafting model moves to v1.1a.

## 6. Deferred requirements

The following Must requirements are planned after launch according to the project plan:

- FR-010 — Case and questionnaire created together — v1.1b
- FR-047 — Automatic audio deletion at retention expiry — v1.1b
- FR-052 — Table row removal keeps order — v1.1b
- FR-070 — One template version per report — v1.1a
- FR-073 — Sources introduction reflects the record — v1.1a
- FR-132 — Retention enforced — v1.1b
- FR-140 — Report types — v1.1a
- FR-141 — Scenario panel — v1.1a
- FR-142 — Standard paragraph library — v1.1a
- FR-143 — Remuneration scale tables — v1.1a
- FR-149 — Full-document analysis with opinion priority — v1.1b

Out of scope: OCR for scanned documents, sending reports/invoices by email, quantifying loss of earnings, and learning style from other clients' reports.

## 7. Roadmap

| Window | Dates | Planned sessions |
|---|---|---:|
| Build A | 21 Sep–2 Oct 2026 | 7.5 |
| Build B | 5–23 Oct 2026 | 9.5 |
| Build C | 26 Oct–13 Nov 2026 | 12.5 |
| Build D | 16–20 Nov 2026 | 3 |
| Beta R1 | 23 Nov–4 Dec 2026 | 6 |
| Beta R2 | 7–18 Dec 2026 | 6.5 |
| Beta R3 | 4–15 Jan 2027 | 7 |
| Beta R4 | 18–29 Jan 2027 | 7 |
| v1.1a | 1 Feb–16 Mar 2027 | 22.5 |
| v1.1b | 17 Mar–22 Apr 2027 | 18.5 |
| v1.2 | 23 Apr–27 May 2027 | 18 |

The plan assumes five focused build sessions per week and no work from 21 December 2026 to 3 January 2027.

## 8. Architecture and branching

### Current POC

- TanStack Start / React with server functions
- Lovable Cloud / Supabase Postgres
- Row-level security, authentication and file storage
- Lovable AI Gateway
- Browser MediaRecorder with 30-second chunks and crash recovery

### Planned

- Separate staging and production Supabase projects
- App hosting on Vercel or another TanStack Start-compatible host
- AI adapter under `src/lib/ai/`
- Transcription adapter under `src/lib/transcription/`
- Business rules enforced in database/server functions
- Background jobs for long AI work
- Standard paragraph library and scenario answers

### Branch model

| Branch | Environment | Data |
|---|---|---|
| `feature/*` | Local | Local Supabase |
| `staging` | Staging | Fictional data only |
| `main` | Production | Real practice use |

The Lovable POC is frozen after handover. Building continues in Claude Code; using Lovable and Claude Code on the same branch is specifically avoided.

## 9. Git workflow

1. Update `staging` locally.
2. Create a feature branch from `staging`, e.g. `feature/P2-T03-workflow-gates`.
3. Run task prompts one stage at a time and commit after each stage.
4. Test locally against the definition of done.
5. Open a pull request into `staging` and reference the task ID.
6. Merge and test on staging.
7. Update `BACKLOG.md`.
8. During build, promote staging to `main` at the end of each build stage.
9. During beta, promote staging to `main` once per release after the staging check.

## 10. Data and migration rules

- Database changes are new migration files under `supabase/migrations`.
- Staging contains fictional seed data only.
- No real personal data goes into code, migrations, seed files or tests.
- The REPORT MASTER is imported from a local copy and is not committed to the repository.
- Before launch, POC real data is either re-entered in production or moved by a reviewed script, then the POC data is deleted.

## 11. Quality approach

- Test each task locally against its definition of done.
- Include API-level tests that expect refusals where server-side rules must be enforced.
- Use two staging testing sessions during the build window.
- During beta, test each release on staging before production.
- Use BRS acceptance criteria AC-01 to AC-30 as the acceptance test script.

## 12. Change management

New requests are logged in `BACKLOG.md` as **Proposed**. During beta, they are considered at two-week release planning and either added with an explicit trade-off or deferred. Scope is not added in the middle of an active task.

## 13. Key risks

- Build window has little slack beyond its buffer.
- Long AI work may exceed normal web-request limits.
- POPIA review may not finish before beta.
- Launch scope excludes several Must requirements.
- Details from other matters could leak into a draft.

Mitigations and the complete RAID register should be maintained in `RAID.md`.
