# PRD — Alpha Stack: Claude Code Skills for Crypto & DeFi

**Version:** 1.0
**Date:** 2026-04-14
**Status:** APPROVED — building

---

## Problem

Crypto traders and DeFi researchers using Claude Code have to manually write complex prompts for every research task — token due diligence, protocol evaluation, on-chain signal reading. There's no standardized, battle-tested skill set for this domain. Generic Claude Code packs exist but none target crypto/DeFi specifically.

## Solution

A drop-in Claude Code skills pack: a set of markdown files the buyer places in their project. Each file is a named skill — a carefully engineered prompt template with step-by-step research workflows, output formats, and decision criteria built in. Works with standard Claude Code, no API keys or plugins required.

## Target Users

- Crypto traders using Claude Code for research
- DeFi researchers evaluating protocols and yield opportunities
- Indie hackers building crypto tools who want Claude to understand the domain
- CT (Crypto Twitter) content creators who want faster research workflows

## Scope — v1.0

### Skills (8 files)
1. `token-research.md` — Full DD on any token: team, tokenomics, narrative fit, entry thesis
2. `defi-protocol-eval.md` — Safety and yield sustainability assessment for any DeFi protocol
3. `narrative-radar.md` — Identify hot narratives, score momentum, find underpriced plays
4. `onchain-intel.md` — Interpret whale moves, smart money signals, unusual contract activity
5. `trade-journal.md` — Log and analyze trades with structured P&L and lesson extraction
6. `portfolio-risk.md` — Check positions against defined risk limits, flag overexposure
7. `arbitrage-scout.md` — Spot cross-exchange spreads, funding rate anomalies, CEX/DEX gaps
8. `CLAUDE.md` — Master config: sets crypto domain context, terminology, and default behavior

### Workflows (3 files)
1. `morning-alpha.md` — 10-minute morning research ritual: market, narratives, opportunities
2. `token-dd-workflow.md` — End-to-end token due diligence, from discovery to go/no-go
3. `defi-entry-checklist.md` — Pre-entry checklist for any DeFi position

### Examples (2 files)
1. `example-token-research.md` — Worked example of a token research session
2. `example-defi-eval.md` — Worked example of a DeFi protocol evaluation

## Pricing

- **Free tier (GitHub):** CLAUDE.md + one skill (narrative-radar.md) — drives discovery
- **Paid (Gumroad):** Full pack, $19 one-time

## Distribution

1. GitHub public repo (free tier + README with Gumroad link)
2. Gumroad listing
3. Post to relevant subreddits (r/ClaudeAI, r/LocalLLaMA, r/algotrading, r/CryptoCurrency)
4. AlphaSurface X post

## Out of Scope (v1.0)

- No code — markdown only
- No API integrations
- No updates/support commitments beyond README
