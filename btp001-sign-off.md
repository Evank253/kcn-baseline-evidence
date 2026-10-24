# BTP-001 — Patch Evidence Verification and Human Sign-Off (Unsigned Draft)

Document: BTP-001 Patch Artifact Sign-Off (`btp001-patch`)
Status: UNSIGNED DRAFT — PENDING EXTERNAL HUMAN SIGNATURE
Repository: https://github.com/Evank253/kcn-baseline-evidence
Canonical baseline policy sign-off (separate file, untouched): `BTP-001-sign-off.md` (`sha256`: `e04d03f999e7af738ff0b13e08838128042b89cb45e723d5832285dd09abaf51`)

## 1. Referenced Repository State and Artifact

- Branch: `btp001-patch`
- Commit: `324282d1ec3298d16ed64b382ba20293e75c178f` (`324282d`)
- Commit subject: `Rename 0001-btp001-evidence-correction.patch to scratch/btp001-patch.patch`
- Commit date: `2026-10-24 14:37:49 -0700`
- Artifact path: `scratch/btp001-patch.patch`
- Artifact size: `11118` bytes (`LF` line endings)
- Verified SHA-256 digest: `33ec196e37a2834ddd4ad47595d4edeeff0033f0163a07e3658eb41202afd8f7`

## 2. Measured Pre-Sign-Off Checks

- Remote fetch & `sha256sum scratch/btp001-patch.patch`: PASS (`33ec196e37a2834ddd4ad47595d4edeeff0033f0163a07e3658eb41202afd8f7`)
- Byte-for-byte comparison (`cmp -l`) against local `0001-btp001-evidence-correction.patch`: PASS (`0` differing bytes, `exit=0`)
- Tampered digest rejection check (`...9534...` vs. measured `...95d4...`): MISMATCH DETECTED (`diff` `exit=1` at hex character 27)
- Clean `git am` application against `main` (`e6e804b39e90e97ad63e93ce40456e6edc0256a2`) and `sha256sum -c Manifex.sha256`: PASS (`OK` for all 3 `btp001-*` files)

## 3. External Human Authority Attestation

- Approving authority / key custodian: Evan Ketchum
- Required signing key fingerprint: `827B 5E62 05B5 8529 F1E2 FDCD FF81 7AEE AC19 C76A`
- Decision: PENDING HUMAN REVIEW AND SIGNATURE
- Decision date and time: PENDING
- Detached signature artifact (`btp001-sign-off.md.asc`): NOT YET CREATED
- Signature verification result: NOT_MEASURED (unsigned draft)

## 4. Signing Boundary Notice

This file was drafted in an agent workspace that holds neither the private signing key nor human ratification authority under `BTP-001-sign-off.md`. It becomes a signed attestation only after Evan Ketchum reviews the exact bytes of this file, updates Section 3 if desired, and produces a detached OpenPGP signature using hardware-backed key `827B 5E62 05B5 8529 F1E2 FDCD FF81 7AEE AC19 C76A`.
