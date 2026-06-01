---
name: skill-nda-review
description: Review Non-Disclosure Agreements (NDA) for Korean parties, identifying high-risk clauses and recommending market-standard alternatives. Use when a user asks to review, analyze, or check an NDA, confidentiality agreement, or CDA — especially Korean contracts with M&A, SaaS, medical AI, executive recruitment, trade secret, or technology collaboration contexts.
---

# NDA Contract Review Skill

Review Non-Disclosure Agreements (NDA) for Korean parties, identifying high-risk clauses and recommending market-standard alternatives.

## When to Use

- User uploads or pastes an NDA (Korean, English, or bilingual)
- User asks to "review my NDA", "NDA 검토해줘", "계약서 봐줘"
- Any contract labeled as NDA, confidentiality agreement, or CDA

## Skill Overview

Analyze the provided NDA against market-standard review rules derived from 30+ legal team annotations across M&A, SaaS, Medical AI, executive recruitment, trade secret, and technology collaboration NDAs.

---

## Review Workflow

### Step 1: Identify NDA Type and Context

Determine the following before applying rules:

| Attribute | Options |
|-----------|---------|
| Direction | **Mutual** (양방향) or **Unilateral** (단방향) |
| Context | M&A/Due Diligence, SaaS/API, Medical/AI, Executive Recruitment, Trade Secret/Manufacturing, Technology, General |
| Parties | Korean vs. Korean, Korean vs. US, Korean vs. Other |
| Recipient Type | **Company (법인)** or **Individual (자연인)** |

**RULE-011 (Information-Flow Asymmetry):** Before committing to mutual form, map expected information flow. If one party discloses >80%, request unilateral NDA.

**RULE-023 (Individual vs. Company):** If the receiving party is an individual (e.g., executive candidate, contractor), apply enhanced protections (see RULE-020, RULE-021, RULE-022).

---

### Step 2: Check Confidential Information Definition (RULE-001)

Verify the definition of "Confidential Information" (비밀정보):

- [ ] Does NOT use catch-all language ("all forms", "all information", "일체의 정보")
- [ ] Limited to: (a) marked confidential, AND/OR (b) reasonably understood as confidential at disclosure
- [ ] Oral disclosures: confirmed in writing within 30 days
- [ ] Examples of confidential types included (tech specs, business plans, customer data)
- [ ] Purpose clause is specific (not "any business discussion" — see RULE-016)

**Flag as HIGH risk if:** "모든 형태", "일체", "구두 정보 포함" without written confirmation window.

**RULE-014 (Purpose Clause Must Be Specific):** Overly broad purpose clauses ("any business discussion," "possible collaboration") allow the receiving party to use confidential information for unrelated purposes. Flag as Medium.

**Preferred language:**
```
"비밀정보"라 함은 Confidential 또는 이에 상응하는 표시가 된 서면 정보와,
공개 당시 비밀로 인식될 수 있는 정보에 한한다. 구두로 공개된 정보는
공개 후 30일 이내에 서면으로 확인된 경우에 한하여 비밀정보에 포함한다.

본 계약의 목적: [구체적인 프로젝트 또는 평가 목적]
```

---

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

---

### Step 4: Review Non-Disclosure Period (RULE-003)

| Context | Market Standard | Max Acceptable |
|---------|-----------------|----------------|
| M&A / Due Diligence | 3 years post-termination | 5 years |
| Technology / SaaS | 3 years post-termination | 5 years |
| General cooperation | 3 years | 5 years |
| Medical / Healthcare | 3 years (general), indefinite (personal data) | Indefinite for health data |
| Trade secrets | Indefinite (separate dual-period structure) | Indefinite |

**Flag as HIGH risk if:**
- General confidentiality period exceeds 5 years or is indefinite (for non-trade-secret information)
- Lacks dual-period structure (finite term + separate trade secret carve-out)

**Anti-pattern:** "본 계약 종료 후 7년간" — 7 years is excessive. "무기한" (indefinite) is rarely enforceable.

**RULE-024 (Dual-Period Structure for Trade Secrets):** The NDA should separate general confidentiality period from trade secret protection:
- General term: 3 years post-termination
- Trade secrets: Indefinite, governed by separate provisions

**Suggested fix:** "본 계약 종료 후 3년간. 단, 영업비밀에 대하여는 별도 법정에 따른다."

