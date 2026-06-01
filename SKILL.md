---
name: skill-nda-review
description: Review Non-Disclosure Agreements (NDA) for Korean parties, identifying high-risk clauses and recommending market-standard alternatives. Use when a user asks to review, analyze, or check an NDA, confidentiality agreement, or CDA — especially Korean contracts with M&A, SaaS, medical AI, or technology collaboration contexts.
---

# NDA Contract Review Skill

Review Non-Disclosure Agreements (NDA) for Korean parties, identifying high-risk clauses and recommending market-standard alternatives.

## When to Use

- User uploads or pastes an NDA (Korean, English, or bilingual)
- User asks to "review my NDA", "NDA 검토해줘", "계약서 봐줘"
- Any contract labeled as NDA, confidentiality agreement, or CDA

## Skill Overview

Analyze the provided NDA against market-standard review rules derived from 30+ legal team annotations across M&A, SaaS, Medical AI, and manufacturing NDAs.

---

## Review Workflow

### Step 1: Identify NDA Type

Determine the following before applying rules:

| Attribute | Options |
|-----------|---------|
| Direction | **Mutual** (양방향) or **Unilateral** (단방향) |
| Context | M&A/Due Diligence, SaaS/API, Medical/AI, Technology, General |
| Parties | Korean vs. Korean, Korean vs. US, Korean vs. Other |

**RULE-011 (Mutual vs. Unilateral):** Before committing to mutual form, map expected information flow. If one party discloses >80%, request unilateral NDA.

### Step 2: Check Confidential Information Definition (RULE-001)

Verify the definition of "Confidential Information" (비밀정보):

- [ ] Does NOT use catch-all language ("all forms", "all information", "일체의 정보")
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

### Step 3: Verify All Four Exceptions (RULE-002)

Every NDA must contain ALL FOUR standard exceptions:

| # | Exception | Required? |
|---|-----------|-----------|
| 1 | Already public / made public through no fault of receiving party | Yes |
| 2 | Already lawfully possessed before disclosure | Yes |
| 3 | Lawfully received from third party without confidentiality obligation | Yes |
| 4 | **Independently developed** (독자개발한 정보) | **Yes — CRITICAL** |
| 5 | Compelled by law/government (optional but recommended) | Recommended |

**Flag as HIGH risk if:** Exception #4 (independent development) is missing — this is the MOST frequently omitted exception.

### Step 4: Review Non-Disclosure Period (RULE-003)

| Context | Market Standard | Max Acceptable |
|---------|-----------------|----------------|
| M&A / Due Diligence | 3 years post-termination | 5 years |
| Technology / SaaS | 3 years post-termination | 5 years |
| Medical / Healthcare | 3 years (general), indefinite (personal data) | Indefinite for health data |
| Trade secrets | Indefinite protection | Indefinite protection |

**Flag as HIGH risk if:** Term exceeds 5 years or lacks trade-separate carve-out.

**Anti-pattern:** "본 계약 종료 후 7년간" — 7 years is excessive.

### Step 5: Check Liability & Damages (RULE-004)

Every NDA must include BOTH:

1. **Limitation to direct damages only** — exclude indirect, consequential, punitive damages
2. **A monetary cap on liability**

| Context | Typical Cap |
|---------|-------------|
| Mutual NDA | USD 100,000 or 12 months of anticipated payments |
| Unilateral NDA | Fixed sum (e.g., KRW 1 billion) |
| M&A NDA | Transaction value or fixed sum |

**Flag as HIGH risk if:** "직접·간접·결과적 손해 일체" (all direct, indirect, consequential damages) without cap.

### Step 6: Review Non-Solicitation (RULE-005)

If non-solicitation clause exists:

- [ ] Duration ≤ 12 months (24+ months is excessive)
- [ ] Limited to employees encountered through the NDA relationship
- [ ] Does NOT prohibit "indirect" contact (overly broad)
- [ ] Complies with Korean Labor Standards Act

**Flag as HIGH risk if:** 24+ month duration, or blanket prohibition on all employee contact.

### Step 7: Governing Law & Jurisdiction (RULE-006)

Priority hierarchy for Korean party:

