# Case Study: From Audit Findings to System Improvement

**Category:** AI quality assurance · Recursive improvement  
**Maturity:** Independently written and publicly reproducible *synthetic* demonstration  
**Evidence:** [GitHub Actions run — 16 tests passed](https://github.com/dlehdrb9750/ai-audit-and-improvement/actions/runs/38137191873) · 2026-10-11

## Problem

AI output can appear complete despite missing references. A reviewer may correct one affected artifact without learning why similar defects recur. Conversely, repeated failures are not automatically proof of a single systemic cause.

## Architecture choice

Two roles are intentionally separated:

- **AUDS:** verify which evidence was inspected; record findings without suppressing the original defect; allow R1 repairs with verification.
- **RIS:** group observations from different artifacts/cycles as *hypotheses*, attach rationale, and propose L1–L3 improvements, preserving the human's decision rights.

This prevents a local repair from being mistaken for systemic remediation, and a proposed system redesign from being mistaken for an applied change.

## Public demonstration

The [AI Audit & Improvement public reference](https://github.com/dlehdrb9750/ai-audit-and-improvement) uses two fictional public-information reports that both omit a citation. A separate formatting issue receives an R1 correction with its original finding preserved. Repeated citation omissions generate an unconfirmed R2 candidate and a proposed additional citation check.

The user-facing output labels the proposal `APPROVED_NOT_APPLIED` after a simulated authorized decision. **No real service or rule is changed** by this demo.

## Observed evidence

The published Python code and GitHub Actions job execute the example and standard-library unit tests. The [public CI log](https://github.com/dlehdrb9750/ai-audit-and-improvement/actions/runs/38137191873) reports **16 tests passed**.

This demonstrates the state machine's behavior under synthetic inputs. It does **not** validate audit accuracy, establish a real shared cause, prove AI quality gains, or certify the supplied evidence references.

## Next meaningful verification

A future extension could use consented public documents with independently checkable citations, assess reviewer agreement, and compare whether the proposed improvements reduce observed repeat defects.

**Disclosure:** No private research, internal logs, or protected data were copied into this public case study.
