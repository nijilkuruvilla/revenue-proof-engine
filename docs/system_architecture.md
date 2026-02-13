# System Architecture

## Purpose

Provide explicit implementation blueprint for Claude Code build.

---

## Folder Structure

/app
  /dashboard
  /proofs
  /assets
  /api

/lib
  /db
  /llm
  /pdf
  /validators
  /events

/components
/styles
/prompts
/types

---

## Database Schema (Postgres)

### workspaces

- id (uuid, primary key)
- name (text, not null)
- stripe_customer_id (text)
- created_at (timestamp)

---

### proofs

- id (uuid, primary key)
- workspace_id (uuid, foreign key)
- company_name (text)
- industry (text)
- persona (text)
- use_case (text)
- claim_statement (text)
- metric_type (text)
- metric_value (numeric)
- timeframe (text)
- objection_addressed (text)
- product_capability (text)
- source_type (text)
- confidence_score (numeric)
- created_at (timestamp)

---

### assets

- id (uuid)
- proof_id (uuid, foreign key)
- asset_type (text)
- headline (text)
- executive_summary (text)
- metric_callout (text)
- objection_section (text)
- created_at (timestamp)

---

### events

- id (uuid)
- workspace_id (uuid)
- event_type (text)
- metadata (jsonb)
- created_at (timestamp)

Track:
- proof_uploaded
- proof_structured
- asset_generated
- pdf_exported

---

## API Contracts

POST /api/proofs/extract  
Input:
- raw_text

Output:
- Structured proof JSON

---

POST /api/proofs  
Input:
- structured proof object

Output:
- proof_id

---

POST /api/assets/generate  
Input:
- proof_id

Output:
- structured asset object

---

GET /api/assets/{id}/pdf  
Returns:
- Binary PDF

---

## LLM Constraints

Extraction:
- Temperature 0
- Strict JSON output
- Reject missing required fields

Asset generation:
- Must use only structured proof fields
- No hallucinated data
- Deterministic format
