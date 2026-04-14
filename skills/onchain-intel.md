# Skill: On-Chain Intel

**Trigger:** "What's smart money doing?" / "Any on-chain signals?" / "Check whale activity on $TOKEN"

## What This Does

Reads on-chain signals to surface what smart money, whales, and protocol insiders are doing before it hits social or price. Helps you front-run narrative confirmation, not chase it.

---

## Workflow

### Step 1 — Signal Sources to Check

- **Lookonchain** (lookonchain.com) — curated whale and smart money moves
- **Arkham Intelligence** public feeds — wallet labeling and cluster analysis
- **Whale Alert** — large transfers between wallets and exchanges
- **Nansen Smart Money** — if user has access; otherwise use public Lookonchain
- **DEXScreener** — new pair creation, early volume spikes before social attention
- **Exchange flows** — large inflows = selling pressure; large outflows = accumulation signal

### Step 2 — Signal Classification

For each notable on-chain event, classify it:

| Signal Type | What It Means |
|-------------|--------------|
| Whale accumulation (wallet buying, not exchange) | Bullish — smart money building position |
| Exchange inflow (wallet → CEX) | Bearish — likely selling |
| Exchange outflow (CEX → wallet) | Bullish — moving to cold storage / long-term hold |
| New smart money wallet interaction | Early signal — research what they've been right about |
| Unusual contract deployment | Could be new protocol — or could be rug setup |
| LP removal (large) | Bearish — insiders leaving liquidity |
| LP addition (large, new wallet) | Bullish — smart money providing liquidity ahead of launch |

### Step 3 — Contextualize

Don't report raw data — interpret it:
- Is this wallet known? What's their track record? (use Arkham labels if available)
- Does this move make sense given current market conditions?
- Does it corroborate or contradict the current social narrative on this token?
- What's the likely timeframe — is this a short-term trade setup or long accumulation?

### Step 4 — Score (Category B)

| Criterion | Score (1-5) | Notes |
|-----------|-------------|-------|
| Time Sensitivity | | How quickly will this signal be public knowledge? |
| Signal Strength | | How many independent on-chain sources confirm? |
| Downside Bound | | If the signal is wrong, what's the max loss? |
| Liquidity | | Can you act at this wallet's scale? |
| Regulatory Clarity | | Front-running based on public blockchain data is legal — note if insider-adjacent |
| Edge Source | | Are you acting on this before the crowd? |
| **Total** | **/30** | |

### Step 5 — Output

```
## On-Chain Intel — [DATE] [TIME]

### [Signal Description] — Score: X/30
**Asset:** $TICKER on [chain]
**Wallet:** [label or address] — [known entity or unknown]
**Action:** [what happened on-chain — be specific: amounts, destinations]
**Interpretation:** [what this likely means]
**Trade thesis:** [entry, stop-loss, target if actionable]
**Confidence:** [High/Medium/Low] — [why]

---
[repeat for each signal ≥15/30]

### Nothing Actionable
[If no signals meet threshold]
```
