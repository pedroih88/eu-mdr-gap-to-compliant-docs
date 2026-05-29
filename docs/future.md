---
layout: page
title: "Future Improvements"
permalink: /docs/future/
---
### Near-term (next version)

**Persistent state via export/import.** The session-only architecture's most significant practical limitation is that work is lost when the browser is closed. A defined export-to-JSON / import-from-JSON workflow — or a structured PDF export of the current state — would allow teams to maintain continuity across sessions without introducing server infrastructure.

**Expanded gap item coverage.** The current 55-item baseline covers the highest-frequency compliance obligations for Class IIa/IIb medical devices. Coverage gaps remain in: Article 120 legacy device transitional provisions with device-specific nuance, SaMD (Software as a Medical Device) under MDCG 2019-11, Class III device-specific requirements, and IVD-specific EUDAMED obligations for Class C and D devices.

**Regulatory update automation.** The Regulatory Updates log is currently maintained manually. A structured prompt-to-log workflow — or an integration with EUR-Lex change notifications — would reduce the risk of regulatory updates being missed between periodic reviews.

### Medium-term

**Multi-device portfolio view.** The current tool tracks compliance for a single device or product line. Consulting firms and larger medtech organisations managing portfolios of 5–50 devices need a parent-level view that aggregates RAG status and deadline exposure across devices, with drill-down to the device-level gap matrix.

**NB submission readiness report.** The Summary Dashboard is formatted for internal management review. A parallel output formatted for Notified Body submission — organised by MDR Annex rather than functional area, with supporting evidence mapped to each requirement — would reduce the manual assembly work at the point of NB engagement.

**Integration with QMS platforms.** The tool currently operates as a standalone file. An API-based integration with QMS platforms (Veeva Vault, Qualio, SimplerQMS, MasterControl) would allow gap items and action tracker entries to flow directly into the organisation's existing document control and CAPA workflows, rather than being managed in parallel.

**Validated SaaS deployment.** The single-file architecture solves the deployment constraint for early adoption but is not the right architecture for teams that need role-based access, concurrent editing, and server-side audit logs. A validated SaaS deployment — with the same functional specification and a full IQ/OQ/PQ validation package — would serve teams that have moved past the procurement stage and need a production-grade system.

### Longer-term

**Regulatory change impact analysis.** When a new regulation or MDCG guidance document is published, the relevant gap items should be automatically flagged for re-review. A retrieval-augmented generation (RAG) layer over EUR-Lex and MDCG documents — with human review gating — could support this, surfacing which items in the gap matrix are affected by a given regulatory change.

**Benchmarking and anonymised aggregate reporting.** With appropriate data governance, anonymised aggregate data from multiple organisations' gap matrices could support industry-level benchmarking — showing, for example, that PMCF gap closure rates are significantly lower than QMS gap closure rates across the sector, or which functional areas carry the highest unresolved critical items at a given date.

---

*This document is provided for public reference. It describes the design rationale, tooling, and development experience behind the Gap to Compliant framework. It does not constitute regulatory advice. The tool and all companion documents require review, customisation, and formal QA approval before use in a regulated environment.*

*Built with Claude (Anthropic) · May 2026*