---

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

---

### Step 6: Review Non-Solicitation & Non-Compete (RULE-005, RULE-007)

#### Non-Solicitation (RULE-005)
If non-solicitation clause exists:

- [ ] Duration ≤ 12 months (12+ months is excess; flag as HIGH)
- [ ] Limited to employees encountered through the NDA relationship
- [ ] Does NOT prohibit "indirect" contact (overly broad)
- [ ] Complies with Korean Labor Standards Act

**Flag as HIGH risk if:** 12+ month duration, or blanket prohibition on all employee contact.

#### Non-Compete (RULE-007)
- [ ] Non-compete clause is NOT embedded in the NDA
- [ ] If present, flag as **HIGH** and recommend moving to a separate agreement

Non-compete (경업금지) clauses embedded in NDA templates are problematic under Korean law:
- They restrict freedom of occupation (직업선택의 자유)
- Courts require: business-necessity, consideration (반대급부), reasonable scope (period/region)
- They should be in a **separate agreement** (e.g., employment contract)

---

### Step 7: Governing Law & Jurisdiction (RULE-006)

Priority hierarchy for Korean party:

| Priority | Preferred Terms | When to Accept |
|----------|-----------------|----------------|
| 1st | Korean law + Seoul Central District Court | Default position |
| 2nd | Singapore arbitration (SIAC rules) | Neutral forum acceptable |
| 3rd | US state court jurisdiction | **Flag as negotiation blocker** — high cost, potential bias |

**Flag if:** Delaware Chancery Court, California superior court, or any US state court without SIAC arbitration fallback.

---

### Step 8: Representatives & Sub-contractors (RULE-008)

- [ ] NO prior written consent required for employees (need-to-know basis)
- [ ] Professional advisors (lawyers, accountants) permitted upon imposition of **equivalent confidentiality obligations**
- [ ] Sub-contractors: primary party assumes vicarious liability for breaches
- [ ] **Sub-tier subcontracting:** if subcontractors are further subcontracting, extend equivalent confidentiality obligations downstream

**Preferred language:**
```
"수령자는 본 거래 검토에 필요한 범위 내에서 임직원 및 자문사에게
비밀정보를 제공할 수 있으나, 해당 자에게 본 계약과 동등 이상의
비밀유지 의무를 부과하여야 한다."
```

**RULE-026 (Trade Secret — Anti-Unfair-Competition Law):** For trade secret NDAs, reference Korea's Trade Secret Protection Act (부정경쟁방지법). Define trade secret using the three-element test:
1. Information not readily accessible to the public (비공상성)
2. Actual use for business purposes (영업이용성)
3. Confidentiality measures taken (비밀유지성)

---

### Step 9: Return & Destruction (RULE-009)

- [ ] Specific timeline: 5 business days (fast) or 30 days (reasonable)
- [ ] **Destruction certificate:** officer-signed written confirmation required
- [ ] Archival copy exception for regulatory compliance
- [ ] Covers electronic copies and derivatives

**RULE-019 (Destruction Certificate for Individuals):** When the recipient is an individual, destruction certificate should be signed in writing (not officer-seal).

---

### Step 10: Check Boilerplate Clauses (RULE-010)

Verify presence of these standard clauses:

| Clause | Purpose |
|--------|---------|
| No-binding / No-obligation (RULE-015) | Prevents forced transactions |
| Notice method with deemed-receipt (RULE-017) | Prevents disputes about notice delivery |
| Residuals clause (tech) (RULE-018) | Engineers can use general knowledge |
| Change of control (RULE-022) | Protects against unexpected M&A changes |
| No-assignment clause | Restricts transferring rights/obligations |

**RULE-015 (No-Deal-Obligation):** Add clause: "본 계약은 어떠한 거래 의무도 발생시키지 않으며, 양 당사자는 언제든 협상을 중단할 수 있다." Flag as High if missing — NDA could be construed as preliminary agreement.

**RULE-017 (Notice Clause Must Cover Both Parties):** The notice clause must:
1. Specify contact information for **both** parties (name, address, email)
2. Define deemed receipt (e.g., email sent + 5 business days = delivered)
3. Avoid requiring "reply confirmation" for email, which creates uncertainty

