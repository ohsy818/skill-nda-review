---
name: skill-nda-review
description: Review Non-Disclosure Agreements (NDA) for Korean parties, identifying high-risk clauses and recommending market-standard alternatives. Use when a user asks to review, analyze, or check an NDA, confidentiality agreement, or CDA — especially Korean contracts with M&A, SaaS, medical AI, trade secret, or technology collaboration contexts.
---

# NDA Contract Review Skill

Review Non-Disclosure Agreements (NDA) for Korean parties, identifying high-risk clauses and recommending market-standard alternatives.

## When to Use

- User uploads or pastes an NDA (Korean, English, or bilingual)
- User asks to "review my NDA", "NDA 검토해줘", "계약서 봐줘"
- Any contract labeled as NDA, confidentiality agreement, or CDA
- NDAs involving M&A, SaaS integration, healthcare AI, trade secrets, executive hiring, or technology collaboration

## Skill Overview

Analyze the provided NDA against market-standard review rules derived from 29+ legal team annotations across M&A, SaaS, Medical AI, trade secret, manufacturing, and individual candidate NDAs. Rules are organized into 21 checkable items across 8 categories.

---

## Category A: Confidential Information Definition

### RULE-001 — CI Definition Must Not Be Overly Broad

Verify the definition of "Confidential Information" (비밀정보):

- [ ] Does NOT use catch-all language ("all forms", "all information", "구두·서면·전자적 형식 등 모든 형태", "일체의 정보")
- [ ] Limited to: (a) marked confidential, AND/OR (b) reasonably understood as confidential at disclosure
- [ ] Oral disclosures: confirmed in writing within 30 days
- [ ] Examples of confidential types included (tech specs, business plans, customer data)

**Flag as HIGH risk if:** "모든 형태", "일체", "구두 정보 포함" without written confirmation window.

**Preferred language:**
```
"비밀정보"라 함은 Confidential 또는 이에 상응하는 표시가 된 서면 정보와,
공개 당시 비밀로 인식될 수 있는 정보에 한한다. 구두로 공개된 정보는
공개 후 30일 이내에 서면으로 확인된 경우에 한하여 비밀정보에 포함한다.
```

### RULE-002 — CI Definition Must Not Be Overly Narrow (For Oral Disclosure Contexts)

- [ ] NOT limited to only "written marked information" ("서면으로 Confidential 표시된 정보에 한한다")
- [ ] Oral disclosures covered if marked confidential at disclosure AND confirmed in writing within 30 days

**Flag as MEDIUM risk if:** Written-only definition in contexts where oral disclosure is common (SaaS partnerships, R&D collaboration).

---

## Category B: Exceptions to Confidential Information

### RULE-003 — All Four Standard Exceptions Must Be Present

Every NDA must contain ALL FOUR standard exceptions:

| # | Exception | Required? |
|---|-----------|-----------|
| 1 | Already public / made public through no fault of receiving party | Yes |
| 2 | Already lawfully possessed before disclosure | Yes |
| 3 | Lawfully received from third party without confidentiality obligation | Yes |
| 4 | **Independently developed** (독자개발한 정보) | **Yes — CRITICAL** |
| 5 | Compelled by law/government (optional but recommended) | Recommended |

**Flag as HIGH risk if:** Exception #4 (independent development) is missing — this is the MOST frequently omitted exception (appears in ALL training NDA types).

---

## Category C: Confidentiality Period

### RULE-004 — Confidentiality Period Should Match Market Standard (Typically 3 Years)

| Context | Market Standard | Max Acceptable |
|---------|-----------------|----------------|
| M&A / Due Diligence | 3 years post-termination | 5 years |
| Technology / SaaS | 3 years post-termination | 5 years |
| Medical / Healthcare | 3 years (general), indefinite (health data) | Indefinite for health data |
| Trade secrets | Indefinite (while maintained) | Indefinite |
| Individual recipients | 2–3 years max (indefinite unenforceable) | 5 years absolute max |

**Flag as HIGH risk if:** Term exceeds 5 years, "무기한" (indefinite) for general cooperation, or lacks trade-separate carve-out.

**Anti-patterns:**
- "본 계약 종료 후 7년간" — 7 years is excessive for any standard context
- "기간의 정함 없이" (no period defined) — creates perpetual liability

---

## Category D: Liability & Damages

### RULE-005 — Always Include a Liability Cap

Every NDA must include BOTH:

1. **Limitation to direct damages only** — exclude indirect, consequential, punitive damages
2. **A monetary cap on liability**

| Context | Typical Cap |
|---------|-------------|
| Mutual NDA | USD 100,000 or 12 months of anticipated payments |
| Unilateral NDA (Korean counterparty) | KRW 1 billion |
| Unilateral NDA (US counterparty) | USD 100,000 |
| M&A NDA | Transaction value or fixed sum |
| Individual recipients | Actual damages proof required; cap at 30–50% of annual salary |

