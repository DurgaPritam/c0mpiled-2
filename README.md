
# TrustMove UAE 🏙️

**Agentic Relocation & Rental Trust Assistant**

TrustMove UAE is an agentic assistant that helps people relocating to the UAE **choose the right neighborhood** and **assess rental listing trust/safety** in a single conversation.

It combines **area-level reasoning** with **rule-based scam detection**, producing transparent, explainable outputs suitable for civic and real-estate contexts.

---

## Problem

Relocation to the UAE typically fails in two places:

1. **Area Selection**

   * Users don’t know which neighborhoods fit their job, budget, commute, and lifestyle.
   * Advice is fragmented (friends, Reddit, hearsay).

2. **Rental Scams**

   * Listings on WhatsApp and classifieds are often unverified.
   * Common risks include fake agents, urgency tactics, and upfront deposit fraud.

These are usually treated as separate steps — but they are part of the **same decision journey**.

---

## Solution

TrustMove UAE addresses both problems in one agentic workflow:

1. Understand the user’s constraints (work, budget, commute, lifestyle)
2. Recommend **areas (not live listings)**
3. Evaluate the **scam risk of a pasted rental listing**
4. Explain every decision with a clear trace

---

## Agent Architecture

TrustMove behaves as a coordinated multi-agent system:

* **Interview Agent**
  Collects minimal inputs (max 2–3 clarifying questions)

* **Reasoning Agent**
  Ranks neighborhoods using constraints and trade-offs

* **Risk Analysis Agent**
  Computes a scam risk score using heuristic signals

* **Explanation Agent**
  Produces a decision trace for transparency and demo clarity

---

## Conversation Flow

### Phase A — Area Recommendations

Inputs:

* Work location
* Budget (AED/year)
* Unit type (Studio / 1BHK / 2BHK)
* Commute preference (metro vs car)
* Lifestyle (quiet / social / family)
* Must-haves and dealbreakers

Output:

* Top 3 recommended areas + 1 wildcard
* For each area:

  * Fit summary
  * Rent realism vs budget
  * Commute note
  * Lifestyle vibe
  * Pros / cons
  * Confidence level

---

### Phase B — Listing Trust Check

User provides listing text or details.

Output:

* **Scam Risk Score (0–100)**
* Risk label: Low / Medium / High
* Top risk signals with severity
* Actionable “What to do next” checklist

---

## Scam Risk Scoring (Heuristic)

Rule-based scoring (no live scraping):

Signals include:

* Price significantly below area average
* WhatsApp-only contact / refusal to call
* Urgency language (“deposit today”)
* Missing broker license or RERA number
* No viewing allowed
* Deposit requested before viewing
* Vague or inconsistent listing details

Scores are clamped to **0–100** and labeled clearly.

---

## Area Dataset (Hackathon Scope)

* Focus: **Dubai**
* Small internal dataset of common neighborhoods
* Includes:

  * Average rents
  * Metro access
  * Lifestyle tags
  * Notes and trade-offs

TrustMove **recommends areas, not listings**.

---

## Explainability & Trace

Each response includes a **Trace** section showing:

* Inputs considered
* Signals detected
* Reasoning behind rankings and risk scores

This ensures transparency for users, judges, and regulators.

---

## Tech Stack / Partner Tools

* **Crustdata** – Optional broker/company enrichment to reduce impersonation scams
* **Lingo.dev** – Arabic ↔ English localization for UAE users
* **Lyra** – Agent distribution and deployment marketplace
* **Trace** – Decision logging and explainability
* **Uplift AI** – Conversation analysis to improve prompts and safety guidance over time

---

## Safety & Disclaimers

* Not a legal authority
* Provides risk assessment, not guarantees
* Encourages:

  * Broker/RERA verification
  * In-person or video viewings
  * No upfront deposits
  * Official payment channels only

Unsafe or illegal requests are refused with safer alternatives suggested.

---

## Hackathon Constraints

* No live web scraping
* No real payments or integrations
* Rule-based logic
* Demo-first design
* Beginner-friendly implementation

---

## Vision

TrustMove UAE demonstrates how **adaptive city agents** can embed trust into everyday decisions — not by controlling users, but by helping them reason safely and transparently.

