# BTP-001 — External Authority Decision and Sign-Off

Document: Baseline Trust and Key Lifecycle
Version: 1.0
Decision status: PENDING EXTERNAL HUMAN AUTHORIZATION
Purpose: Establish the documented human decision required before BTP-001 can be ratified and its genesis governance-ledger record created.

## 1. Signing-Key Protection

Select one:
- Hardware-backed signing key.
- Dedicated signing service with restricted access and auditable signing operations.

Selection: Hardware-backed signing key.
Responsible custodian or service: Evan Ketchum

## 2. Independent Trust Channel

Select one:
- Independently authenticated, out-of-band public-key fingerprint verification.
- Separately controlled organizational trust registry.
- Other documented method, subject to explicit approval.

Selection: Independently authenticated, out-of-band public-key fingerprint verification.
Trust-channel owner: Evan Ketchum

## 3. Key Rotation

Select one:
- Human-approved rotation with an authenticated transition record.
- Human-approved rotation through an independently authenticated trust-anchor update.

Selection: Human-approved rotation with an authenticated transition record.
Approval authority: Evan Ketchum

## 4. Key Compromise and Recovery

Select one:
- Designated human authority approves revocation, impact assessment, and replacement trust-anchor establishment through an independent channel.
- Other documented recovery procedure approved by the designated human authority.

Selection: Designated human authority approves revocation, impact assessment, and replacement trust-anchor establishment through an independent channel.
Recovery authority: Evan Ketchum
Independent recovery channel: Evan.ketchum2026@outlook.com

## 5. External Authority Attestation

Decision-maker identity: Evan Ketchum
Authority basis: Project owner and sole administrative control of the evank253 GitHub account 
Decision: Approved
Decision date and time: October 16,2026. 12:06pm
Signature or attestation: Evan Ketchum

The decision-maker's authority must be established independently of this document and the governance ledger being initialized.

## 6. Independent Preservation

Approved artifact location:http://github.com/Evank253/kcn-baseline-evidence
Exact artifact digest: Pending calculation from final bytes
Independent retrieval result: NOT_MEASURED
Signature verification result: NOT_MEASURED

## 7. Genesis Ledger Record

The initial governance-ledger record may be created only after the external decision and applicable authority checks are verified.

Genesis record ID:http://github.com/Evank253/kcn-baseline-evidence
External authority artifact reference:http://github.com/Evank253/kcn-baseline-evidence
Verification evidence reference: Pending

The initial record must derive its trust from the verified external authority decision and independently retrievable artifact. It must not claim that the ledger establishes its own authority.

## Final Disposition

BTP-001 remains PROPOSED — NOT RATIFIED until the required selections are made, the authorized human decision is independently evidenced, and the ratification requirements are satisfied.

No signing key, trust anchor, genesis ledger record, or signed baseline tag is established by this template.

## Bootstrap Rule (Adopted in Conversation, 2026-10-16)

Initial Ledger Bootstrap Rule: The first authorized governance decision may instantiate the governance ledger and create its genesis record as part of the same controlled operation. The record must identify its approving authority, exact decision artifact, integrity metadata, and independent preservation location. Subsequent decisions must reference existing ledger records. No record may establish its own authority, and missing or unverifiable bootstrap evidence prevents ratification from being represented as complete.

## Approval Boundary

Approval selects the controls defined above. It does not prove that a key has been generated, that the trust channel is operational, that a signature is valid, or that the baseline has been independently verified. Those are subsequent implementation and evidence requirements.

BTP-001 becomes ratified only when the authorized human decision is validly recorded under the applicable governance procedure.
