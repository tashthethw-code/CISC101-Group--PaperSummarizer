# Module 3 — Guardrails

## 🔄 CHANGE LOG (Task 3 Update)
- Added `evidence_mode = "strict"` functionality.
- Added standardized warning messages for:
  - Missing sections
  - Empty sections
  - Sections under 50 words
- Added logic to block unsupported claims in strict evidence mode.
- Improved rule clarity and organization.

---

## Responsibilities
- Enforce safe, accurate summarization rules.
- Prevent hallucinations and unsupported claims.
- Detect and warn about problematic section inputs.

---

## Variables
- `evidence_mode`
  - `"default"` → normal summarization rules  
  - `"strict"` → ONLY allow claims directly supported by text  

---

# ⚠️ Guardrail Rules

### 1. **Missing Section**
If a section is not provided:

```
"Section [NAME] skipped: no usable text was provided."
```

---

### 2. **Short Section (<50 words)**
If a section contains fewer than 50 words:

```
"Section [NAME] is very short — summary may be incomplete."
```

---

### 3. **Strict Evidence Mode**
When `evidence_mode = "strict"`:
- Summaries MUST use only facts explicitly present in the text.
- No interpretations, assumptions, or inferred claims.
- If there isn’t enough information:

```
"Strict evidence mode: insufficient information to summarize this section."
```

---

## Workflow
1. Check if section exists.  
2. If missing → issue missing-section warning.  
3. If short → issue short-section warning.  
4. Apply evidence-mode rules:
   - strict → allow ONLY text-supported details  
   - default → normal summarization  
5. Return:
   - warnings  
   - evidence-validated summary output  

