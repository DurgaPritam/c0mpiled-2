# TrustMove UAE

**Agentic Relocation & Rental Trust Assistant**

TrustMove UAE is an agentic assistant designed to help people relocating to the UAE make better housing decisions. It supports users in two connected steps: choosing the right neighborhood and assessing the trust and safety of a rental listing, all within a single conversation.

By combining area-level reasoning with rule-based scam detection, TrustMove produces clear, explainable guidance suitable for real-world civic and real-estate use cases.


## Problem

Relocating to the UAE commonly breaks down in two places.

### Area Selection

Many newcomers struggle to understand which neighborhoods fit their job location, budget, commute preferences, and lifestyle. Advice is usually fragmented across friends, online forums, and informal recommendations, which makes it difficult to compare options realistically.

### Rental Scams

Once an area is chosen, users often rely on unverified listings from WhatsApp or classifieds. This exposes them to common risks such as fake agents, pressure tactics, and requests for deposits before viewings.

These two challenges are typically treated as separate steps, even though they are part of the same decision journey.


## Solution

TrustMove UAE addresses both challenges through a single agentic workflow:

1. Collects key user constraints such as work location, budget, commute, and lifestyle
2. Recommends suitable areas rather than individual listings
3. Evaluates the scam risk of a pasted rental listing using transparent heuristics
4. Explains every recommendation and risk assessment through a clear reasoning trace


## Agent Architecture

TrustMove operates as a coordinated multi-agent system:

* **Interview Agent**
  Gathers essential inputs using no more than two to three clarifying questions

* **Reasoning Agent**
  Ranks neighborhoods based on constraints, trade-offs, and budget realism

* **Risk Analysis Agent**
  Applies a consistent heuristic rubric to estimate scam risk

* **Explanation Agent**
  Produces a concise decision trace to ensure transparency and demo clarity


## Conversation Flow

### Phase A — Area Recommendations

**Inputs**

* Work location
* Budget (AED per year)
* Unit type (Studio, 1BHK, 2BHK)
* Commute preference (metro or car)
* Lifestyle preference (quiet, social, family-oriented)
* Must-haves and dealbreakers

**Outputs**

* Top three recommended areas plus one wildcard option
* For each area:

  * Short fit summary
  * Rent realism relative to the stated budget
  * Approximate commute note
  * Lifestyle characteristics
  * Key pros and cons
  * Confidence level


### Phase B — Listing Trust Check

The user provides a rental listing or its details.

**Outputs**

* Scam risk score (0–100)
* Risk label: Low, Medium, or High
* Key risk signals with severity
* A practical checklist outlining next steps


## Scam Risk Scoring (Heuristic)

TrustMove uses a rule-based approach with no live web scraping.

Signals considered include:

* Pricing far below typical area averages
* WhatsApp-only communication or refusal to speak by phone
* Urgency language such as “deposit today”
* Missing broker license or RERA details
* Refusal or inability to arrange a viewing
* Requests for payment before viewing
* Vague or inconsistent listing information

All scores are clamped between 0 and 100 and clearly labeled.


## Area Dataset

* Focused on Dubai
* Uses a small internal dataset of common neighborhoods
* Includes:

  * Typical rent ranges
  * Metro access
  * Lifestyle indicators
  * Notes on trade-offs and limitations

TrustMove recommends areas rather than individual properties.


## Explainability and Trace

Each response includes a short trace section that outlines:

* Inputs considered
* Signals detected
* Reasoning behind area rankings and risk scores

This supports user trust, judging clarity, and future regulatory alignment.


## Tech Stack and Partner Tools

* **Crustdata**
  Optional enrichment of broker or company details to reduce impersonation scams

* **Lingo.dev**
  Arabic and English localization to support the UAE’s bilingual user base

* **Lyra**
  Distribution and deployment of TrustMove as a reusable agent

* **Trace**
  Logging of decision steps to make agent reasoning transparent and auditable

* **Uplift AI**
  Analysis of anonymized conversations to improve prompts and safety guidance over time


## Safety and Disclaimers

* TrustMove is not a legal authority
* It provides risk guidance, not guarantees
* Users are encouraged to:

  * Verify broker and RERA details
  * Conduct in-person or video viewings
  * Avoid upfront deposits
  * Use official payment channels

Requests involving illegal or unsafe actions are refused, with safer alternatives suggested.

## Vision

TrustMove UAE illustrates how adaptive city agents can support everyday decisions by embedding trust, transparency, and practical reasoning into the relocation experience.
