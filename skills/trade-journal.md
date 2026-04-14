# Skill: Trade Journal

**Trigger:** "Log this trade" / "Journal: bought X" / "Review my trades" / "What am I doing wrong?"

## What This Does

Two modes: **Log** a trade with structured metadata, or **Review** your trade history to extract patterns and lessons.

---

## Mode 1: Log a Trade

When the user says they made a trade, collect and format:

### Required Fields
- Date and time (UTC)
- Token/pair (e.g., SOL/USDC)
- Direction: Long or Short
- Entry price
- Position size ($ amount and % of portfolio)
- Stop-loss price and % from entry
- Target price(s) and % from entry
- Entry thesis (1-3 sentences: why this, why now)
- Narrative it's attached to
- Signal source (on-chain, social, chart, scan)

### Optional Fields
- Emotional state at entry (FOMO / Conviction / Systematic / Other)
- Market context at entry (risk-on / risk-off / neutral)

### Output Format

```
## Trade Log — [DATE]

| Field | Value |
|-------|-------|
| Token | |
| Direction | Long / Short |
| Entry | $X |
| Size | $X (X% of portfolio) |
| Stop-loss | $X (X% below entry) |
| Target | $X (X% above entry) — R:R ratio: X |
| Thesis | |
| Narrative | |
| Signal source | |
| Emotion | |
| Market context | |

**Status:** OPEN
```

When the trade closes, update with:
- Exit price and date
- P&L ($ and %)
- Exit reason (stop hit / target hit / manual / thesis invalidated)
- Lesson (1 sentence: what would you do differently?)

---

## Mode 2: Review Trade History

When the user asks to review trades, analyze the log and output:

### Win Rate Analysis
- Total trades, win rate, average win %, average loss %
- Expectancy: (win rate × avg win) - (loss rate × avg loss)
- Best and worst trade

### Pattern Identification

Look for patterns across losing trades:
- Are losses concentrated in a specific narrative type?
- Are losses larger than planned stops? (discipline issue)
- Are entries FOMO-driven vs. systematic?
- Are wins cut too early?

### Sizing Analysis
- Average position size vs. risk limits
- Is sizing consistent or erratic?

### Output Format

```
## Trade Review — [DATE RANGE]

**Trades:** X | **Win rate:** X% | **Expectancy:** +/- $X per trade

### What's Working
...

### What's Costing You
...

### Top Lesson
[Single most important change to make]
```
