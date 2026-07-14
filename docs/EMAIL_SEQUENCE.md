# Receipt operator email sequence

The inbound page captures email addresses for a six-part sequence about:

1. using captures as bounded public receipts,
2. what counts as a useful capture,
3. rewarding capturers without making MetaSPN the reward authority,
4. registering downstream reward endpoints,
5. evaluating mindshare before September,
6. revealing and auditing receipts at the September event.

Live signup endpoint:

```text
POST https://inbound.metaspn.network/api/email/signup
```

Transport status is explicit. If SMTP/sendmail is unavailable, subscribers are stored and messages remain queued; no fake sent receipts.
