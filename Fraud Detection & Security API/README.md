# 🛡️ Fraud Detection & Security API

> A security middleware layer designed to evaluate financial transactions for suspicious activity before they reach the transaction-processing system.

![Status](https://img.shields.io/badge/Status-Planning-yellow?style=for-the-badge)
![Project Type](https://img.shields.io/badge/Project-Backend-blue?style=for-the-badge)
![Domain](https://img.shields.io/badge/Domain-FinTech-green?style=for-the-badge)
![Focus](https://img.shields.io/badge/Focus-Security-red?style=for-the-badge)

---

## 📌 About The Project

The Fraud Detection & Security API is a backend security layer designed to evaluate financial transactions before they are authorised by the main transaction-processing system.

The system will analyse transaction information and look for potentially suspicious behaviour.

Instead of allowing every transaction to immediately reach the banking transaction processor, transactions will first pass through a security layer.

```text
Transaction
     │
     ▼
┌─────────────────────────┐
│ Fraud Detection &       │
│ Security API            │
└────────────┬────────────┘
             │
        Risk Analysis
             │
       ┌─────┴─────┐
       ▼           ▼
    Suspicious     Safe
       │           │
       ▼           ▼
     Reject      Authorize
                   │
                   ▼
          Transaction Processor
