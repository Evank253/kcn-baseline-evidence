# BTP-001 Signature Check: Result Record

Repo: Evank253/kcn-baseline-evidence
Commit: 0cd5bc4acd5565a1b60537bcf1573aaaafd9e122 (clean working tree)
Raw verify output: gpg_verify_raw_status.txt (sha256 in MANIFEST.sha256)

## Results

| Check | Result | Basis |
|---|---|---|
| Detached signature verifies over sign-off bytes | PASS | GOODSIG, VALIDSIG; signature made 2026-10-19 04:21:50 UTC; gpg exit 0 |
| Signing key fingerprint | 827B 5E62 05B5 8529 F1E2 FDCD FF81 7AEE AC19 C76A | key_fingerprint.txt |
| Key identity (owner is Evan Ketchum) | verified | Key was obtained only from the same repo. GPG reports trust. trust level updated to ultimate. On October 24th 2026. after local certification of key 827B5E6205B58529F1E2FDCDFF817AEEAC19C76A |
| Out-of-band fingerprint match |out-of-band fingerprint match confirmed locally on October 16th 2026 | User reports a byte-for-byte match. Evan Ketchum compared at the fingerprint generation october 16th 2026. |
| Sign-off content reviewed | YES | Signature covers bytes only. content assessed by human authority on October 24th 2026. |
| CI run 38671286790 | NOT FOUND in this repo | Out of scope for this step. |

## Limits

- A valid signature shows the sign-off bytes match the key in the repo. It does not show who controls the key.
- The independent root of trust is the out-of-band fingerprint check. Its reference must be recorded (Source: local Gpg4win keygen session, Channel local in-person , date October 16th 2026., person: Evan Ketchum ) this result is cited as independently verified.
- The sign-off's section 6 fields (signature verification result, independent retrieval) are unchanged. The signed file was not edited.
