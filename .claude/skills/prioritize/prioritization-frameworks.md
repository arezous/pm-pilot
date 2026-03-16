# Prioritization Frameworks

Reference for the scoring and bucketing methods available in `/prioritize`. The skill defaults to weighted scoring for ranking and MoSCoW for scope cuts. Ask for any framework by name.

---

## Framework Selection Guide

| Situation | Framework |
|---|---|
| Quarterly roadmap planning, cross-team comparison | RICE |
| Quick feature comparison, early-stage exploration | ICE |
| Custom dimensions, evidence-heavy prioritization | Weighted Scoring |
| Scope cuts, release planning | MoSCoW |
| Visual triage, quick alignment | Value vs Effort Matrix |
| Understanding user satisfaction drivers | Kano Model |

---

## Weighted Scoring (default)

Custom dimensions scored 1-10 with configurable weights. Default dimensions:

| Dimension | Weight | What it measures |
|---|---|---|
| User impact | 30% | Users affected, pain severity |
| Strategic alignment | 25% | Ties to company priorities |
| Effort | 20% | Engineering/design time, dependencies |
| Competitive pressure | 15% | Market urgency, deal losses |
| Confidence | 10% | Evidence quality behind the scores |

**Score:** weighted average across dimensions.

**When to use:** Most situations. Best when you have context files with real evidence to cite. Weights are adjustable per exercise.

**Strengths:** Flexible, evidence-grounded, surfaces confidence gaps.
**Weaknesses:** Requires good context to score well. More subjective than RICE.

---

## RICE

**Formula:**
```
RICE Score = (Reach x Impact x Confidence) / Effort
```

| Component | Description | Values |
|---|---|---|
| Reach | Users affected per quarter | Numeric count (e.g., 5,000) |
| Impact | Effect on each user | massive=3x, high=2x, medium=1x, low=0.5x, minimal=0.25x |
| Confidence | Certainty in estimates | high=100%, medium=80%, low=50% |
| Effort | Person-months required | Numeric (e.g., 5) |

**Example:**
```
Feature: Mobile push notifications
Reach: 10,000 users
Impact: massive (3x)
Confidence: medium (80%)
Effort: 5 person-months

RICE = (10,000 x 3 x 0.8) / 5 = 4,800
```

**Interpretation:**
- 1000+: High priority
- 500-999: Medium priority
- 100-499: Low priority
- <100: Deprioritize

**When to use:** Quarterly planning, comparing features across product areas, resolving debates with data.

**Strengths:** Reach makes it data-driven. Hard to game when estimates are honest. Good for cross-team comparison.
**Weaknesses:** Requires reasonable reach estimates. Doesn't account for dependencies. May undervalue platform investments.

---

## ICE

**Formula:**
```
ICE Score = (Impact + Confidence + Ease) / 3
```

| Component | Scale | Description |
|---|---|---|
| Impact | 1-10 | Expected effect on key metric |
| Confidence | 1-10 | How sure are you about impact? |
| Ease | 1-10 | How easy to implement? (inverse of effort) |

**When to use:** Early-stage exploration, quick estimates, growth experiments. Good when you don't have reach data for RICE.

**Strengths:** Fast, simple, low overhead.
**Weaknesses:** All components weighted equally. No reach dimension. Easy to inflate scores.

---

## MoSCoW

| Category | Definition | Capacity guide |
|---|---|---|
| Must Have | Product fails without it. Non-negotiable. | ~60% |
| Should Have | Important but workarounds exist. | ~20% |
| Could Have | Desirable enhancements. Build if time allows. | ~10% |
| Won't Have (this time) | Explicitly out of scope. Revisit later. | 0%, documented |

**"Must Have" criteria:**
- Regulatory or legal requirement
- Core user job cannot be completed without it
- Explicitly promised to customers
- Security or data integrity requirement

**Common mistakes:**
- Everything becomes "Must Have" (scope creep)
- Not documenting "Won't Have" items (they come back)
- Treating "Should Have" as optional (they're important, just not blocking)

**When to use:** Scope cuts, release planning, V1 definition. Best when the PM already knows what to build and needs to decide what ships now vs later.

**Strengths:** Forces hard decisions. Clear communication to stakeholders.
**Weaknesses:** No scoring, just bucketing. Doesn't help compare items within a bucket.

---

## Value vs Effort Matrix

```
                  Low Effort          High Effort
                +--------------+------------------+
   High Value   |  QUICK WINS  |    BIG BETS      |
                |  [Do First]  |   [Plan & Validate] |
                +--------------+------------------+
   Low Value    |   FILL-INS   |   TIME SINKS     |
                |   [Maybe]    |    [Avoid]       |
                +--------------+------------------+
```

**Portfolio balance (rough guide):** 40% Quick Wins, 30% Big Bets, 20% Fill-Ins, 10% Buffer.

**When to use:** Visual triage, team alignment workshops, quick gut-check before deeper scoring. Good for getting a room to agree on what's obviously high or low value.

**Strengths:** Fast, visual, intuitive. Good for group exercises.
**Weaknesses:** Binary (high/low), no nuance. Value and effort definitions are subjective without scoring criteria.

---

## Kano Model

Classifies features by how they affect user satisfaction:

| Type | If absent | If present | Priority |
|---|---|---|---|
| Basic (Must-Be) | Dissatisfied | Neutral | High, table stakes |
| Performance (Linear) | Neutral | Satisfied proportionally | Medium, differentiation |
| Excitement (Delighter) | Neutral | Very satisfied | Strategic, competitive edge |
| Indifferent | Neutral | Neutral | Low, skip unless cheap |
| Reverse | Satisfied | Dissatisfied | Avoid |

**Classification questions:**
1. How would you feel if the product HAS this feature?
2. How would you feel if the product DOES NOT have this feature?

**When to use:** Understanding what users expect vs what delights them. Good for deciding between "catch up" features (basic) and "leap ahead" features (excitement). Best paired with user research.

**Strengths:** User-centered. Reveals which features are table stakes vs differentiators.
**Weaknesses:** Requires user survey data. Categories shift over time (today's delighter becomes tomorrow's expectation).
