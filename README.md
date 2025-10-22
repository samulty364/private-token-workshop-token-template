---

# Samuelty123 — Compliant Private Token (Aleo Workshop Project)

The **Samuelty123 Token** is a privacy-preserving smart contract built on the **Aleo blockchain** during the **Compliant Private Tokens Workshop (Uyo, Nigeria)**.  
It demonstrates how to create, verify, and deploy a **compliant fungible token** that merges **privacy, compliance, and transparency** through Aleo’s zero-knowledge programming model.

---

## Deployment Information

- **Program Name:** `samuelty123.aleo`  
- **Blockchain:** Aleo Testnet  
- **Dependency Module:** `workshop_ofac.aleo` (for compliance verification)  
- **Deployment ID:** `at1vmh7m9gp50m0uxt27xr9pd492wyt0zc364u0mcw8lpzps88w5ugqzqxe02`  
- **Deployment URL:** [View on Aleo Testnet](https://testnet.aleo.info/program/samuelty123.aleo)  
- **Author:** Samuel Anthony Uwa  

---

## Execution Information
- **mint_public ID:** `at1yypzdhmh32rp7ydywu5re3h3fjwpxclxc44jz4z44r7sp57h0szqn4dg56`
- **mint_private ID:** `at1g4qdcn2t3nj2haf5qlqz6h2235lhh8ps6vsyv9d0qtffhgrmpczsy4g4sx`
- **transfer_public ID:** `at1caxcr8qrz2q4qchljpewd75fvr2cwg6qc7aavgzsmyez2uxhnyrsd7hpkw`
- **transfer_private ID:** `at1tdk2gej88yq3mweyyv3tj7nunxqwranzee3v05khatcrsqgusvyqwmwn8mv`

---

## Project Overview

The **Samuelty123 Token** represents a compliant digital asset that balances **regulatory enforcement** and **user privacy**.  
It integrates a compliance layer through `workshop_ofac.aleo`, ensuring that all public and private operations — from minting to transfers — undergo address verification before execution.

This project reflects Aleo’s vision: **privacy and compliance can coexist** within decentralized systems.

---

## Purpose

This project was created to help participants of the **Aleo Workshop in Uyo** learn how to:

- Build privacy-first token contracts using **Leo**.  
- Understand **public mappings** vs. **private record storage**.  
- Integrate compliance verification through **asynchronous functions (Future + await)**.  
- Deploy and interact with Aleo programs confidently.  

---

## Core Principles

### **1. Public Ledger Operations**

Public functions operate on transparent on-chain mappings of balances.  
Each address and its balance are visible but verified before any update.

Example functions include:

- `mint_public`: Mints tokens to an address after compliance check.  
- `transfer_public`: Transfers visible balances between two verified addresses.

mapping balances: address => u64;
Examples:

mint_public: Mints tokens to a recipient after verification.

transfer_public: Transfers tokens between verified public addresses.

All balances remain visible, ensuring auditability and accountability.

---

### **2. Private Record Operations**

Private functions utilize Aleo’s record system to maintain confidentiality of ownership and balances.

record Token {
    owner: address,
    amount: u64
}


Examples:

mint_private: Mints tokens privately as encrypted records.

transfer_private: Transfers value privately using record consumption and regeneration.

Records are cryptographically bound to owners and never publicly revealed, protecting user privacy.

---

### **3. Integrated Compliance Layer**

Every operation interacts with the compliance module:

let address_check: Future = workshop_ofac.aleo/address_check(recipient);
address_check.await();


This mechanism validates every address against restricted lists before any minting or transfer occurs, ensuring regulatory alignment.

---

 ## Functional Overview
 
| Function           | Visibility | Description                                                     |
| ------------------ | ---------- | --------------------------------------------------------------- |
| `mint_public`      | Public     | Adds tokens to recipient’s balance after compliance validation. |
| `mint_private`     | Private    | Issues a new token record privately to the recipient.           |
| `transfer_public`  | Public     | Moves visible tokens between two public accounts.               |
| `transfer_private` | Private    | Privately transfers tokens via record regeneration.             |

---

## Learning Objectives

By building and deploying the token, participants learned to:

1. Use mappings and records effectively in Leo.
2. Implement asynchronous compliance verification using Futures.
3. Handle public and private state transitions securely.
4. Deploy and test Aleo smart contracts using Playground and CLI.
5. Apply real-world regulatory logic in decentralized environments.

---

## Build, Run, and Deploy

**Build the project:**

```bash
leo build
```

**Deploy to Aleo Testnet:**

```bash
leo deploy
```

**Run sample functions:**

```bash
leo run mint_public recipient_address 100u64
leo run transfer_public recipient_address 100u64
leo run mint_private recipient_address 100u64
leo run transfer_private sender_record recipient_address 20u64
```
---

## Technical Highlights
| Feature              | Description                                               |
| -------------------- | --------------------------------------------------------- |
| **Language**         | Leo                                                       |
| **Mapping**          | Tracks public balances on-chain                           |
| **Records**          | Maintain private ownership details                        |
| **Async Validation** | Ensures compliance checks run before state updates        |
| **Extensibility**    | Can include additional logic like `burn`, `approve`, etc. |

---

## Use Case Scenarios

- **Regulated Token Deployments:** Enables compliant issuance of digital assets.
- **Privacy-Preserving Transactions:** Supports confidential transfers while maintaining compliance.
- **Enterprise & Institutional Use:** Ideal for CBDCs, corporate tokens, and other regulated assets.

---

## Educational Value

This project represents the practical component of the Aleo Workshop in Uyo.
It bridges theoretical understanding and hands-on zero-knowledge development, teaching participants how to:

* Write Leo contracts with compliance logic.
* Manage private and public state.
* Deploy, test, and verify privacy-preserving applications.

---

## Author

**Samuel Anthony Uwa**
Student Researcher | Aleo Workshop Participant (Uyo, Nigeria)

> Developed during the Aleo Compliant Private Tokens Workshop — Demonstrating how privacy and compliance can operate seamlessly within Aleo’s zero-knowledge environment.>

---

<img width="1312" height="463" alt="deploy" src="https://github.com/user-attachments/assets/5a118492-fb8c-4f7d-aac5-24948b1deb4a" />
<img width="855" height="361" alt="decrypted rec" src="https://github.com/user-attachments/assets/d4413193-2e91-40f1-a6ba-31281ad1453a" />
