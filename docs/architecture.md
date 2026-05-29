---
layout: page
title: "Architecture and Tools"
permalink: /docs/architecture/
---
### Deployment Model

The tool is deployed as a **single standalone HTML file**. There is no server, no login, no installation, and no data transmitted outside the user's environment. It runs entirely in the browser. This was a deliberate design choice: the deployment constraint that consulting firms and lean medtech QA teams face most often is not access to software — it is the inability to get new software onto regulated or IT-controlled systems quickly. A single HTML file has no such barrier.

### Application Architecture

The application is structured around five functional modules, implemented as navigable tabs within the HTML:

| Module | Function |
|--------|----------|
| **Gap Matrix** | 55 pre-mapped gap items across 8 functional areas (Technical Documentation, Clinical Evaluation, PMS/PMCF, EUDAMED, QMS, Labelling, Cybersecurity, Transitional Provisions). Each item carries an impact rating, recommended action, and supporting evidence reference. Status dropdowns update live across all modules. |
| **Action Tracker** | Converts open gap items into remediable actions with owner, target date, and status fields. Drives the escalation view in the Summary Dashboard. |
| **Summary Dashboard** | Four-section management review output formatted to ISO 13485:2016 Cl. 5.6: (A) KPI tiles, (B) RAG status board, (C) deadline countdown table, (D) escalation items requiring management attention. Ready to present without additional preparation. |
| **APP Change Log** | Immutable record of every change committed to the tool — timestamp, action type, reason, author, and batch ID. Traceable to ISO 13485:2016 Cl. 4.2.5. |
| **Regulatory Updates** | Live log of MDR/IVDR regulatory events, each linked to a Change ID identifying the batch of app updates made in response. Closes the evidence chain from regulatory trigger to tool update. |

A **Usage Notice tab** provides permanent governance context: seven-point statement covering QA ownership, content customisation requirements, regulatory currency limitations, AI disclosure, and the validation requirement before regulated use.

### AI Tooling

The tool and all companion documents were prepared with the assistance of **Claude (Anthropic)**. AI was used to:

- Draft and structure the 55 gap items, including regulatory article references, impact ratings, and recommended actions
- Draft the Validation Plan and Test Protocols (VAL-PLAN-001), aligned to GAMP 5 Category 4 and ISO 13485:2016 Cl. 4.1.6 — including 30 IQ/OQ/PQ test cases with sign-off blocks
- Draft the Content Verification Protocol (VAL-ADD-A-001, Addendum A) — a three-layer human review framework
- Draft the Demo Script and Setup Guide
- Draft this Product Brief

**No AI-generated content is designed to enter the regulated record as fact without human verification.** The framework requires every statement to pass three human gates before QA approval:

- **CV-01 · Source Traceability** — a qualified RA reviewer checks every article reference, deadline, and obligation against current consolidated EUR-Lex and European Commission text
- **CV-02 · Benchmark Comparison** — RA and QA reviewers compare content against MDCG guidance and ISO 13485:2016 / ISO 14971:2019
- **CV-03 · Independent SME Attestation** — an independent subject-matter expert not involved in drafting attests to regulatory fitness; the QA Manager is the final approver

The prompt-to-record flow is: **Prompt → AI draft → Human verification (CV-01/02/03) → QA approval → Approved record.**

### Companion Document Set

| Document | Reference | Purpose |
|----------|-----------|---------|
| EU MDR / IVDR Gap Matrix (Full Version) | — | Primary tool with edit capability, add-item workflow, and full field-level audit trail |
| EU MDR / IVDR Gap Matrix (Lite Version) | — | Reduced feature set for demo, evaluation, and procurement review |
| Validation Plan & Test Protocols | VAL-PLAN-001 | GAMP 5 / ISO 13485:2016 Cl. 4.1.6 validation framework; 30 test cases |
| AI Content Verification Protocol | VAL-ADD-A-001 | Three-layer human review protocol for AI-generated regulatory content |
| Demo Script | — | Six-beat, 3-minute screen recording script with narration cues |
| Demo Setup Guide | — | Step-by-step data setup for a live and credible demo run |

---
