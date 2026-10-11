# Verified AI State Management — Public DLS Reference

**Maturity:** Educational prototype + conceptual architecture · **Status:** Published within the portfolio; standalone repository not yet created

> This is an **independently written public reference**, not the text of an internal operational standard or an active canonical-state router.

## What problem does it solve?

A long-running AI workflow needs to answer four different questions: **What is authoritative? What was executed? What was actually persisted and read back? What could be recovered later?** Treating any two as interchangeable creates errors when tools fail, work spans sessions, or state moves between providers.

## Core ideas

| Principle | Meaning |
| --- | --- |
| Authority ≠ execution route ≠ buffer location | Where content was produced or temporarily stored does not decide its canonical authority. |
| One accepted frontier per owner scope | An owner/scope has one accepted pointer, while multiple unpublished candidates may exist. |
| Prepared ≠ published ≠ accepted | Creating a candidate, moving a branch, verifying the data and authorizing it are separate events. |
| Readback before claims | A tool success message alone is not proof that the expected content is visible at the intended ref. |
| Recovery is selective | Valuable unaccepted material can be buffered; a retry packet does not automatically become canonical. |

## Run the synthetic demonstration

Only **Python 3.9+**, using standard-library modules:

```bash
cd architecture/dls
python examples/state_demo.py
python -m unittest discover -s tests -v
```

The code simulates an in-memory branch and owner decisions. It deliberately has **no live GitHub API access, tokens, file writes or external side effects**. The demo prints an accepted candidate, rejects a stale proposal, and shows a noncanonical recovery packet.

## Browse

- [Architecture and state transitions](docs/architecture.md)
- [Decisions and practical tradeoffs](docs/design-decisions.md)
- [Limits, threats and verification scope](docs/limitations.md)
- [Python demonstration](examples/state_demo.py) · [tests](tests/test_state_demo.py)
- [Release notes](CHANGELOG.md)

## Evidence and scope

**Internal observation:** Verified Git-based artifact publishing/readback and evolving governance contracts informed this public design. These records are not publicly replicated here.

**Public evidence:** The source and eight standard-library tests in this directory can be independently inspected and executed. Passing them proves only the behaviors of this teaching model.

**Not claimed:** A production-ready repository integration, distributed transactional guarantee, automatic authority transfer, end-to-end scheduler reliability, or a complete security model.

**Relationship:** [Portfolio](../../README.md) · [Publication policy](../../publication-policy.md). Source operational authority remains outside the public portfolio. No third-party data or private paths are copied.

**License:** No open-source license has been selected; viewing public source does not imply unrestricted reuse.