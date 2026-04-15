# Institutional DeFi Protocol Risk Assessment

A high-level checklist for verifying the safety of decentralized protocols before institutional or HNW participation.

### 1. Smart Contract Integrity
- [ ] Audit Recency: Has the code been audited in the last 6 months? By whom?
- [ ] Bug Bounty: Is there an active bounty program (Immunefi, etc.)?
- [ ] Upgradeability: Are the contracts immutable or upgradeable? Who holds the keys?

### 2. Governance & Ownership
- [ ] Multisig Thresholds: Minimum 3-of-5 or 5-of-9 for treasury/admin functions.
- [ ] Timelocks: Minimum 48-hour delay on all administrative changes.
- [ ] Key Distribution: Proof of geographically distributed keyholders.

### 3. Economic Risk
- [ ] Liquidity Depth: Analyzing slippage risk for entry/exit at scale.
- [ ] Oracle Robustness: Vulnerability assessment of price feeds (Chainlink integration, etc.).
- [ ] TVL Stability: History of rapid capital inflow/outflow signals.
