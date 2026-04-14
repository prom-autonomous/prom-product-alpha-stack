# Skill: Arbitrage Scout

**Trigger:** "Any arb right now?" / "Check funding rates" / "CEX/DEX spreads?"

## What This Does

Surfaces risk-bounded arbitrage opportunities: cross-exchange price gaps, CEX/DEX spreads, funding rate anomalies, and stablecoin depegs. Calculates net spread after costs before flagging anything as actionable.

---

## Workflow

### Step 1 — Scan Opportunity Types

**Cross-Exchange Price Arb**
- Same token, different prices on two CEXes
- Check: Binance, Coinbase, Kraken, OKX, Bybit for major pairs (BTC, ETH, SOL, major alts)
- Net spread must exceed: withdrawal fees + trading fees on both sides + slippage estimate

**CEX/DEX Spread**
- Token priced differently on a DEX vs. CEX
- Factor in: gas fees, DEX swap fee, price impact at your position size
- Tools: DEXScreener, 1inch aggregator quotes

**Funding Rate Arb (Cash-and-Carry)**
- Long spot + short perpetual (or vice versa) to capture funding rate
- Positive funding: short perp collects, long spot exposed to price
- Negative funding: long perp collects, short spot (or use stablecoin)
- Check: CoinGlass (coinglass.com) for current funding rates across exchanges
- Net yield = funding rate - borrowing cost (if using leverage) - trading fees

**Stablecoin Depeg**
- Stablecoin trading above or below $1.00 on any major venue
- Buy low, redeem/bridge at $1.00 — or short if overcollateralized mechanism guarantees peg
- Check: Curve Finance pools, 1inch, CoinGecko stablecoin prices

### Step 2 — Calculate Net Spread

For each opportunity, calculate:

```
Gross spread: X%
- Trading fees (entry + exit): X%
- Withdrawal/gas fees: $X (X% of position at intended size)
- Slippage estimate at $X position: X%
= Net spread: X%
```

Flag as actionable only if **net spread > 0.5%** (otherwise fees eat the profit).

> For cross-chain execution: [ChangeNOW](https://changenow.io/?link_id=alphasurface) is non-custodial, supports 850+ assets, and has no withdrawal delays — useful for closing cross-exchange gaps quickly. *(affiliate)*

### Step 3 — Risk Assessment

Even "risk-free" arb has risks — name them:
- Execution risk: price could move while you're transferring between venues
- Withdrawal delay: CEX withdrawal taking hours while price moves
- Smart contract risk: for DEX-side of the trade
- Counterparty risk: is the CEX solvent?
- Regulatory: any issues with the specific tokens?

### Step 4 — Score (Category B)

| Criterion | Score (1-5) | Notes |
|-----------|-------------|-------|
| Time Sensitivity | | How long does this window typically last? |
| Signal Strength | | Confirmed on multiple sources? |
| Downside Bound | | Is the max loss truly bounded? Name the tail risk. |
| Liquidity | | Can you execute at your position size without moving the market? |
| Regulatory Clarity | | Are both venues accessible in your jurisdiction? |
| Edge Source | | Why hasn't this been closed already? Speed? Capital requirement? |
| **Total** | **/30** | |

Threshold: ≥20/30 to flag as actionable.

### Step 5 — Output

```
## Arbitrage Scout — [DATE] [TIME]

### [Opportunity Name] — Net spread: X% — Score: X/30
**Type:** [Cross-exchange / CEX-DEX / Funding rate / Stablecoin depeg]
**Asset:** $TICKER
**Venues:** [Venue A] vs. [Venue B]
**Gross spread:** X% | **Net spread after costs:** X%
**Est. window:** [minutes / hours / ongoing]
**Max position at risk limits:** $X
**Tail risk:** [name it]
**Execution steps:**
1. ...
2. ...
3. ...

---
[repeat for each opportunity ≥20/30]

### Nothing Actionable
[If no opportunities meet threshold]
```
