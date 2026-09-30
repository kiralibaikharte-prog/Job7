# PaisaKamao

Customer rewards website and admin dashboard starter.

## Customer site
Open `index.html` or deploy it to a static host. It currently uses a demo API adapter. Configure `window.PAISAKAMAO_CONFIG` before the script to connect your API.

## Admin app
```bash
cd admin
npm install
cp .env.example .env
npm run dev
```

The admin dashboard uses demo data unless `VITE_DEMO_MODE=false`. Set `VITE_API_BASE_URL` to your backend API.

## Production checklist
- Implement server-side auth, role checks, CSRF, rate limits, validation and audit logs.
- Use secure HttpOnly cookies and HTTPS.
- Keep payout/OTP secrets on the backend; never ship secrets to the browser.
- Replace demo data and verify all payout/task flows before launch.
