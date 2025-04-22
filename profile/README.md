# Glofica

Global Financial Infrastructure for Modern Payments

Glofica is an API-first platform providing next-gen financial infrastructure for banks, fintechs, and wallets. Enable seamless local, regional, and international payments in USDC and fiat through a reliable network of local anchors.

## Features

- Multi-currency transfers (USDC, fiat)
- On-ramp/off-ramp infrastructure with local partners
- Automated disbursement and collections
- Manual KYC onboarding
- Secure, scalable API

## Use Cases

- Neobanks offering cross-border payments
- Fintech apps needing stablecoin payouts
- Payroll platforms with multi-currency distribution
- Treasury automation with smart conversion

## Tech Stack

- RESTful API + Webhooks
- JSON over HTTPS
- OAuth2 authentication
- WebSocket support for real-time notifications

## Sample API Endpoint

`http
POST /v1/transfers

Headers:
Authorization: Bearer <access_token>

Body:
{
  "from_currency": "USDC",
  "to_currency": "VES",
  "amount": "100.00",
  "recipient": {
    "name": "Juan Perez",
    "bank_account": "01021234567890123456",
    "country": "VE"
  }
}
