---
layout: page
title: "Lessons Learned"
permalink: /docs/lessons/
---
### 1. The deployment constraint is the design constraint.

The single-file HTML architecture was chosen because it is the only format that works without friction in the environments where this tool is actually needed — regulated QMS environments, consultant laptops, and procurement reviews. Any architecture requiring installation, a server, or IT sign-off would have failed at the first obstacle. Starting from the deployment constraint produced a better, more honest design.

### 2. AI is fast at structure; it is not reliable for regulatory accuracy.

Claude produced well-structured, plausible-sounding regulatory content quickly. The problem is that language models generate by pattern — they do not verify article numbers against live EUR-Lex text, they do not know whether a deadline has been superseded by a subsequent regulation, and they can produce confident-sounding statements that are subtly wrong. Addendum A (the Content Verification Protocol) exists because this was discovered early, not assumed. The lesson: AI is a drafting accelerator, not a regulatory authority. Build the human review layer in from the start — do not retrofit it.

### 3. The audit trail requirement shapes the whole application.

Early prototypes treated the change log as a reporting feature. It is not — it is a foundational data integrity control under ISO 13485:2016 Cl. 4.2.5. When the log was treated as core infrastructure rather than an add-on, it changed how the pending changes modal, the commit workflow, and the batch ID system were designed. The lesson: understand the regulatory requirements that govern the tool before designing the tool.

### 4. A session-only architecture has real data integrity limitations.

The tool runs in the browser with no persistent server-side storage. Session state — status changes, tracker entries — is not automatically saved. Organisations using the tool in a regulated context must define a procedure for capturing or exporting session state at the end of each use session to satisfy ALCOA+ principles (Attributable, Legible, Contemporaneous, Original, Accurate). This was documented in the validation plan but was underappreciated in early design. This has since been addressed: the Lite version now provides an Export/Import (overlay) workflow and Print/PDF outputs for retaining and re-loading session state — see the changelog below.

### 5. Validation documentation is a first-class deliverable, not an afterthought.

The companion validation plan and test protocols were not written after the tool was built — they were developed in parallel. This forced precision about what the tool was supposed to do (the specification) before testing it. Teams that treat validation as a sign-off formality at the end of development consistently discover that their tool does things they did not intend and fails to do things they assumed. Building validation artefacts alongside the tool prevents that.

### 6. AI-generated regulatory content needs explicit provenance disclosure.

The Usage Notice tab and the "AI use & human oversight" section in the Product Brief were not optional additions — they are governance requirements. Anyone using this tool in a regulated environment needs to know that the content was AI-drafted and what the verification controls are. Concealing AI involvement in regulated document production is a data integrity failure, not a stylistic choice.

---
