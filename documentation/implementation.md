# Implementation and architecture

The application source in this package is preserved from the GitHub baseline identified in [Package contents](../PACKAGE-CONTENTS.json). This documentation refresh does not change transaction logic, authentication, models or application templates.

## Source responsibilities

| File | Responsibility |
| --- | --- |
| [pcs-website.py](../codes/pcs-website.py) | FastAPI website, Jinja templates, user/session routes, purchase requests, receipt upload and confirmation, monthly credits, projects and inspectors. |
| [perfectcharitysystem.py](../codes/perfectcharitysystem.py) | API application and loading of the profile, wallet and ledger modules. |
| [pcs-crypto.py](../codes/pcs-crypto.py) | Prototype blocks, transactions, hash calculation, balance lookup and serialisation. |
| [pcs-wallet.py](../codes/pcs-wallet.py) | Wallet summaries and helper operations. |
| [pcs-profiles.py](../codes/pcs-profiles.py) | Profile objects and profile management helpers. |
| [pcs_persistence.py](../codes/pcs_persistence.py) | JSON-backed data and model path utilities. |
| [pcs_ai.py](../codes/pcs_ai.py) | Security assessment and monitoring code with optional machine-learning dependencies. |

## Current source workflow

The website contains donor registration, representative-created receiver accounts, purchase request approval, receipt upload and receiver confirmation. Confirmation updates account balances and attempts to record the associated PCS movement.

The monthly credit function adds 10,000 PCS for receiver and charity-organisation roles and can catch up missed months. Manual coin additions record an inspector action and reason. This provides part of the basis for the intended monthly-allocation and justified-exception policy; a complete request/evidence/approval workflow remains to implement.

Project pages support descriptions, files, targets and internal PCS contributions to project owners. Public profile templates, volunteer achievements and financial disclosure need completion and validation against the clarified rules.

## Payment processing boundary

External providers handle the actual payment. Receipt submission and confirmation belong to PCS. There is no implemented PCS-owned fiat payment gateway to operate or advertise.

The intended valuation is based on net external value received against the USDT reference. The current entered purchase amount is not a completed fee, FX and net-value accounting implementation.

## Integration work

The hyphenated module filenames, package-relative imports, dynamic loading and launchers must be made consistent. Existing entry points in startup scripts and Docker definitions do not all match the current source layout.

The account wallet fields and ledger-based wallet helpers require one consistent source of transaction truth. Purchase completion must update status, balances and ledger history atomically and idempotently.

History loading must validate hashes and links, and the independently verifiable checkpoint and reconciliation mechanisms must be added. Country inspector uniqueness, complete earnings disclosure, volunteer achievements and privacy enforcement remain implementation work.

This is an architecture description, not a successful end-to-end runtime or production-readiness claim. See [Development status](development-status.md) and [Simple controls](pcs-simple-controls.md).
