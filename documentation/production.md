# Production preparation

PCS remains an approximately 5% complete prototype. This repository package is complete as a source and presentation snapshot; production application completion is a separate engineering task.

## Resolve the application entry point first

The current startup scripts, dynamic imports and container commands need alignment with the actual module layout. Validate a local startup before building a public deployment. Existing Docker and reverse-proxy files are engineering starting points.

## Complete the charity workflow

Implement and verify the rules in [PCS model](pcs-model.md), [PCS governance](pcs-governance.md) and [Simple controls](pcs-simple-controls.md):

- Verify receiver eligibility and designated payment destinations.
- Match actual external payments and prevent a second PCS release for the same payment.
- Commit purchase completion, balance changes and ledger records consistently.
- Apply the 10,000 PCS standard monthly allocation and the evidence-backed exception process.
- Enforce one inspector account per country and record privileged actions.
- Complete donor privacy, receiver contribution histories, volunteer achievements and relevant earnings disclosure.
- Separate assistance, operating funding, projects, issuance and internal circulation in reports.
- Validate history and reconcile records, with recoverable backups and independently verifiable checkpoints.

## Prepare the deployment boundary

Use deliberate configuration for the environment, authenticated administrative access, controlled upload access, protected session credentials, HTTPS and monitored storage. Test restart and recovery against the same verified ledger and balances.

The existing multi-worker container configuration must not be treated as proof that process-local account and wallet state is safe across workers. Resolve shared-state and concurrency behaviour before selecting the deployment process model.

## Demonstrate readiness

A release should report the tests actually run: clean-environment startup, complete purchase flow, repeated-confirmation handling, privacy and inspector permissions, net-value accounting, monthly limits, corrections and restore/reconciliation.

Record measured results and the precise supported scope. Do not infer support for hundreds of thousands of users from file presence, source comments or an untested server configuration.

See [Development status](development-status.md) for the current boundary. The new README and image assets can be published independently of public deployment of the application.
