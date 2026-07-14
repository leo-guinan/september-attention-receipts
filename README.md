# September Attention Receipts

Public receipt repository for the September Attention Camera game.

This repo is where exported attention receipts, encoded camera rolls, first-seen tweet bounty records, and manual QUAI payout receipts can be submitted.

## Bounty rule

A valid, first-seen tweet receipt is worth `1 QUAI`.

The server-side collector dedupes by normalized tweet ID. The extension is only a camera; the payout ledger is the referee.

## Important custody boundary

No hot wallet is configured here. Bounties are queued for manual payment until a burner wallet is generated, hardened, funded, and explicitly approved.

Queued is not paid. A depressingly necessary sentence.

## Submit receipts

Preferred:

1. Export JSONL from the Chrome extension.
2. Encode it:

```bash
python3 scripts/encode_receipts.py encode metaspn-attention-receipts.jsonl -o submissions/<handle>-bundle.json
```

3. Open a PR adding:
   - your encoded bundle under `submissions/`
   - optional commitment hash in the PR body
   - optional payout address if you want manual bounty payout

## Reveal / verify

```bash
python3 scripts/encode_receipts.py decode submissions/<handle>-bundle.json -o revealed.jsonl
sha256sum revealed.jsonl
```

The decoded receipt JSONL should match the bundle's `raw_sha256`.

## Live collector endpoints

```text
POST https://guide.metaspn.network/api/sensor
GET  https://guide.metaspn.network/api/sensor/summary.json
GET  https://guide.metaspn.network/api/sensor/bounties.json
```

## What counts

- Public tweet/profile/page receipts captured by an opted-in browser.
- Visible DOM stats only.
- No private analytics unless voluntarily exported by the account owner.
- Duplicate tweet IDs do not earn duplicate QUAI.
- Synthetic smoke receipts do not count.
