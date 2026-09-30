# PaisaKamao

Customer rewards website, operations dashboard, and API starter.

## Applications

### Customer website
Open `index.html` or deploy it to a static host. It currently uses a demo API adapter. Configure `window.PAISAKAMAO_CONFIG` before the script to connect your API.

### Admin dashboard
```bash
cd admin
npm install
cp .env.example .env
npm run dev
```

The dashboard uses demo data unless `VITE_DEMO_MODE=false`. Set `VITE_API_BASE_URL` to the backend API URL.

### Backend API
```bash
cd backend
npm install
cp .env.example .env
npm run db:generate
npm run db:migrate
npm run dev
```

The API currently provides a health endpoint and a Prisma data model. Task, wallet, and withdrawal routes intentionally remain disabled (HTTP 501) until secure authentication, database services, ledger transactions, and payout-provider verification are implemented.

## Production checklist
- Implement server-side authentication, authorization, CSRF protection, rate limits, validation, and audit logs.
- Use secure HttpOnly cookies and HTTPS.
- Keep payout/OTP secrets on the backend; never ship secrets to the browser.
- Implement and test an append-only ledger, payout idempotency, provider webhook verification, and reconciliation.
- Replace demo data and verify all customer/admin flows before launch.
- Review privacy notices, consent records, data retention, backups, monitoring, and applicable Indian regulatory requirements.
