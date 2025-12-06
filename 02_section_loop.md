# Module 2 — Section Loop

## 🔄 CHANGE LOG (Task 3 Update)
- Added `summary_level` variable (`short` or `detailed`).
- Implemented conditional summarization logic:
  - Short → 1–2 sentences
  - Detailed → 1 paragraph + 3–5 bullet points
- Updated workflow to reflect summary-level choices.
- Improved formatting consistency.

---

## Responsibilities
- Summarize each section based on the selected summary level.
- Use **only** the content found in the provided section text.
- Maintain consistent formatting and structure across all sections.

---

## Variables
- `summary_level` (string)
  - `"short"`
  - `"detailed"`

---

## Workflow
1. Receive:
   - Normalized section list  
   - Section text blocks  
   - Summary level  

2. For each section:
   - Check if text exists  
   - Pass missing/short flags to Module 3  
   - Apply summarization rules:

---

### ⭐ **If `summary_level = "short"`**
Produce a **1–2 sentence** concise summary:
- No bullet points  
- No long explanations  
- Just the essential idea  

---

### ⭐ **If `summary_lev_**
