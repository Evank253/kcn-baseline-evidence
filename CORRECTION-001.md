# CORRECTION-001: Manifest filename typo and BTP-001 evidence file cleanup

Issue recorded: 2026-10-20
Correction finalized: 2026-10-24

## Error
1. **Manifest filename typo:** The repository owner reported that the canonical manifest filename is **Manifex.sha256**, not `MANIFEST.sha256`.
2. **File/digest mismatch on `main`:** Commit `b252703` added `Manifex.sha256` containing the true SHA-256 digests of the raw verification artifacts, paired with unprefixed filenames. Commit `ad12e74` subsequently added a reconstructed placeholder transcript (`gpg_verify_raw_status.txt`), a human-readable single-line fingerprint file (`key_fingerprint.txt`), an unauthorized `input_sha256.txt`, and a hashless Markdown `MANIFEST.sha256`, causing `sha256sum -c Manifex.sha256` to fail on `main`.

## Legacy filenames retained in existing records
Original result and reference lines are left unedited so historical wording is preserved; read them with this correction in mind:

- **`RESULT.md`** (original 22 lines unedited; 1 pointer line inserted at line 6, shifting subsequent lines down by 1):
  - **Line 5:** `Raw verify output: gpg_verify_raw_status.txt (sha256 in MANIFEST.sha256)` — superseded by `btp001-gpg-verify-raw-output.txt` and `Manifex.sha256`.
  - **Line 13** (line 12 prior to this commit): `| Signing key fingerprint | ... | key_fingerprint.txt |` — superseded by `btp001-signing-key-fingerprint.txt`.
  - **File SHA-256 update:** Inserting the line 6 pointer updates `RESULT.md` from `8ba5508ad557f055923273c5ef81288855c78d3a4b1afe5b2eb14ccba9df0253` (cited as `8ba5508a…0253` in `oob-fingerprint-reference.md`, line 16) to `a43641af2152db8448f0fd3e5d6a6d8aed4c6f32f14375e82060e3adc99af719`.
- **`oob-fingerprint-reference.md`** (kept completely untouched; `sha256`: `10738d4e6732ae1288242e2a93610f8125d2371d81340123c4aa9ca22b3654bf`):
  - **Line 3:** names `gpg_verify_raw_status.txt`, `input_sha256.txt`, `key_fingerprint.txt`, and `repo_head.txt`.
  - **Line 9:** `git add MANIFEST.sha256 gpg_verify_raw_status.txt input_sha256.txt key_fingerprint.txt repo_head.txt`.
  - **Lines 14 & 16:** reference leaving `RESULT.md` untouched at its pre-pointer digest `8ba5508a…0253`.

## Evidence files in this commit (verified by `Manifex.sha256`)
- **`btp001-gpg-verify-raw-output.txt`** (`sha256`: `2414fce030e12d41c83c40b85e2095d1f3496b6c3e37cfe861f20ea719cce45c`): Real `gpg --status-fd 1 --verify` transcript for `BTP-001-sign-off.md.asc` over `BTP-001-sign-off.md` (`GOODSIG` / `VALIDSIG`, primary EdDSA signing key `827B5E6205B58529F1E2FDCDFF817AEEAC19C76A`, email `evan.ketchum2000@gmail.com`). Includes an appended `gpg_exit=0` line at the end; the digest in `Manifex.sha256` is computed over the final 968 bytes including that line.
- **`btp001-signing-key-fingerprint.txt`** (`sha256`: `9a7a37e191a37bc3955cb11277190936d57abad0780f29a289b16bd7cb25c618`): `gpg --with-colons --fingerprint` `fpr:` lines for the primary Ed25519 signing key (`827B5E6205B58529F1E2FDCDFF817AEEAC19C76A`) and Curve25519 encryption subkey (`66DFF8782A494C5C7E53C88607E3BEB70E59478A`).
- **`btp001-repo-head-commit.txt`** (`sha256`: `53d06b878f18ce1b45588176628a940178cc33d47ebdb1b8f9773d46825b7fcf`): Renamed byte-for-byte from `repo_head.txt`. Records commit `0cd5bc4acd5565a1b60537bcf1573aaaafd9e122` (`0cd5bc4`), the clean-tree repository `HEAD` at which detached signature `BTP-001-sign-off.md.asc` was added and verified (note: `0cd5bc4` itself is an unsigned git commit).
- **Omitted file (`btp001-input-sha256.txt` / `input_sha256.txt`):** Not included in this commit, and its `e4735701...` entry is removed from `Manifex.sha256`. The repository owner reverted `input_sha256.txt` in `dac3c96` as *"added without authorization"*; a carry-over copy under `btp001-input-sha256.txt` in an earlier local draft was removed.

## Files removed or deprecated in this commit
- **`gpg_verify_raw_status.txt` (removed):** Reconstructed placeholder (`sha256`: `03a18c65a8ca2837b44ac11bb46b8151d1702e84984545167bb6d4a1a906d36e`) that mismatched the real transcript digest (`2414fce0...`) already recorded in `Manifex.sha256` on `main`. Replaced by `btp001-gpg-verify-raw-output.txt`.
- **`key_fingerprint.txt` (removed):** Held only the spaced human-readable primary fingerprint (`827B 5E62 05B5 8529 F1E2 FDCD FF81 7AEE AC19 C76A`, `sha256`: `fa5558330233b9d80b243546e425831fd7186ca15d0223433b3352bdda82aafb`), mismatching the `9a7a37e1...` digest in `Manifex.sha256` on `main`. Replaced by `btp001-signing-key-fingerprint.txt`, which carries the identical primary fingerprint in GPG colon format plus the encryption subkey.
- **`repo_head.txt` (renamed/removed):** Renamed without byte changes (`sha256`: `53d06b87...`) to `btp001-repo-head-commit.txt`.
- **`MANIFEST.sha256` (deprecated):** Listed filenames in Markdown without hashes. Replaced with a deprecation notice pointing to `Manifex.sha256` and `CORRECTION-001.md`. `Manifex.sha256` is the only active manifest.

## Attribution note
The reverts `dac3c96` and `e6e804b` on `main` were authored directly by `evan ketchum`, not by the agent that prepared the evidence draft.

## Verification
`sha256sum -c Manifex.sha256` returns `OK` for all three listed files.
