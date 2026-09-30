# PaisaKamao API (starter)

## Setup
1. Copy `.env.example` to `.env` and configure a MySQL database and allowed origins.
2. Run `npm install`.
3. Run `npm run db:generate`.
4. After reviewing the schema, run `npm run db:migrate`.
5. Start with `npm run dev`.

`GET /health` is implemented. Customer task, wallet and withdrawal routes intentionally return HTTP 501 until authentication, authorization, database-backed services, ledger invariants and payment-provider verification are implemented. Do not expose this as a live money-moving API yet.

## Security requirements before launch
- Implement OTP delivery/verification with provider-side rate limits and abuse controls.
- Use server-managed sessions, secure HttpOnly cookies, CSRF protection and role-based authorization.
- Keep an append-only ledger; update balances and withdrawal reservations in database transactions.
- Encrypt UPI identifiers at rest and redact them from logs.
- Verify payout provider signatures, idempotency keys and webhook replay protection.
- Add tests, migrations, backups, monitoring and a security review.
