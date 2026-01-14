# Web3-Security-Resources
Practical DeFi/Web3 security &amp; protocol risk checklists, incident response playbooks, and onchain investigation workflows.
# Web3 Security & Protocol Risk Resources (Mike Pirie)

Practical, battle-tested resources for assessing and reducing risk in DeFi and Web3 systems.

I combine enterprise-grade security and incident response (CISSP) with hands-on onchain work across Ethereum and major EVM L2s (Base, Optimism, Arbitrum, Linea), plus node operations (Theta) and ecosystem exposure (Cosmos, Zilliqa, Monad).

**GitHub:** https://github.com/soutpiel358

---

## What you’ll find here

- **Protocol Risk Checklists**: repeatable reviews for common DeFi risk categories  
- **Incident Response Playbooks**: what to do in the first hour/day/week of a security event  
- **Onchain Investigation Workflow**: how to validate what happened using explorers + public data  
- **Governance & Ops Controls**: practical guardrails that prevent avoidable failures  
- **Tooling Notes**: how I use common tools to reduce uncertainty and improve decisions  

---

## Quick Protocol Risk Checklist (v1)

### 1) Contract Architecture & Upgradeability
- Determine whether the system is **upgradeable** (proxy pattern) or immutable
- If upgradeable:
  - Who can upgrade?
  - Is there a **timelock**?
  - Is there an emergency pause and who controls it?
- Confirm the **implementation address** and verify source where possible

### 2) Privileged Access & Admin Key Risk
- List all privileged roles (owner, guardian, pauser, upgrader, fee setter, oracle admin)
- Confirm whether privileges are protected by:
  - multisig (recommended)
  - timelock (recommended)
  - separation of duties / role-based controls
- Validate signer set quality:
  - number of signers
  - distribution (not all the same org/person)
  - operational security hygiene

### 3) Economic Design & Incentive Risk
- Identify incentive attack surfaces:
  - liquidity mining / emissions
  - fee switches
  - referral systems
  - points programs
- Watch for:
  - wash trading incentives
  - sybil incentives
  - MEV amplification
  - reflexive leverage loops

### 4) Oracle & Pricing Risk
- Determine oracle model:
  - Chainlink / external oracle
  - TWAP
  - custom
- Validate:
  - manipulation resistance
  - fallback behavior
  - staleness handling
  - circuit breakers

### 5) Cross-Chain / Bridge Risk (if applicable)
- Identify bridge type:
  - canonical
  - third-party
  - messaging layer
- Review:
  - trust assumptions
  - validator set / multisig structure
  - emergency pause / unwind plan
- Treat bridges as **high-risk** until proven otherwise

### 6) Operational Resilience
- Monitoring:
  - key contract events (upgrades, pauses, parameter changes)
  - TVL changes
  - oracle deviations
  - abnormal transaction patterns
- Incident readiness:
  - roles & escalation tree
  - comms templates
  - pre-drafted “pause” + user protection playbooks

---

## Onchain Investigation Workflow (fast)

1. **Confirm the facts**
   - affected contract(s), block range, timestamps, attacker address(es)

2. **Use explorers + public data**
   - Etherscan / Basescan (tx traces, internal calls, logs)
   - DeFi Llama (TVL and ecosystem context)
