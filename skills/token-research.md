# Skill: Token Research

**Trigger:** "Research $TOKEN" / "DD on [token name]" / "Is [token] worth looking at?"

## What This Does

Runs a structured due diligence workflow on any token. Output is a scored research report with a clear go/no-go recommendation.

---

## Workflow

When the user asks you to research a token, execute these steps in order:

### Step 1 — Identity & Basics
- Full name, ticker, chain(s)
- Contract address (note: user should verify independently)
- Launch date and current market cap / FDV
- Token type: utility, governance, memecoin, RWA, liquid staking, etc.

### Step 2 — Team & Legitimacy
- Is the team doxxed or anonymous? If doxxed, any prior projects?
- GitHub activity: is the repo active or dead?
- Audit status: audited by whom, when, findings?
- Any rugs, exploits, or controversies in team history?

### Step 3 — Tokenomics
- Total supply, circulating supply, FDV vs. market cap ratio
- Unlock schedule: when do team/VC tokens unlock? (cliff/vesting)
- Emission rate: inflationary or deflationary?
- Where does yield come from? Is it sustainable or printed?

### Step 4 — Narrative Fit
- What narrative does this token attach to? (AI, RWA, DeFi, L2, meme, etc.)
- How early or late is that narrative? (emerging / peaking / fading)
- What's the catalyst for re-rating? Is it time-bound?

### Step 5 — Liquidity & Market Structure
- Primary DEX/CEX, liquidity depth at ±2% and ±10%
- 24h and 7d volume vs. market cap ratio (flag if volume > 50% of MC — suspicious)
- Holder distribution: top 10 wallets hold what %? (flag >30% in top 10 non-protocol wallets)

### Step 6 — Score (Category B Framework)

| Criterion | Score (1-5) | Notes |
|-----------|-------------|-------|
| Time Sensitivity | | How narrow is the opportunity window? |
| Signal Strength | | How many independent sources confirm the thesis? |
| Downside Bound | | Can max loss be defined? Does 20% stop-loss protect adequately? |
| Liquidity | | Can you enter and exit cleanly at your position size? |
| Regulatory Clarity | | Is this legally clear in the user's jurisdiction? |
| Edge Source | | Why would you win this trade? Speed? Information? Automation? |
| **Total** | **/30** | |

### Step 7 — Recommendation

State clearly:
- **GO** (score ≥18/30): Entry thesis, suggested position size as % of portfolio, stop-loss level, and target exit. For spot entry: [Coinbase](https://coinbase.com/join/alphasurface) for regulated fiat pairs, [ChangeNOW](https://changenow.io/?link_id=alphasurface) for non-custodial cross-chain swaps.
- **WATCH** (15-17/30): What would need to change to make it a GO
- **PASS** (<15/30): Primary reason(s) — be blunt

---

## Output Format

```
## Token Research: $TICKER — [DATE]

**Chain:** | **MC:** | **FDV:** | **Score:** X/30

### Identity
...

### Team & Legitimacy
...

### Tokenomics
...

### Narrative Fit
...

### Liquidity & Market Structure
...

### Score
| Criterion | Score | Notes |
...

### Recommendation: GO / WATCH / PASS
...
```
