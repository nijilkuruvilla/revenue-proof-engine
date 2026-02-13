# 100x PMM Revenue Proof Engine — Master Plan

## Purpose

Define the vision, scope, constraints, and expansion logic for Stage 1.

---

## Vision

Build revenue proof infrastructure.

This product transforms:

Unstructured customer proof  
→ Structured revenue data  
→ Deal-ready executive assets  

This is not a content generator.  
This is revenue intelligence infrastructure.

---

## Stage 1 Wedge

Single workflow:

1. Upload proof
2. Structure it
3. Generate executive asset
4. Export PDF

Nothing else.

No CRM.
No collaboration.
No dashboards.
No analytics UI.

If this is used weekly in real deals, Stage 1 succeeds.

---

## Product Principles

1. Structure data from day one.
2. Keep UI surface area small.
3. Architect for expansion.
4. Signal credibility in design.
5. Delight through refinement, not playfulness.

---

## Core Objects

### Workspace
Represents a revenue team.

### Proof
Structured revenue evidence.

Required fields:
- company_name
- industry
- persona
- use_case
- claim_statement
- metric_type
- metric_value
- timeframe
- objection_addressed
- product_capability
- source_type
- confidence_score

No freeform JSON blob for structured fields.

### Asset
Generated executive asset derived only from structured Proof fields.

---

## Architecture Direction

Frontend:
- Next.js (App Router)
- TypeScript
- Tailwind with strict token system

Backend:
- Supabase (Postgres + Auth)
- Row-level security

AI:
- Claude or OpenAI
- Deterministic JSON extraction
- Temperature 0

PDF:
- Server-side generation only
- Board-ready output

---

## Delight Philosophy

Delight = calm craftsmanship.

- Generous white space
- Subtle emerald accents
- Intelligent loading states
- No gimmicks
- No mascots
- No gradients

The interface should feel like a quiet executive briefing room.

---

## Stage 1 Success Criteria

- Users upload real proof
- Assets exported weekly
- Teams use it in live deals
- Someone requests CRM integration

Only then expand.
