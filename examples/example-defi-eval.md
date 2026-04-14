# Example: DeFi Protocol Evaluation Output

*This is a worked example showing what the defi-protocol-eval skill produces. The protocol and data are illustrative.*

---

## DeFi Protocol Eval: Morpho Blue USDC/ETH Market — 2026-03-20

**Chain:** Ethereum | **TVL:** $1.8B | **APY:** 8.4% (supply USDC) | **Score:** 24/30

### Protocol Basics
Morpho Blue is a permissionless lending protocol. This specific market: supplying USDC to earn yield, collateralized by ETH. Category: lending. Live since August 2023. Token: MORPHO (governance), not required to use protocol.

### Safety Assessment

**Smart Contract Risk: Low**
- Audited by Spearbit, MixBytes, and Trail of Bits (2023, 2024). No critical findings unresolved.
- Bug bounty: active, $1M maximum payout (Immunefi).
- Contracts are immutable (no upgrades) — admin cannot change market parameters after deployment.
- No prior exploits on Morpho Blue.

**Centralization Risk: Low**
- Immutable contracts — no upgrade key risk.
- Oracle: Chainlink ETH/USD + Uniswap v3 TWAP (dual oracle with circuit breaker).
- Governance can create new markets but cannot change existing ones.

**Economic Risk: Low-Medium**
- Collateral is ETH — high quality, deep liquidity.
- LTV: 86% max — leaves buffer for liquidation.
- Black swan scenario: ETH flash crashes 20%+ before liquidation bots can act. Historical precedent: March 2020 and May 2021 both saw this — assess your risk tolerance accordingly.
- No death spiral mechanics — USDC supply earns interest, no circular dependency.

### Yield Source

USDC suppliers earn interest paid by ETH borrowers who want leverage.
**Yield source:** Real borrower interest — not token emissions.
**Sustainability:** Sustainable as long as there is demand to borrow against ETH (historically persistent).
**Current rate drivers:** High ETH borrowing demand for restaking leverage plays. Rate may compress as restaking matures.

### Score

| Criterion | Score | Notes |
|-----------|-------|-------|
| Time Sensitivity | 3 | No specific end date — yield could compress gradually |
| Signal Strength | 5 | Well-established protocol, multiple data sources confirm rates |
| Downside Bound | 4 | Smart contract risk is low; main risk is ETH price crash triggering bad debt |
| Liquidity | 5 | Instant withdrawal, no lock-up, deep USDC liquidity |
| Regulatory Clarity | 4 | Lending protocol on Ethereum — relatively clear, but stablecoin regs evolving |
| Edge Source | 3 | Not uniquely early, but rate is genuinely good vs. alternatives |
| **Total** | **24/30** | |

### Recommendation: DEPLOY

**Allocation:** Up to 30% of stablecoin holdings (within illiquid limit — this is liquid)
**Entry:** Permissionless — supply USDC directly to Morpho Blue USDC/ETH market
**Minimum acceptable yield:** 5% APY (exit if drops below — consider Aave v3 as fallback at current ~4.8%)
**Exit triggers:**
- APY drops below 5%
- TVL drops below $500M (whale exit signal)
- Any smart contract incident on Morpho (even unrelated markets)
- ETH price drops >30% in a single day (potential bad debt risk — reassess)

**Interface:** app.morpho.org — verify contract address against official docs before first interaction.
