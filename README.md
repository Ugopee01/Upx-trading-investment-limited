# Backend API — UPX TRADING/INVESTMENT LTD

## Overview

Node.js (Express) RESTful API for trading, portfolio management, user authentication, KYC/AML, payments, and integration with AI microservices.

---

## Key Features

- JWT authentication + 2FA (TOTP)
- Role-based access control (RBAC)
- End-to-end encrypted sensitive fields (e.g., KYC data)
- Secure deposit/withdrawal endpoints (integrated with payment gateway)
- Real-time price feeds (WebSockets)
- Admin endpoints for compliance, regulatory, onboarding

---

## Structure

```
/src
  /controllers
  /models
  /routes
  /middleware
  /services
  /utils
/tests
```

---

## Main Endpoints

- `POST /auth/register` — Register user (with KYC/AML workflow)
- `POST /auth/login` — Login, JWT & 2FA
- `POST /auth/2fa/verify` — Verify OTP
- `POST /deposit`, `POST /withdraw` — Payments (secure, audit-logged)
- `GET /portfolio` — Portfolio performance (live)
- `GET /risk-score` — AI-based risk scoring (calls AI engine)
- `GET /recommendations` — Personalized investment advice
- `POST /trade` — Place trades (stocks, crypto, forex)
- `GET /market-data` — Live market prices (Nigeria, US, crypto, forex)
- `GET /admin/kyc` — KYC/AML onboarding
- `POST /admin/compliance/report` — Regulatory reporting

---

## Security

- HTTPS enforced (behind load balancer)
- All endpoints JWT-protected
- 2FA required for sensitive actions
- Database encryption via PostgreSQL

---

## Environment

Set variables in `.env` (see `.env.example`).

---

## Scripts

- `npm run lint`
- `npm test`
- `npm start`

---

## Integration

- AI Engine (Python): `/risk-score`, `/recommendations`
- Market Data APIs: Nigerian/US stocks, crypto, forex
- Payment Gateway, KYC/AML APIs

---

## See also

- [AI Engine Spec](/ai-engine/README.md)
- [Frontend API Usage](/frontend/README.md)