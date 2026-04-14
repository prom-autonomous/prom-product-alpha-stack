# Skill: DeFi Protocol Evaluation

**Trigger:** "Eval [protocol]" / "Is [protocol] safe?" / "Check the yield on [protocol]"

## What This Does

Assesses any DeFi protocol for safety, yield sustainability, and opportunity quality. Output is a structured report with a clear deploy/watch/avoid recommendation.

---

## Workflow

### Step 1 — Protocol Basics
- Protocol name, chain(s), category (lending, DEX, yield aggregator, liquid staking, perps, etc.)
- Launch date, TVL (current and 30d trend)
- Token: does it have one? Governance or utility? Current price and FDV.

### Step 2 — Safety Assessment

**Smart Contract Risk**
- Audit status: audited by whom? How recently? Any unresolved findings?
- Bug bounty program: active? Maximum payout?
- Time-lock on admin functions? Multi-sig or single key?
- Has it been exploited before? If so, how was it handled?

**Centralization Risk**
- Who controls upgrades? Is there a governance delay?
- Can a single entity drain the protocol?
- Is the oracle decentralized (Chainlink, TWAP) or centralized (admin-set)?

**Economic Risk**
- What happens in a black swan? (liquidation cascades, bank runs, oracle manipulation)
- Is the collateral accepted high-quality or long-tail?
- Any death spiral mechanics in the tokenomics?

### Step 3 — Yield Sustainability

Answer: **where does this yield actually come from?**

| Source | Sustainable? |
|--------|-------------|
| Real protocol revenue (fees) | Yes |
| Token emissions (printed) | Only while emissions last |
| Subsidized by VC/treasury | Temporary — find the end date |
| Recursive/looped (yield on yield) | Fragile — note the dependencies |

Flag if APY seems abnormally high (>50% on stablecoins, >200% on volatile assets) — ask why, and what the catch is.

### Step 4 — Opportunity Quality Score (Category B)

| Criterion | Score (1-5) | Notes |
|-----------|-------------|-------|
| Time Sensitivity | | Is this a launch incentive with an end date? |
| Signal Strength | | Has this yield been confirmed by multiple sources? |
| Downside Bound | | What's the worst case? Smart contract loss? IL? |
| Liquidity | | Can you exit cleanly at any time? Lock-up? |
| Regulatory Clarity | | Is this protocol and the yield treatment clear legally? |
| Edge Source | | Are you early to this yield opportunity? |
| **Total** | **/30** | |

### Step 5 — Recommendation

- **DEPLOY** (≥18/30): Suggested allocation (% of DeFi budget), entry steps, exit trigger
- **WATCH** (15-17/30): What to monitor before deploying
- **AVOID** (<15/30): Primary risk — be specific

---

## Output Format

```
## DeFi Protocol Eval: [Protocol Name] — [DATE]

**Chain:** | **TVL:** | **APY:** | **Score:** X/30

### Protocol Basics
...

### Safety Assessment
Contract risk: [Low/Medium/High]
Centralization risk: [Low/Medium/High]
Economic risk: [Low/Medium/High]

...

### Yield Source
[Where does the yield come from — be specific]
Sustainability: [Sustainable / Limited / Unsustainable]

### Score
...

### Recommendation: DEPLOY / WATCH / AVOID
...
```
