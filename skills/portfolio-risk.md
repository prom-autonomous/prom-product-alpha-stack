# Skill: Portfolio Risk Check

**Trigger:** "Check my risk" / "Am I overexposed?" / "Portfolio risk snapshot"

## What This Does

Audits current positions against defined risk limits and flags any exposure that needs trimming. Forces you to see the full picture before making a new trade.

---

## Workflow

### Step 1 — Collect Current Positions

Ask the user to provide (or read from a positions file if available):
- Each open position: token, size ($), entry price, current price, unrealized P&L
- Total portfolio value ($ cash + open positions at current prices)

### Step 2 — Check Against Risk Limits

Prompt user for their risk limits (or read from a risk-limits config file). Default framework if none provided:

| Limit | Default | User's Limit |
|-------|---------|-------------|
| Max single position | 20% of portfolio | |
| Max total exposure | 80% of portfolio | |
| Max single token | 20% of portfolio | |
| Stop-loss per trade | 20% from entry | |
| Daily drawdown halt | 10% of portfolio | |
| Weekly drawdown halt | 20% of portfolio | |
| Max illiquid exposure | 30% of portfolio | |
| Max unaudited contract | 10% of portfolio | |

### Step 3 — Flag Violations

For each limit, calculate current value and flag if breached:

```
[BREACH] Max single position: SOL at 34% of portfolio (limit: 20%)
[OK] Total exposure: 65% (limit: 80%)
[WARNING] Illiquid: 28% (limit: 30%) — close to limit
```

### Step 4 — Drawdown Tracking

- Calculate current drawdown from portfolio peak (ask user for peak value or calculate from logs)
- Flag if approaching daily or weekly halt threshold

### Step 5 — New Trade Pre-Check

If the user is considering a new trade, run pre-check:
- Would this trade breach any limit?
- What's the max loss on this trade at stop-loss? Does it push daily drawdown over the halt?
- After this trade, what does total exposure look like?

### Output Format

```
## Portfolio Risk Snapshot — [DATE]

**Total portfolio:** $X | **Cash:** $X (X%) | **Deployed:** $X (X%)
**Peak:** $X | **Drawdown:** X% (daily limit: X%, weekly limit: X%)

### Position Summary
| Token | Size | % Portfolio | Entry | Current | Unrealized P&L | Status |
...

### Limit Check
[BREACH/WARNING/OK for each limit]

### Pre-Trade Check (if applicable)
**Proposed trade:** $TOKEN, $X size
[Results of limit check with trade added]

### Action Required
[Specific trims or halts needed, if any — or "No action needed"]
```
