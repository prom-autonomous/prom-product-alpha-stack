# Workflow: Token Due Diligence (End-to-End)

**Trigger:** "Full DD on $TOKEN" / "Should I buy $TOKEN?" / "Go deep on [token name]"

## What This Does

A complete due diligence sequence from discovery to go/no-go decision. Chains multiple skills together for a thorough assessment. Takes 5-15 minutes.

---

## Sequence

### Phase 1 — Narrative Context (use narrative-radar)
Before researching the token itself, understand the narrative it's attached to.
- What narrative is this token riding?
- What stage is that narrative in?
- Is the narrative confirmed by multiple sources or just social?

**Gate:** If the narrative is Saturated or Fading, stop here unless there's a specific catalyst reason to continue.

### Phase 2 — Token Research (use token-research)
Run the full token-research workflow. Score the token on Category B criteria.

**Gate:** Score must be ≥15/30 to continue.

### Phase 3 — On-Chain Confirmation (use onchain-intel)
Specifically look for:
- Is smart money accumulating this token?
- What does the holder distribution look like?
- Any suspicious on-chain patterns (team wallets moving, LP being removed)?

This step is about confirming or disconfirming the thesis from Phase 2.

**Gate:** If on-chain signals contradict the thesis, downgrade the score and note why.

### Phase 4 — Portfolio Risk Pre-Check (use portfolio-risk)
Before sizing:
- Would this position breach any risk limit?
- What's the max loss if the stop-loss is hit?
- Does it push total exposure over the limit?

### Phase 5 — Decision

```
## DD Decision: $TICKER — [DATE]

**Narrative:** [Name] — Stage: [X]
**Token score:** X/30
**On-chain:** [Confirms / Neutral / Contradicts] thesis
**Risk check:** [Clean / Breach on: X]

### GO — Entry Plan
- Entry: $X (or range $X-$X)
- Position size: $X (X% of portfolio)
- Stop-loss: $X (X% below entry) — max loss: $X
- Target 1: $X (X% above entry) — partial exit X%
- Target 2: $X (X% above entry) — remainder
- Thesis invalidation: [what would make you exit early]

### PASS — Reason
[Be specific — one clear reason]
```
