# Signature Refusal Test — Reused Signature Rejection

**Status:** PASS (locally observed)
**Date recorded:** 2026-10-19

## What was tested

A production BTP-001 detached signature (covering sign-off bytes in kcn-baseline-evidence) was presented against clone content — bytes the signature was never made over.

## Expected behavior

Verification recomputes the hash of the presented bytes, compares against the claimed signature, and rejects on mismatch without human intervention.

## Observed result

Refusal. The ledger/verification path rejected the reused signature.

## What this proves

- Hash recomputation is live, not decorative
- Mismatch detection does not depend on a human noticing
- The verification logic fails measured rather than failing open or closed

## What this does not prove

- Automated capture of the refusal as a ledger event (the run was local/session-only)
- Behavior under a different key, different algorithm, or partial-byte corruption

## Next step

Re-run inside the clone test harness so the refusal becomes a recomputable evidence event in the evidence root.
