# TasteLens — Product Memo  
Kaitlyn Chang  
Prototype AI Insight Engine  

---

## Executive Summary

TasteLens is a prompt-driven AI prototype that analyzes public restaurant reviews and converts unstructured customer text into structured insight categories, revealing why people actually like a place, what consistently stands out, and where inconsistencies may exist.

Online reviews contain real signals about what customers value, but those signals are buried inside repetitive, emotional, and inconsistent free text. TasteLens organizes these text reviews into recurring praise drivers, complaint themes, vibe signals, occasion fit, and differentiators. It then synthesizes patterns across businesses to surface positioning insights and tradeoffs.

The goal of this project was not to build a full analytics platform, but to demonstrate how structured prompt design can transform noisy text into interpretable, layered insights.

---

## Problem

Consumers rely heavily on reviews to decide where to eat. However:
- Reviews are unstructured and repetitive  
- Emotional tone often outweighs substance  
- It takes significant time to detect consistent patterns  
- Star ratings do not explain tradeoffs  

To answer simple questions like:
- Why do people actually like this place?  
- Is the price justified?  
- What kind of occasion is it best for?  

Users must manually scan dozens of opinions.

Most platforms display star ratings or short summaries, but they do not distinguish recurring themes from isolated complaints, nor do they clarify positioning signals.

I wanted to explore whether structured AI extraction could reduce that friction.

---

## Product Approach

Rather than focusing on sentiment scoring or star aggregation, I chose to prioritize structure first.

The workflow operates in three layers:

### 1. Structured Extraction  
AI prompts convert raw reviews into consistent insight buckets:
- Praise Drivers  
- Complaint Drivers  
- Vibe & Experience Signals  
- Occasion Fit  
- Differentiators  

I chose these insight categories intentionally based on how users naturally evaluate restaurants. When deciding where to eat, people tend to consider what stands out positively, what tradeoffs exist, what the overall experience feels like, and what type of occasion the restaurant fits. Separating praise, complaints, vibe signals, and differentiators prevents themes from blending together and makes positioning clearer. The schema was designed to reflect user decision-making rather than simply mirror how reviews are written.

The extraction prompt was built to enforce this structure consistently. It required themes to appear multiple times, enforced strict output categories, limited bullet length, and prohibited invented facts. These constraints were designed to reduce noise, avoid overreacting to one-off comments, and produce repeatable, comparable outputs across different businesses rather than generic summaries.

### 2. Synthesis  
After extracting structured themes, I analyze outputs to identify:
- Positioning signals  
- Recurring tradeoffs  
- Operational friction points  
- Cross-business patterns  

This step validates that the schema supports comparison and scalability beyond individual summaries. By applying the same structure across multiple restaurants, I can observe whether consistent positioning patterns and tradeoffs emerge. This demonstrates how structured extraction enables interpretation and comparison across businesses, which is a foundation that could extend into broader merchant or market analytics.

Extraction was performed using structured prompts, while synthesis and system-level observations were manually derived from the structured outputs.

### 3. Presentation  
Insights are layered into an “At a Glance” view above the detailed insights breakdowns, simulating how a lightweight product interface might present both speed and depth.

I intentionally kept ingestion manual and avoided building a UI to focus on the clarity and repeatability of the insight framework itself.

---

## Data Selection & Validation Approach

For this prototype, I manually sampled publicly available Google reviews for three Orange County restaurants: Sidecar Doughnuts, Bear Flag Fish Co., and Habana.

I chose Google Reviews because they offer large volumes of unstructured, natural language feedback that reflect real customer experiences. The three restaurants were intentionally selected to represent different positioning types: a dessert/cafe-like concept, a casual restaurant market hybrid, and an upscale sit-down dining experience. This variation allowed me to test whether the extraction framework could generalize across different price points, formats, and cuisine categories.

I collected 30 publicly visible reviews per restaurant to validate repeatability and theme consistency. The goal was not to build a comprehensive dataset, but to test whether structured prompt extraction could reliably surface recurring signals from real-world review text.

---

## Key Prototype Insights

Analyzing three Orange County restaurants surfaced recurring system-level patterns:
- Premium pricing appeared across all concepts  
- Customers tolerated higher prices when quality felt consistent  
- Long lines were accepted when service moved efficiently  
- Signature items anchored brand identity  
- Atmosphere strongly shaped occasion fit  
- Operational inconsistencies drove dissatisfaction  

What stood out to me was how predictable the tradeoffs became once reviews were structured. Noise decreased significantly once themes were categorized.

This reinforced the idea that structure enables synthesis.

---

## Scope Decisions & Tradeoffs

TasteLens is intentionally a prototype.

Includes:
- Structured prompt design  
- Repeatable extraction framework  
- Cross-business synthesis  
- Layered output formatting  

Excludes (deliberately):
- Automated ingestion  
- Sentiment scoring  
- Quantitative benchmarking  
- Real-time updates  
- Front-end interface  

I chose to prioritize clarity of insight generation over technical complexity. Adding scoring or dashboards without reliable structure would risk amplifying noise rather than signal.

---

## Future Direction

If expanded, the next logical steps would be:

### Phase 1 — Automation
- URL ingestion  
- Automated review sampling  

### Phase 2 — Quantification
- Sentiment scoring per category  
- Confidence weighting by frequency  

### Phase 3 — Benchmarking & Personalization
- Comparative scoring across businesses  
- Personalized recommendation engine  

Each builds on the same structured extraction foundation.

---

## Reflection

This project reinforced that:
1. Structure matters more than model complexity. In past analytical projects, I often focused on building technical depth without clearly defining clean frameworks. This project emphasized the importance of designing structure first.
2. Clear scope decisions improve early prototypes. Without defined constraints, it is easy to overbuild before validating foundational logic.
3. Synthesis creates more value than raw summarization. Structured extraction alone organizes information, but synthesis turns it into usable insight.

TasteLens demonstrates how prompt design, when intentionally structured, can transform noisy qualitative data into layered, interpretable signals. While lightweight, the framework could extend beyond restaurants into merchant feedback analysis, seller reviews, or customer experience monitoring.
