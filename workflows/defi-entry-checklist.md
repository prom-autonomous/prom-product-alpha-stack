# Workflow: DeFi Entry Checklist

**Trigger:** "Should I deploy into [protocol]?" / "DeFi checklist for [protocol]"

## What This Does

A fast pre-entry checklist that surfaces the most common ways DeFi positions go wrong before you commit capital. Runs in under 5 minutes.

---

## Checklist — Answer Each Before Deploying

### Safety (must pass all)
- [ ] Contract audited by a reputable firm in the last 12 months?
- [ ] No unresolved critical/high findings in the audit?
- [ ] Admin keys are time-locked or multi-sig? (not a single EOA with instant upgrade power)
- [ ] Protocol has been live for >3 months without a major exploit?
- [ ] Oracle is decentralized (Chainlink, TWAP) — not admin-set?

If any box is unchecked, flag the risk and note it in the output. Any unchecked box is a potential loss of principal, not just yield.

### Yield Source (must understand)
- [ ] I can explain where this yield comes from in one sentence
- [ ] The yield source is sustainable beyond the current incentive period
- [ ] I know when/if the incentive emissions end

If you can't explain the yield source, you don't understand the risk. Don't deploy.

### Liquidity (must pass)
- [ ] I can exit my full position without more than 1% price impact
- [ ] There is no lock-up period, or I accept the lock-up and have sized accordingly
- [ ] If there's a withdrawal queue, I know the current wait time

### Risk Sizing
- [ ] This position is within my max single-position limit
- [ ] Adding this to my portfolio doesn't push total DeFi exposure over my limit
- [ ] I've run the portfolio-risk check with this position included

### Exit Conditions (define before entry)
- [ ] Exit if: APY drops below X% (minimum acceptable yield)
- [ ] Exit if: TVL drops below $Xm (whale leaving = warning signal)
- [ ] Exit if: any governance change that weakens safety
- [ ] Exit if: token price drops X% (for LP positions — impermanent loss threshold)

---

## Output Format

```
## DeFi Entry Checklist: [Protocol] — [DATE]

**Pool/Strategy:** [e.g., ETH/USDC LP, USDC lending]
**APY:** X% | **Intended size:** $X | **Lock-up:** [None / X days]

### Safety
[✓ or ✗ for each item — note any ✗ explicitly]

### Yield Source
[One sentence explaining the yield]
Sustainable: [Yes / Until: date / No]

### Liquidity
[✓ or ✗ for each item]

### Risk Sizing
[✓ or ✗ for each item]

### Exit Conditions
- APY < X%
- TVL < $Xm
- [other]

### Decision: DEPLOY / DO NOT DEPLOY
[If DO NOT DEPLOY — specific reason]
```
