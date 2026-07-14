# Hot wallet is not enabled

This repository intentionally does not contain a live signer.

Before any automatic QUAI payout daemon is enabled:

- use a burner wallet only;
- generate/place the key on the target host without printing it;
- run as a dedicated no-login service user;
- set strict file permissions;
- run negative read controls;
- separate gas budget from payout budget;
- require an executable hardening check to return `RESULT PASS`;
- publish a receipt documenting what remains unproven.

Until then, all bounty records are queued for manual payment.