**Flag as HIGH risk if:** "직접·간접·결과적 손해 일체" (all direct, indirect, consequential damages) without cap.

### RULE-006 — Penalty / Liquidated Damages Must Be Reasonable

- [ ] Penalty is not disproportionately excessive relative to recipient's ability to pay
- [ ] For individuals: cap at 30–50% of annual salary, or use actual damages proof
- [ ] Language states damages are a "predetermined estimate" (손해배상 예정액), not punitive

**Flag as HIGH risk if:** Fixed penalty (e.g., ₩500,000,000) disproportionate to individual's annual salary.

---

## Category E: Permitted Disclosures

### RULE-007 — Relax Prior Written Consent for Permitted Disclosures

- [ ] Employees: disclosure permitted on need-to-know basis WITHOUT prior written consent
- [ ] Professional advisors (lawyers, accountants): permitted upon imposition of **equivalent confidentiality obligations**
- [ ] No prior written consent requirement for routine employee/advisor sharing

**Preferred language:**
```
"수령자는 본 거래 검토에 필요한 범위 내에서 임직원 및 자문사에게
비밀정보를 제공할 수 있으나, 해당 자에게 본 계약과 동등 이상의
비밀유지 의무를 부과하여야 한다."
```

**Flag as MEDIUM risk if:** "사전의 서면 동의를 얻어야 한다" for employee/advisor sharing — creates impractical friction.

### RULE-008 — Purpose Clause Must Be Narrowly Tailored

- [ ] Purpose is narrow and specific (e.g., "SaaS API 통합 검토", "M&A 실사")
- [ ] Does NOT use overly broad language ("일체의 사업 협의", "any business discussion")

**Flag as MEDIUM risk if:** Purpose clause is broader than the actual intended collaboration.

---

## Category F: Non-Solicitation / Non-Compete

### RULE-009 — Non-Solicitation Period Must Be Reasonable (≤ 12 Months)

If non-solicitation/non-compete clause exists:

- [ ] Non-solicitation duration ≤ 12 months
- [ ] Limited to employees encountered through the NDA relationship only ("본 계약을 통해 알게 된 임직원")
- [ ] Does NOT prohibit "indirect" contact (overly broad)
- [ ] Does NOT include non-compete (동종·유사 사업 영위 금지) within the NDA body
- [ ] Complies with Korean Labor Standards Act

**Flag as HIGH risk if:**
- 18+ month non-solicitation duration (e.g., 24 months)
- Non-compete clause embedded in NDA
- Individual recipient subject to corporate non-solicit/non-compete clauses

**Action:** Separate non-compete into distinct employment agreement with reasonableness test (necessity, consideration, duration, geography).

---

## Category G: Return / Destruction

### RULE-012 — Require Destruction Certificate on Return / Destruction

- [ ] Specific timeline: 5 business days (fast) or 30 days (reasonable)
- [ ] **Destruction certificate:** officer-signed written confirmation required for corporations; written confirmation for individuals
- [ ] Archival copy exception for regulatory compliance
- [ ] Covers electronic copies and derivatives
- [ ] Certificate required within 30 days of termination or upon request

**Flag as MEDIUM risk if:** "반환 또는 파기" obligation without destruction certificate requirement.

---

## Category H: Governing Law & Dispute Resolution

### RULE-013 — Governing Law / Jurisdiction Must Favor the Receiving Party's Home Jurisdiction

Priority hierarchy for Korean party:

| Priority | Preferred Terms | When to Accept |
|----------|-----------------|----------------|
| 1st | Korean law + Seoul Central District Court (서울중앙지방법원) | Default position |
| 2nd | Singapore arbitration (SIAC rules) | Neutral forum acceptable |
| 3rd | US state court jurisdiction | **Flag as negotiation blocker** — high cost, potential bias |

**Flag as HIGH risk if:** Delaware Chancery Court, California superior court, or any US state court without SIAC arbitration fallback.

---

## Category I: Miscellaneous / Structural Clauses

### RULE-015 — Include a Non-Binding / No-Obligation Clause

**Flag as HIGH risk if:** No-binding clause missing — NDA could be construed as preliminary agreement creating negotiation obligation.

**Preferred language:**
```
"본 계약은 어떠한 거래 의무도 발생시키지 않으며,
양 당사자는 언제든 협상을 중단할 수 있다.
본 계약은 최종 거래 계약 체결을 강제하지 않는다."
```

### RULE-014 — Include a Notice Clause with Both Parties' Contact Information

Notice clause should include:

- [ ] Both parties' addresses and emails (two-way)
- [ ] Accepted delivery methods (written, email)
- [ ] Default: email deemed received 5 business days after sending
- [ ] Breach, termination, and rescission notification methods

