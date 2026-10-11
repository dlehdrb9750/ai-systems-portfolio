# Case Study: Research Continuity Across Execution Routes

**Category:** AI research operations · Long-running context · Evidence provenance  
**Maturity:** Independently written and publicly reproducible *synthetic* workflow demonstration  
**Evidence:** [GitHub Actions — 21 tests passed](https://github.com/dlehdrb9750/ai-research-automation/actions/runs/38137612538) · 2026-10-11

## 1. The problem

Research work can extend over multiple sessions and tools. A batch may produce a draft, fail to save, or run under a scheduled producer rather than the normal interactive writer. Treating a scheduled execution record, a generated note, a stored file, an Owner-accepted batch and an accepted substantive finding as equivalent leads to misleading status reports and potentially duplicated work.

## 2. Architecture choice

**[AI Research Automation & Continuity](https://github.com/dlehdrb9750/ai-research-automation)** is a clean-room public educational application of general-purpose workflow, state and evidence-management concepts.

It models:

- Per-track research goals and explicitly registered source provenance.
- Interactive publication candidates versus noncanonical scheduled-route producer packets.
- Readback and explicit Owner admission before the accepted research frontier advances.
- Independent progress across tracks when one attempt fails.
- Unknown-effect reconciliation, genuinely distinct alternate attempts, and selective recovery.
- Noncanonical Issue-like coordination references and JSON state handoff.

## 3. Public demonstration

The script uses two **fictional** tracks and `example://` source identifiers. One produces an interactive note. Another creates a synthetic scheduled producer packet; its frontier does not move until a separate, simulated publication, readback and Owner admission occur. A transient failed attempt is replaced by a new in-scope approach and resumed via checkpoint.

The synthetic study note remains an **unaccepted substantive hypothesis** even after the fictional research batch is admitted.

## 4. Verified versus unverified

**Verified:** The public Python demonstration and its **21 unit tests passed** in [GitHub Actions](https://github.com/dlehdrb9750/ai-research-automation/actions/runs/38137612538). This is public evidence for the local state transitions.

**Not verified by this demo:** A real LLM researching automatically, a real scheduled task running, a provider handoff, a remote GitHub write, independent source fact-checking, scientific conclusion quality, or any measured improvement in research efficiency.

The separately operated private research systems are **not reproduced** here. Actual operational entrypoints and scheduled executions retain their own Owner-controlled authority.

## 5. What a next evaluation needs

A stronger public evaluation would use consented, non-sensitive sources and an authorized scheduler, verify a real research producer handoff to disposable storage, compare accepted readback against source evidence, and measure recovery across interruptions.

**Disclosure:** This case study contains no private research findings, investment strategies, personal information, account-specific scheduling configuration or proprietary production history.
