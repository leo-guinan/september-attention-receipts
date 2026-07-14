# Payout queue

The live collector queues one `quai-tweet-bounty-v1` record for each first-seen tweet ID.

Payment status lifecycle:

- `queued_manual_payment`: eligible, not paid.
- `paid`: manual payment completed; include `payment_tx`.
- `rejected`: invalid receipt, synthetic smoke, spam, private/doxxing, or otherwise out of bounds.
- `duplicate`: tweet ID was already seen.

No funded hot wallet is configured. Do not add private keys, mnemonics, wallet JSON, `.env`, or RPC secrets to this repo.
