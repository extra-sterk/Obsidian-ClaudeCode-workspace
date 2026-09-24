---
name: finance
description: Analyze personal financial accounts, balances, transactions, cash flow, spending, and financial records through available read-only sources such as Plaid exports or tools.
---

# Finance

Requires an authorized financial data source or local export.

Treat Plaid and similar services as data sources for a broader finance workflow. Obtain account meanings, ownership, preferred groupings, currencies, and provider-specific configuration from Context.

## Default boundary

- Default to read-only analysis. Do not initiate transfers, payments, trades, account changes, or new data connections without explicit instruction.
- Request only the provider products and fields needed for the task. Avoid identity, routing, and full account-number data when transaction and balance data are sufficient.
- Keep credentials and access tokens in the configured secret store or environment; never include them in reports or saved exports.

## Analysis discipline

- State the source, retrieval time, covered date range, and any known incompleteness.
- Distinguish pending from posted transactions and avoid double-counting internal transfers, refunds, reversals, and credit-card payments.
- Preserve original currency and sign conventions; explain any normalization.
- Use deterministic calculations for totals, reconciliation, and projections. Check subtotals against source totals where possible.
- Separate observed facts from classifications, assumptions, and advice.
- Redact full account identifiers in user-facing output unless specifically needed.

For repeated analyses, prefer a normalized local read-only dataset so provider quirks remain in the ingestion layer rather than the reasoning workflow.
