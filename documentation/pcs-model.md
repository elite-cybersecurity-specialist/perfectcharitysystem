# PCS: the donation cycle

This document describes the clarified Perfect Charity System concept. Implementation is approximately 5% complete; the operating model and its prototype implementation must be distinguished.

## What moves

Two things move through different channels:

| Movement | Channel | Recipient |
| --- | --- | --- |
| External money | A participant-selected bank or existing payment provider | The chosen receiver's designated external account |
| Internal PCS | The PCS platform and its transaction records | The buyer, then any eligible receiver the buyer chooses to support |

PCS does not build or operate a fiat payment gateway. All authorised charity activity still follows the PCS workflow and must be recorded. External processing does not authorise unrecorded side collections.

## The repeating sequence

1. An interviewed and approved receiver has a public profile and an allocated PCS balance.
2. A donor selects that receiver and a supported external payment method.
3. The donor pays the receiver directly and submits payment evidence through PCS.
4. The receiver or authorised internal team verifies the actual payment received.
5. PCS moves from the receiver's balance to the donor's balance after confirmation.
6. The donor can donate those units to another eligible receiver.
7. A new donor purchases PCS from that receiver through a new direct payment. The sequence continues.

The first purchase already helps the initial selling receiver. An onward gift transfers internal PCS; the next receiver obtains external money when another buyer pays them. The flow depends on continued donor participation rather than a promise of guaranteed redemption.

## Worked example: two fresh payments, the same 100 PCS

1. Donor A pays Receiver A a confirmed net value of 100 USDT; Receiver A transfers 100 PCS to Donor A.
2. Donor A donates those same 100 PCS to Receiver B. No fresh external money is paid at this step.
3. Donor B pays Receiver B a fresh confirmed net value of 100 USDT; Receiver B transfers those same 100 PCS to Donor B.

The receivers have received **200 USDT net assistance from two fresh payments**, while **the same 100 PCS circulates**. Internal circulation is recorded separately and is not counted again as new money received. Participants may use an available local-currency method; each purchase is valued from the confirmed net receipt.

## Value, fees and currency

The valuation reference is **1 PCS = 1 USDT**. PCS is not externally tradable and does not provide an external exchange or redemption mechanism. The reference does not require every participant to pay in USDT or imply a USDT reserve backing every allocation.

Internal PCS credit follows the confirmed **net payment value received** after external deductions. The records must distinguish gross payment, external charges, net received amount, original currency, conversion reference and resulting PCS amount.

The universal local-currency conversion source and timestamp policy remain to be finalised. For implementation, use one published conversion policy across users, preserve the rate and source with each transaction, and disclose actual provider conversion charges. Do not silently treat USDT and USD as identical.

## Minimum purchase record

Record the purchase ID, donor and receiver IDs, designated payment destination, provider, original transaction reference where available, original payment timestamp, upload timestamp, amount and currency, net value, evidence reference, confirming actor and time, PCS amount, status and ledger reference.

The original payment timestamp and the receipt upload timestamp are different fields. Re-uploading evidence must not authorise a second release for the same external payment. The simple recommended enforcement is described in [Simple controls](pcs-simple-controls.md).

## Issuance and accounting

The standard monthly receiver allocation is **10,000 PCS**, valued against the **1 PCS = 1 USDT** reference. Requests for additional PCS require a stated need, supporting evidence, review and recorded approval.

Receiver PCS allocations and exceptional additions must be recorded separately from external financial assistance. The prototype credits the standard amount monthly and can accumulate missed credits; the monthly allocation is not a hard total-wallet ceiling or a guarantee of external money received. The complete evidence-backed exception process still requires implementation.

Report these separately:

- Fresh external assistance actually received by each receiver.
- Internal PCS purchases, donations and transfers.
- New PCS allocations and exceptional additions.
- Internal operating support, expenditure and balance.
- External project support, expenditure, delivery and relevant earnings.

An internal transfer does not count again as new cash received. Public financial records should make these distinctions visible without publishing sensitive raw documents unnecessarily.

## Corrections

Preserve the original transaction. A management-authorised correction is a new recorded PCS transfer to the donor, without a PCS return-transfer charge. Record its reason, approving actor and link to the original event. Any handling of external money follows the external provider's process and must be separately documented.

## Source of the concept

The repository's README and this document take priority for the clarified donation model. Historical engineering notes may describe an earlier design. Changes to the concept must preserve direct assistance, separate operating support, non-tradable internal PCS and public accountability.