| Priority | Preferred Terms | When to Accept |
|----------|-----------------|----------------|
| 1st | Korean law + Seoul Central District Court | Default position |
| 2nd | Singapore arbitration (SIAC rules) | Neutral forum acceptable |
| 3rd | US state court jurisdiction | **Flag as negotiation blocker** — high cost, potential bias |

**Flag if:** Delaware Chancery Court, California superior court, or any US state court without SIAC arbitration fallback.

### Step 8: Representatives & Sub-contractors (RULE-007)

- [ ] NO prior written consent required for employees (need-to-know basis)
- [ ] Professional advisors (lawyers, accountants) permitted upon imposition of **equivalent confidentiality obligations**
- [ ] Sub-contractors: primary party assumes vicarious liability for breaches

**Preferred language:**
```
"수령자는 본 거래 검토에 필요한 범위 내에서 임직원 및 자문사에게
비밀정보를 제공할 수 있으나, 해당 자에게 본 계약과 동등 이상의
비밀유지 의무를 부과하여야 한다."
```

### Step 9: Return & Destruction (RULE-008)

- [ ] Specific timeline: 5 business days (fast) or 30 days (reasonable)
- [ ] **Destruction certificate:** officer-signed written confirmation required
- [ ] Archival copy exception for regulatory compliance
- [ ] Covers electronic copies and derivatives

### Step 10: Check Boilerplate Clauses (RULE-009)

Verify presence of these standard clauses:

| Clause | Purpose |
|--------|---------|
| No-binding / No-obligation | Prevents forced transactions |
| Notice method with deemed-receipt | Prevents disputes about notice delivery |
| Residuals clause (tech) | Engineers can use general knowledge |
| Change of control | Protects against unexpected M&A changes |
| No-assignment clause | Restricts transferring rights/obligations |

**Flag as MEDIUM risk if:** No-binding clause missing (NDA could be construed as preliminary agreement).

### Step 11: Industry-Specific Provisions (RULE-010)

Add based on context:

#### Medical / Healthcare Data
- [ ] Separate Personal Information Processing Agreement (PIPA Art. 26)
- [ ] Anonymization standards (K-Anonymous, differential privacy)
- [ ] Cross-border transfer consent (PIPA Art. 28-8)
- [ ] Security controls: ISMS-P or ISO 27701
- [ ] Data breach notification: 72 hours + written report + subject notice (PIPA Art. 34)
- [ ] Personal information protection liability insurance

#### AI / Technology Collaboration
- [ ] IP ownership explicitly allocated (avoid joint ownership without commercial terms)
- [ ] Data provider retains data rights; AI company owns model IP with usage license
- [ ] Sub-contractor liability succession clause
- [ ] Training data provenance documented

#### SaaS / Software Integration
- [ ] Purpose scope specific (not "any business discussion")
- [ ] Residuals clause essential
- [ ] Source code and technical specs receive highest protection
- [ ] Mutual form appropriate when both parties share technical information

---

## Output Format

Return a structured review report:

```markdown
# NDA Review Report

## Document Summary
- Type: [Mutual/Unilateral]
- Context: [M&A / SaaS / Medical / Technology / General]
- Parties: [e.g., Korean vs. US]

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
3. **Context-aware** — apply industry-specific addenda based on NDA context
4. **Actionable** — always provide specific alternative language, not just "change this"
5. **Escalation** — flag US jurisdiction as negotiation blocker; missing independent development as critical

## Rule Quick Reference

| Rule | Topic | Severity |
|------|-------|----------|
| RULE-001 | Confidential Info Definition | High |
| RULE-002 | Independent Development Exception | High |
| RULE-003 | NDA Term Limits | High |
| RULE-004 | Liability Cap | High |
| RULE-005 | Non-Solicit Reasonableness | High |
| RULE-006 | Governing Law/Jurisdiction | Medium-High |
| RULE-007 | Prior Consent for Representatives | Medium |
| RULE-008 | Return/Destruction Certificate | Medium |
| RULE-009 | Missing Boilerplate | Varies |
| RULE-010 | Industry-Specific Addenda | Context |
| RULE-011 | Mutual vs. Unilateral Selection | Medium |
