# 🚀 Banking Transaction Processor

> A high-performance, concurrent backend transaction engine designed to process financial operations safely across shared account states while guaranteeing database atomic integrity and absolute balance accuracy.

<!-- Project badges -->
![Status](https://shields.io)
![Version](https://shields.io)
![Language](https://shields.io)
![License](https://shields.io)

---

## 📌 Table of Contents

- [About The Project](#-about-the-project)
- [Project Objectives](#-project-objectives)
- [Core Problem](#-core-problem)
- [Proposed Solution](#-proposed-solution)
- [Features](#-features)
- [Technologies Used](#-technologies-used)
- [System Architecture](#-system-architecture)
- [Transaction Flow](#-transaction-flow)
- [Project Structure](#-project-structure)
- [Transaction Types](#-transaction-types)
- [Concurrency & Integrity](#-concurrency--integrity)
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
- [Disclaimer](#-disclaimer)
- [Author](#-author)

---

## 📖 About The Project

### What is this project?

> The Banking Transaction Processor is a backend-focused core utility architecture built to simulate high-frequency financial ledgers. It processes concurrent accounts manipulation safely by ensuring absolute transaction isolation and data integrity.

Rather than linking directly to external active banking clearing networks, this project functions as an isolated simulation kernel. It maps atomic operations, tracks balance changes, updates audit trails, and isolates account validation states cleanly under high-load multithreaded runtime parameters.

### Why did I build it?

This project was created to master:
- **Multithreading & Concurrency:** Orchestrating task execution threads safely without race condition stutters.
- **Thread Synchronization:** Locking records granularly to prevent database corruption.
- **Shared State Management:** Handling high-frequency data mutation loops seamlessly across in-memory structures.
- **Data Integrity Frameworks:** Enforcing strict ACID principles (Atomicity, Consistency, Isolation, Durability) programmatically.

### Project Background

This is a deep backend system architecture and portfolio capstone project built to explore high-throughput transaction routing, thread safety limits, and strict structural banking safety validations.

---

## 🎯 Project Objectives

The main goals are to:

- [ ] Construct an asynchronous thread pool execution kernel capable of handling overlapping client transactions.
- [ ] Implement strict transactional isolation behaviors to eliminate concurrent write state hazards.
- [ ] Build robust transaction validation checks verifying ledger constraints before balance deduction points.
- [ ] Create a thread-safe transaction audit log tracking all history ledger states chronologically.

---

## ❓ Core Problem

Consider an account baseline profile setup initialized with:
* **Account Balance:** `R1,000`

If two independent systems try to deduct funds (e.g., a withdrawal of `R600` and a simultaneous debit transfer of `R500`) at the exact same millisecond:
1. **Thread A** reads the balance: `R1,000`.
2. **Thread B** reads the balance: `R1,000` simultaneously.
3. Both threads validate that `R1,000` is sufficient to cover their individual amounts.
4. **Thread A** subtracts `R600` and writes back `R400`.
5. **Thread B** subtracts `R500` and overrides the ledger with `R500`.

**Resulting Hazard:** The final balance becomes corrupted, creating either an incorrect balance or an unbacked account overdraft. This is a classic concurrency **race condition** that must be prevented at the engine runtime level.

---

## 💡 Proposed Solution

The processing engine deploys **Pessimistic Striped Locking Architecture** combined with atomic transaction operations. 

By isolating updates using atomic account identification tags, the processor ensures that whenever **Account X** is participating in a ledger update, its specific resource pointer is temporarily locked against concurrent reads and writes from neighboring threads. Alternative accounts remain completely unlocked, keeping transaction processing speeds exceptionally linear without compromising system integrity.

---

## ✨ Features

### ✅ Implemented Features

- **Multi-Client Simulation Thread Pool** — An integrated executive scheduler that divides incoming transaction objects across distinct thread execution runners.
- **Audit Ledger Logging** — A synchronized historical tracker mapping all successful, failed, and rolled-back events with precise timestamp stamps.
- **Basic Account CRUD Engine** — Functional backend models managing basic metadata structures, routing keys, and baseline balances.

### 🚧 Features Currently Being Developed

- **Pessimistic Account Locking Guard** — Writing advanced custom synchronization blocks that map balance updates safely across multiple competing threads.
- **Bi-Directional Transfer Router** — Building double-entry ledger checking routines that securely transfer values between separate bank accounts without creating deadlocks.

### 🔮 Planned Features

- [ ] **Optimistic Concurrency Control (OCC)** — An alternative version tracking layout using database row versioning tags to compare balance states before locking.
- [ ] **Automated Fraud Detection Hook** — An inline evaluation script that blocks transaction records automatically if velocities or values exceed safety bounds.

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Java SE (17+) | Core object-oriented runtime platform and concurrency control architecture |
| Java Concurrency API | Leverages `ReentrantLock`, `ExecutorService`, and `Atomic` utility modules |
| Maven | Coordinates build tracking pipelines, packaging tasks, and dependency trees |
| JUnit 5 | Drives isolation assertion scripts and structural stress testing loops |
| Git & GitHub | Manages workflow feature branch rollouts and codebase snapshot tracking |

### Languages

- Java (100% Backend Architecture Core)

### Frameworks / Libraries

- None (Built using pure, framework-free native Java primitives to study low-level thread behaviors directly)

### Development Tools

- IntelliJ IDEA / Eclipse (IDE Workspace)
- Git & GitHub Actions
- VisualVM (Thread Profiling & Deadlock Analysis Tools)

---

## 🏗️ System Architecture & Transaction Flow

The structural lifecycle progression of an inbound financial transaction executes through this absolute transactional loop:

```text
[ Incoming Request ]
        │
        ▼
[ Executor Service Thread Pool ]
        │
        ▼
[ Transaction Validator ] ──(Invalid Payload)──> [ Log Failure & Terminate ]
        │
        ▼
[ Account Lock Manager ] ───(Resource Busy)───> [ Wait in Thread Queue ]
        │
        ▼
[ Lock Acquired Safely ]
        │
        ▼
[ Balance Modification Engine ]
        │
        ▼
[ Commit to Memory Ledger ]
        │
        ▼
[ Release Account Lock ]
        │
        ▼
[ Broadcast Completion Event ]
```

---

## 📂 Project Structure

```text
banking-transaction-processor/
│
├── src/
│   ├── main/
│   │   └── java/
│   │       └── com/banking/processor/
│   │           ├── core/
│   │           │   ├── TransactionEngine.java   # Core thread scheduling system kernel
│   │           │   └── LockManager.java         # Resolves striped locking rules and balances
│   │           ├── models/
│   │           │   ├── Account.java             # Thread-safe account balance records
│   │           │   └── Transaction.java         # Datatype modeling transfer requests
│   │           └── validation/
│   │               └── IntegrityGuard.java      # Validates balance constraints and funds
│   │
│   └── test/
│       └── java/com/banking/processor/
│           └── ConcurrencyStressTest.java       # Asserts ledger stability under high thread loads
│
├── README.md
├── pom.xml                                      # Maven dependency script descriptor
└── .gitignore
```

---

## 💳 Transaction Types

The processing kernel handles four core transaction classes:
* **DEPOSIT:** Adds an absolute monetary sum directly onto a specified target account balance.
* **WITHDRAWAL:** Deducts a defined sum out of a single targeted account profile (guarded against overdrafts).
* **TRANSFER:** Executes a double-entry balance adjustment moving funds securely from a source account to a destination target.
* **AUDIT_LOOKUP:** Reads historical state tracking ledgers without mutating existing data parameters.

---

## 🧵 Concurrency & Integrity Controls

To maintain data integrity under concurrent stress, the engine relies on the following mechanisms:
1. **Deadlock Prevention:** Accounts involved in bi-directional transfers are always sorted and locked in a strict, predictable numerical order (e.g., lower account ID is always locked first). This entirely prevents cyclical lock wait states.
2. **Atomic In-Memory Updates:** Utilizing thread-safe structures to verify that updates to the database are performed as a single unit of work.
3. **Fail-Fast Validations:** Any single transaction attempting to push account states into negative boundaries is intercepted and short-circuited instantly, bypassing the write sequence.

---

## 🚀 Getting Started