**RULE-018 (Residuals / General-Knowledge Clause):** For technical collaborations, include:
> "본 계약은 메모리에 잔존하는 일반 지식의 사용을 금지하지 아니한다."
> (This NDA does not prohibit the use of general knowledge retained in personnel's memories.)

**RULE-022 (Assignment / Change of Control):** The assignment clause should include a Change of Control provision: either automatic binding on successors, or the right to require consent upon CoC.

---

### Step 11: Industry-Specific Provisions (RULE-012)

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
- [ ] Enhanced language for IP co-ownership in joint AI projects

#### SaaS / Software Integration
- [ ] Purpose scope specific (not "any business discussion")
- [ ] Residuals clause essential
- [ ] Source code and technical specs receive highest protection
- [ ] Mutual form appropriate when both parties share technical information

#### Executive Recruitment (Individual Candidate)
- [ ] Liquidated damages proportional to individual income (not fixed corporate levels)
- [ ] Non-compete should NOT be in the NDA — separate employment agreement required
- [ ] Clarify relationship with future employment contract (RULE-021)
- [ ] Infinite confidentiality terms flagged as High risk
- [ ] Damage amounts capped at 30-50% of annual salary at most

#### Trade Secret / Manufacturing
- [ ] Anti-Unfair-Competition Law (부정경쟁방지법) references
- [ ] Triple-test for trade secret definition (공상성, 영업이용성, 비밀유지성)
- [ ] Dual-period structure (finite general term + indefinite trade secret protection)
- [ ] Sub-tier subcontracting confidentiality obligations
- [ ] Physical and digital security measures specified

---

## Individual Recipient Enhancements (Natural Person NDA)

When the receiving party is an individual (e.g., executive candidate, contractor):

**RULE-020 (Liability Proportionality):** Liquidated damages should be proportional to individual income. Cap at 30-50% of annual salary.

**RULE-021 (Employment Contract Relationship):** Clarify how the NDA relates to the future employment contract. Non-compete, non-solicitation, and certain performance provisions should move to the employment agreement.

**RULE-023 (Individual Destruction):** For individuals, destruction certificates should be signed in writing (no officer seal required).

---

## Output Format

Return a structured review report:

```markdown
# NDA Review Report

## Document Summary
- Type: [Mutual/Unilateral]
- Context: [M&A / SaaS / Medical / Technology / Executive Recruitment / Trade Secret / General]
- Parties: [e.g., Korean vs. US]
- Recipient Type: [Company/Individual]

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
5. **Escalation** — flag US jurisdiction as negotiation blocker; missing independent development as critical; non-compete in NDA as High
6. **Recipient-type-aware** — apply enhanced protections for individual recipients

## Rule Quick Reference

| Rule | Topic | Severity |
|------|-------|----------|
| RULE-001 | Confidential Info Definition | High |
| RULE-002 | Independent Development Exception | High |
| RULE-003 | NDA Term Limits | High |
| RULE-004 | Liability Cap | High |
| RULE-005 | Non-Solicit Reasonableness | High |
| RULE-006 | Governing Law/Jurisdiction | Medium-High |
| RULE-007 | Non-Compete Must Be Separate | High |
| RULE-008 | Prior Consent for Representatives | Medium |
| RULE-009 | Return/Destruction Certificate | Medium |
| RULE-010 | Missing Boilerplate | Varies |
| RULE-011 | Mutual vs. Unilateral / Info-Flow Asymmetry | Medium |
| RULE-012 | Industry-Specific Addenda | Context |
| RULE-013 | — | (reserved) |
| RULE-014 | Purpose Clause Specificity | Medium |
| RULE-015 | No-Deal-Obligation Clause | High |
| RULE-016 | — | (reserved) |
| RULE-017 | Notice Clause Both Parties | Medium |
| RULE-018 | Residuals / General-Knowledge | Medium |
| RULE-019 | Individual Destruction Certificate | Medium |
| RULE-020 | Individual Liability Proportionality | High |
| RULE-021 | Individual vs. Employment Contract | Medium-High |
| RULE-022 | Assignment / Change of Control | Medium |
| RULE-023 | Individual Recipient Enhancements | High |
| RULE-024 | Trade Secret Dual-Period Structure | High |
| RULE-025 | — | (reserved) |
| RULE-026 | Trade Secret Triple-Test / Anti-UCPL | High |
