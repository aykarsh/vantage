# Vantage Backend

The central authority and settlement ledger for **Project Vantage**, built with Go.

## 🛠️ Key Roles

- **Voucher Minting**: Issues cryptographically signed vouchers that serve as digital cash.
- **Settlement**: Receives "Digital Envelopes" from mobile clients, verifies the multi-hop signature chain, and settles the balance.
- **Double-Spending Prevention**: Maintains the global state of every voucher ID to ensure each unit of value is only spent once.
- **Idempotency**: Ensures that repeated sync attempts from unreliable mobile connections do not disrupt the ledger.

## 🚀 API Endpoints

- `GET /health`: System health and database connectivity check.
- `POST /mint-voucher`: Endpoint for authorized users/systems to generate new value.
- `POST /settle-payment`: Endpoint for mobile clients to upload offline transaction envelopes.

## 🏗️ Project Structure

- `cmd/api`: Entry point for the server.
- `internal/crypto`: Server-side Ed25519 verification logic.
- `internal/envelope`: Logic for unwrapping and validating the Digital Envelope protocol.
- `internal/handlers`: HTTP handlers and idempotency logic.
- `internal/db`: PostgreSQL connection and repository logic.

## 🚦 Setup

1. **Database**: Run the migration found in `scripts/migrations/schema.sql` on your PostgreSQL instance.
2. **Environment**: Create a `.env` file with your `DB_URL` and `PORT`.
3. **Run**:
   ```bash
   go run cmd/api/main.go
   ```
