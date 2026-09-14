# 🚀 Fraud Detection & Security API

> A high-performance backend security middleware layer engineered to intercept, evaluate, and score financial transactions for suspicious activity or fraudulent behavior before they interact with the core transaction-processing engine.

<!-- Project badges -->
![Status](https://shields.io)
![Version](https://shields.io)
![Language](https://shields.io)
![License](https://shields.io)

---

## 📌 Table of Contents

- [About The Project](#-about-the-project)
- [Project Objectives](#-project-objectives)
- [Features](#-features)
- [Technologies Used](#-technologies-used)
- [Project Structure](#-project-structure)
- [How It Works](#-how-it-works)
- [Getting Started](#-getting-started)
- [Installation](#-installation)
- [Usage](#-usage)
- [Bugs & Fixes](#-bugs--fixes)
- [Challenges & Struggles](#-challenges--struggles)
- [What I Learned](#-what-i-learned)
- [Development Process](#-development-process)
- [Roadmap](#-roadmap)
- [Known Issues](#-known-issues)
- [Future Improvements](#-future-improvements)
- [Project Reflection](#-project-reflection)
- [License](#-license)
- [Author](#-author)

---

## 📖 About The Project

### What is this project?

> The Fraud Detection & Security API acts as an intelligent firewall for financial backends. It intercepts transactions at the perimeter, analyzes payloads against behavioral rules, and dynamically scores them to reject or authorize processing.

Instead of allowing incoming network transactions to immediately touch your banking balances or transactional processors, this gateway acts as a defensive evaluation buffer. It reads metadata vectors (such as velocity counts, location parameters, and historical deviations) to neutralize security threats under sub-second performance limits.

### Why did I build it?

This project was created to master:
- **Middleware Architecture:** Intercepting request-response cycles inside a backend framework pipeline.
- **Risk Score Modeling:** Writing conditional algorithmic score evaluators based on combined risk weightings.
- **High-Velocity Data Audits:** Leveraging in-memory storage networks to track transaction counts within short time loops.
- **Payload Data Sanitization:** Implementing strict security rules to block malicious payload structural injection types.

### Project Background

This is an advanced backend system engineering and portfolio project designed to explore corporate security gateway patterns, high-frequency stream filtering, and automated threat mitigation design.

---

## 🎯 Project Objectives

The main objectives of this project are:

- [ ] Structure a clean Express/Node middleware gateway to filter inbound financial request routing paths.
- [ ] Implement an evaluation risk engine to parse, verify, and score transaction properties.
- [ ] Connect a fast in-memory data store to audit multi-request account velocity metrics.
- [ ] Build automated logging hooks recording safety evaluation actions for security compliance profiles.

---

## ✨ Features

### ✅ Implemented Features

- **Transaction Interception Layer** — Dedicated middleware hooks that stop inbound payloads, ensuring no transaction hits processing loops unverified.
- **Location Discrepancy Validator** — Analytical scripts comparing the geographic source of incoming request keys against known user default locations.
- **Sanitization Guard** — Strict parameter checkers sweeping incoming body tags to block bad character patterns or injection strings.

### 🚧 Features Currently Being Developed

- **Velocity Analysis Matrix** — Connecting fast memory cache ledgers to count how many transactions an account fires within a 60-second window.
- **Dynamic Score Engine** — An algorithmic processor aggregating minor risk markers into a single structural index (0 to 100) to auto-flag threats.
- **Audit Exception Logger** — Database logging routers that permanently save security intercepts, blocked vectors, and high-risk flags for review.

### 🔮 Planned Features

- [ ] **Machine Learning Scoring Hook** — An isolated Python microservice connection running clustering algorithms to predict advanced fraud indicators.
- [ ] **Dual-Factor Authentication Step-Up** — Logic workflows that pause doubtful transactions and trigger an SMS/Email validation check instead of flatly rejecting them.

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Node.js + Express | Serves as the primary REST API core architecture and middleware framework |
| Redis (In-Memory) | Acts as the velocity ledger caching user transaction frequency states instantly |
| MongoDB + Mongoose | Hosts the permanent configuration databases, user risk records, and alert history |
| Crypto API | Manages data validation encryption signatures and security token generation checks |
| Git & GitHub | Code lifecycle version tracking, feature branch workflows, and repository storage |

### Languages

- JavaScript (Node.js REST Engine)
- JSON (Payload data interchange format)

### Frameworks / Libraries

- Express.js (Backend routing and application middleware framework)
- Mongoose (Object Data Modeling database layout interface)

### Development Tools

- VS Code (IDE Workspace)
- Postman / Insomnia (API interaction performance testing)
- Git & GitHub Workspace

---

## 📂 Project Structure

```text
fraud-detection-api/
│
├── src/
│   ├── middleware/
│   │   ├── securityWall.js # Primary interception gateway evaluating global request headers
│   │   └── rateLimiter.js  # Integrates memory caching checks to intercept high-frequency loops
│   │
│   ├── core/
│   │   ├── scoreEngine.js  # Runs calculations aggregating risk rules into a final rating
│   │   └── rulesLedger.js  # Isolated functional criteria checking locations, times, and amounts
│   │
│   ├── routes/
│   │   └── verify.js       # Main processing routing line parsing data requests (`/api/verify`)
│   │
│   ├── models/
│   │   ├── SecurityLog.js  # Schema detailing blocked payloads, score tags, and timestamps
│   │   └── UserProfile.js  # Stores regular transaction limits, known locations, and risk history
│   │
│   └── server.js           # Launch application booting the local node servers and configurations
│
├── README.md
├── .env.example            # Blueprint detailing database string keys and configuration values
└── .gitignore
```

---

## 🧠 How It Works

The mechanical layout tracking lifecycle of a transaction evaluation executes through this structural security loop:

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
```

---

## 🚀 Getting Started

Review the setup instructions listed below to deploy and audit this security middleware application locally.

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com
   cd fraud-detection-api
   ```

2. **Acquire Backend Project Dependencies**
   ```bash
   npm install
   ```

3. **Configure Environmental Framework Settings**
   Create an active `.env` file within your root `src/` directory space:
   ```text
   PORT=5000
   MONGO_URI=your_mongodb_connection_string
   REDIS_URL=redis://127.0.0.1:6379
   RISK_THRESHOLD=75
   ```

### Usage

1. **Fire up the localized Redis service on your testing platform**
   ```bash
   redis-server
   ```
2. **Launch the security gateway backend server**
   ```bash
   npm run dev
   ```
3. Open Postman or your terminal shell to simulate transaction payloads against `http://localhost:5000/api/verify`. Fire matching records rapidly to watch the velocity manager dynamically flag, score, and isolate suspicious streams.

---

## 🐛 Bugs & Fixes

- **Bug:** Extreme numbers or integer overflow properties passed into amount keys broke score loops inside initial data sweeps.
- **Fix:** Structured an absolute data validation parsing block that strictly coerces value strings down to sanitized floating-point bounds before evaluating them.

---

## 💡 Challenges & Struggles

The central challenge of engineering a security middleware lies in **latency containment**. Adding a validation step between the client input and the transaction engine risks slowing down the checkout experience. Optimization requires keeping velocity lookups completely inside an in-memory database tier like Redis, ensuring evaluation processes resolve under 50 milliseconds.

---

## 🧠 What I Learned

- Learned how to write modular, chaining custom middleware components in Express to cleanly inspect, stamp, and route requests without disrupting controller performance.
- Mastered structural implementation rules regarding **Velocity Throttling algorithms**, utilizing sliding-window memory caching models to track user traffic spikes.

---

## 🗺️ Roadmap

- [x] Phase 1: High-fidelity entry validation middleware routes complete.
- [ ] Phase 2: Implementation of in-memory velocity check configurations.
- [ ] Phase 3: Dynamic scoring algorithmic weight updates deployment.
- [ ] Phase 4: Downstream Transaction Processor backend service routing link.

---

## 🚀 Future Improvements

