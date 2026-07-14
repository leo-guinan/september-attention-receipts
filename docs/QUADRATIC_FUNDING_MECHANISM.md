# Quadratic receipt funding mechanism

Current rule:

- first valid, first-seen tweet ID: `1 QUAI` queued for manual payout;
- duplicate valid tweet ID: no immediate payout; creates a `validation_pending` signal;
- future matching can pay duplicates when they prove independent communication breadth.

## Why duplicates matter

The first receipt proves discovery. Later receipts prove propagation.

A duplicate from the same operator on the same surface in the same time window has low value. A duplicate from a different operator, different audience, later time window, or after visible engagement changed is a validation signal.

## Candidate matching formula

```text
validation_breadth(tweet) = unique_operators × unique_surfaces × time_separation_score
future_match(tweet) ∝ (Σ sqrt(valid_receipts_by_independent_operator))²
spam_discount = duplicate_same_operator_same_surface_same_window → near 0
```

The formula is intentionally not final. September reveal data should calibrate the weights.

## Custody boundary

No hot wallet is enabled. All payouts are queued for manual payment until a burner-wallet signer is deployed and hardened.