**Flag as LOW-MEDIUM risk if:** No notice provision, one-sided addresses, or email confirmation required for effectiveness.

### RULE-016 — Include a Residuals Clause (For Technical / Software Contexts)

- [ ] Present in technical, software, or R&D contexts
- [ ] States that general knowledge retained in memory is not restricted

**Flag as MEDIUM risk if:** No residuals clause in SaaS/API or AI collaboration NDA.

**Preferred language:**
```
"본 계약은 메모리에 잔존하는 일반 지식의 사용을 금지하지 아니한다.
기술 종사자가 자연스럽게 학습한 일반적 지식과 기술은
본 계약의 제한을 받지 않는다."
```

### RULE-017 — Include a Change of Control / Assignment Provision

- [ ] Addresses what happens in M&A, merger, acquisition scenarios
- [ ] Either allows assignment to successor with binding agreement, or states automatic termination upon change of control

**Flag as MEDIUM risk if:** No-assignment clause present but no change-of-control exception.

### RULE-018 — Clarify Relationship with Future Employment Agreement (For Candidate NDAs)

When NDA is used during recruitment / candidate interview process:

- [ ] Specifies whether NDA terminates upon hiring, merges into employment agreement, or continues separately
- [ ] Avoids ambiguity about NDA survival after employment begins

**Flag as MEDIUM risk if:** No clarity on NDA relationship to future employment agreement.

### RULE-019 — Address Personal Data / PII Handling

When shared information may include personal data (employee records, customer PII, candidate data):

- [ ] Personal data handling clause included
- [ ] Categories of personal data identified
- [ ] Legal basis for processing stated
- [ ] PIPA compliance referenced (특히 제17조 제3자 제공, 제28조의2 가명정보)

**Flag as MEDIUM risk if:** Personal data shared under NDA without specific data-protection provisions.

### RULE-021 — Include an Entire-Agreement Clause

- [ ] States that the NDA constitutes the complete agreement and supersedes prior negotiations, emails, or LOIs

**Flag as LOW risk if:** Missing entire-agreement clause.

**Preferred language:**
```
"본 계약은 양 당사자 간 본 목적에 관한 완전한 합의를 구성하며,
본 계약과 충돌하는 종전의 합의에 우선한다."
```

---

## Output Format

Return a structured review report:

```markdown
# NDA Review Report

## Document Summary
- Type: [Mutual/Unilateral]
- Context: [M&A / SaaS / Medical / Trade Secret / Technology / Individual / General]
- Parties: [e.g., Korean vs. US, Individual vs. Corporation]
- Governing Law: [if specified]

## Risk Summary
- High Risk Items: [count]
- Medium Risk Items: [count]
- Low Risk Items: [count]

## Detailed Findings

### [Finding #] — [Clause Title]
**Risk:** High/Medium/Low | **Rule:** RULE-XXX

**Current Language:** (quote or summarize the clause)

**Issue:** (explain why it's problematic)

**Recommendation:** (provide preferred language or specific revision)
```

## Key Principles

1. **Korean party protection** — all rules default to favoring the Korean reviewing party
2. **Market standard benchmark** — compare every term against the standards above
3. **Context-aware** — apply industry-specific addenda based on NDA context (M&A, SaaS, Healthcare, Trade Secret, Individual)
4. **Actionable** — always provide specific alternative language, not just "change this"
5. **Escalation** — flag US jurisdiction as negotiation blocker; missing independent development as critical; uncapped liability as HIGH risk
6. **Trade secret awareness** — dual-term structure (fixed + indefinite), separate from general confidentiality
7. **Individual protection** — different rules for natural persons vs. corporations

## Rule Quick Reference

| Rule | Topic | Severity |
|------|-------|----------|
| RULE-001 | Confidential Info Definition | High |
| RULE-002 | Independent Development Exception | High |
| RULE-003 | NDA Term Limits | High |
| RULE-004 | Third-Party Sharing (No Prior Consent) | Medium |
| RULE-005 | Liability Cap & Direct Damages | High |
| RULE-006 | Non-Solicitation/Non-Compete Reasonableness | High |
| RULE-007 | Return/Destruction Certificate | Medium |
| RULE-008 | Governing Law & Jurisdiction | High |
| RULE-009 | Boilerplate (No-Binding, Notice, etc.) | Varies |
| RULE-010 | Purpose Clause Specificity | Medium |
| RULE-011 | Notice Provision (Two-Way) | Low-Medium |
| RULE-012 | Subcontractor Liability | High |
| RULE-013 | Individual Recipient Protection | High |
| RULE-014 | Healthcare Data Processing | High |
| RULE-015 | AI/Tech IP Ownership & Residuals | High |
| RULE-016 | SaaS Residuals Clause | Medium |
| RULE-017 | Trade Secret Dual-Term Structure | High |
| RULE-011 | Mutual vs. Unilateral Selection | Medium |
