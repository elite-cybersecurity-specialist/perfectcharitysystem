# PCS: five simple safeguards for the next build

These are recommended implementation steps for the existing model. They are not claims that the current code already implements them. They do not require PCS to become a payment processor, create another country inspector account or introduce a tradable token.

## 1. One external payment, one completed release

Keep both timestamps: the original external payment time and the receipt upload time. Match the payment against the receiver's actual account record, including provider reference, destination, currency and amount.

Mark that external transaction as used when the purchase completes. A new upload time or a different receipt filename must not make it a new payment. A reliable provider transaction reference is the simplest identifier. If it is unavailable, the authorised team must match and reserve the actual statement entry before confirmation; a receipt image alone is insufficient.

Complete the purchase status, balance updates and ledger entry as one operation. Repeated confirmation of the same purchase returns its existing result without releasing more PCS. This also prevents a double release caused by overlapping requests.

## 2. Verify the destination and record changes

Check that the designated payment destination belongs to the approved receiver or approved organisation. Keep its verification record.

A change requires receiver acknowledgement, a reason and a management check independent of the person making the change. Notify the receiver and retain the before-and-after details for authorised review. Preserve the destination agreed for each existing purchase rather than silently changing it.

## 3. One protected inspector account per country

Enforce a unique country assignment for the inspector role. Protect the national account with MFA and an identified accountable custodian. Give it only the permissions required for its duties.

Log privileged actions with the account, target, time, reason and relevant changes. A hidden public account remains visible to authorised audit. Management can review sensitive actions through its own assigned responsibility without adding a second country inspector.

## 4. Review exceptions and disclose relevant relationships

Keep routine approved work simple. Require a second authorised management review for exceptional PCS additions and sensitive payment-destination or related-party decisions.

Record the requested action, responsible actor, reason, supporting evidence and approval. Identify supplier ownership and relevant relationships when reviewing project spending. Publish the financial disclosure required by the SOPs while restricting sensitive documents appropriately.

No review can authorise directors to profit from donations. A reason field or public earnings entry does not override the prohibition.

## 5. Verify the ledger and reconcile balances

Use one authoritative transaction record to derive balances. Verify block hashes and links when loading history, and reject or quarantine inconsistencies rather than silently accepting them.

Retain recoverable backups and a separately verifiable, timestamped checkpoint of the ledger. This makes later alteration detectable outside the live application's own storage.

Reconcile confirmed external payments, internal PCS movements, issuance and project records. Financial reports must not count internal circulation as fresh cash assistance.

## Smallest practical implementation order

First implement payment uniqueness, a single completion operation and verified destinations. Then enforce the national inspector limit and sensitive-action review. Add ledger validation, reconciliation and independent checkpoints before handling real funds at scale.

These controls reinforce the original logical flow: direct payment, verified receipt, internal PCS transfer, onward donation and the next fresh purchase.
