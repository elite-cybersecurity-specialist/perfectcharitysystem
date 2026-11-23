# Development status

## Current package

PCS is approximately **20% complete**, as stated in the repository. The clarified operating rules describe the intended design. This full repository package integrates the presentation and documentation while preserving the application baseline.

The exact GitHub source commit, file hashes and presentation changes are listed in [Package contents](../PACKAGE-CONTENTS.json).

## Components present in the source

| Area | Present components |
| --- | --- |
| Participation | Donor registration, roles, representative-created receiver/organisation accounts and profile fields. |
| Purchases | Purchase requests, approval, receipt upload, status changes and receiver confirmation. |
| PCS | Wallet fields, transfer helpers, a hash-linked ledger, 10,000 PCS monthly credit and manual coin additions. |
| Projects | Descriptions, attachments, targets, project pages and internal PCS donations to project owners. |
| Oversight | Inspector interfaces for account management, locations and manual coin-addition audit entries. |
| Presentation | Fourteen aligned core visuals, the official ECS card, seven editable diagrams and the staged README. |

These are source components, not a claim of successful end-to-end operation.

## Intended rules requiring completion or validation

| Rule | Remaining work |
| --- | --- |
| Receiver eligibility | Structured interview/approval evidence and enforcement of required profile information. |
| Single payment release | Original-payment matching and uniqueness across separate requests; atomic, idempotent completion. |
| Net-value PCS | Provider deductions, currency conversion, preserved rate/source/time and net-value calculation. |
| Monthly exception requests | Evidence submission, review and approval beyond the existing credit and manual addition mechanisms. |
| Profile accountability | Complete privacy enforcement, public receiver contribution histories, volunteer records and mandatory earnings disclosure. |
| Inspector accountability | Country uniqueness and the complete controlled-access/action-history policy. |
| Ledger integrity | Unified balances, validated history, reconciliation and independent checkpoints. |
| Startup | Consistent package imports, dynamic module loading, scripts, dependency setup and container entry points. |

## What this package validates

Packaging checks verify source provenance, preservation of code and template files, syntax parsing of Python sources, image integrity, local Markdown links, navigation anchors and ZIP contents.

No application changes, payment-provider integration, real-funds processing, runtime scale test or production deployment is claimed by this documentation release.

## Next implementation order

Resolve startup integration and a single authoritative transaction record. Then complete payment matching and destination verification, monthly exceptions, inspector enforcement, public profile/earnings behaviour and independent ledger verification.

Keep the core participant experience simple throughout: choose, pay directly, provide evidence, receive confirmed PCS and optionally donate onward.
