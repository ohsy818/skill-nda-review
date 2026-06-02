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

Analyze the provided NDA against market-standard review rules derived from 25+ legal team annotations across M&A, SaaS, Medical AI, trade secret, manufacturing, and individual candidate NDAs.

---

## Review Workflow

### Phase 1: Context Assessment

Before applying rules, determine:

| Attribute | Options |
|-----------|---------|
| Direction | **Mutual** (양방향) or **Unilateral** (단방향) |
| Context | M&A/DD, SaaS/API, Medical/AI, Trade Secret, Tech Collaboration, Individual Hire, General |
| Parties | Korean vs. Korean, Korean vs. US, Korean vs. Other, Individual (자연인) |

**RULE-011 (Mutual vs. Unilateral):** Map expected information flow. If one party discloses >80%, request unilateral NDA. "Mutual" label may mask asymmetric disclosure (RULE-015).

### Phase 2: Core Confidentiality Rules

#### Check Confidential Information Definition (RULE-001)

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

#### Verify All Four Exceptions (RULE-002)

Every NDA must contain ALL FOUR standard exceptions:

| # | Exception | Required? |
|---|-----------|-----------|
| 1 | Already public / made public through no fault of receiving party | Yes |
| 2 | Already lawfully possessed before disclosure | Yes |
| 3 | Lawfully received from third party without confidentiality obligation | Yes |
| 4 | **Independently developed** (독자개발한 정보) | **Yes — CRITICAL** |
| 5 | Compelled by law/government (optional but recommended) | Recommended |

**Flag as HIGH risk if:** Exception #4 (independent development) is missing — this is the MOST frequently omitted exception (appears in ALL training NDA types).

#### Review Non-Disclosure Period (RULE-003)

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

#### Verify Third-Party Sharing Terms (RULE-004)

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

#### Check Liability & Damages (RULE-005)

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

### Phase 3: Protection Scope Rules

#### Review Non-Solicitation (RULE-006)

If non-solicitation/non-compete clause exists:

- [ ] Non-solicitation duration ≤ 12 months
- [ ] Limited to employees encountered through the NDA relationship only
- [ ] Does NOT prohibit "indirect" contact (overly broad)
- [ ] Does NOT include non-compete (동종·유사 사업 영위 금지) within the NDA body
- [ ] Complies with Korean Labor Standards Act

**Flag as HIGH risk if:**
- 18+ month non-solicitation duration
- Non-compete clause embedded in NDA
- Individual recipient subject to corporate non-solicit/non-compete clauses

**Action:** Separate non-compete into distinct employment agreement with reasonableness test (necessity, consideration, duration, geography).

#### Check Return & Destruction (RULE-007)

- [ ] Specific timeline: 5 business days (fast) or 30 days (reasonable)
- [ ] **Destruction certificate:** officer-signed written confirmation required for corporations; written confirmation for individuals
- [ ] Archival copy exception for regulatory compliance
- [ ] Covers electronic copies and derivatives
- [ ] Certificate required within 30 days of termination or upon request

**Flag as MEDIUM risk if:** "반환 또는 파기" obligation without destruction certificate requirement.

### Phase 4: Legal Framework Rules

#### Governing Law & Jurisdiction (RULE-008)

Priority hierarchy for Korean party:

| Priority | Preferred Terms | When to Accept |
|----------|-----------------|----------------|
| 1st | Korean law + Seoul Central District Court (서울중앙지방법원) | Default position |
| 2nd | Singapore arbitration (SIAC rules) | Neutral forum acceptable |
| 3rd | US state court jurisdiction | **Flag as negotiation blocker** — high cost, potential bias |

**Flag as HIGH risk if:** Delaware Chancery Court, California superior court, or any US state court without SIAC arbitration fallback.

#### Check Boilerplate Clauses (RULE-009)

Verify presence of these standard clauses:

| Clause | Purpose |
|--------|---------|
| No-binding / No-obligation | Prevents forced transactions |
| Notice method with deemed-receipt | Prevents disputes about notice delivery |
| Residuals clause (tech/SaaS) | Engineers can use general knowledge |
| Change of control | Protects against unexpected M&A/ownership changes |
| No-assignment clause | Restricts transferring rights/obligations |

**Flag as HIGH risk if:** No-binding clause missing — NDA could be construed as preliminary agreement creating negotiation obligation.

**Flag as MEDIUM risk if:** Notice clause is one-sided (only one party's address) or email default requires recipient confirmation for effectiveness.

#### Verify Purpose Clause (RULE-010)

- [ ] Purpose is narrow and specific (e.g., "SaaS API 통합 검토", "M&A 실사")
- [ ] Does NOT use overly broad language ("일체의 사업 협의", "any business discussion")

**Flag as MEDIUM risk if:** Purpose clause is broader than the actual intended collaboration.

#### Subcontractor Liability (RULE-012)

- [ ] Primary party assumes vicarious liability for subcontractor breaches
- [ ] Prior written consent required for subcontracting
- [ ] Equivalent confidentiality obligations imposed on subcontractors

**Flag as HIGH risk if:** Subcontracting permitted without corresponding liability inheritance provision ("수임자는 자신의 하수급인의 행위에 대하여도 동일한 책임을 진다").

### Phase 5: Industry-Specific Rules

#### Individual Recipients (RULE-013)

When one party is an individual natural person (자연인):

- [ ] Remove corporate-specific clauses (non-solicit, non-compete) from the NDA
- [ ] Handle non-compete in a separate employment agreement
- [ ] Liability/penalties proportional to individual's financial capacity
- [ ] PII handling addressed (Privacy Law compliance)
- [ ] Avoid indefinite confidentiality obligations
- [ ] Clarify NDA survival: terminates automatically upon employment or merges into employment agreement

**Flag as HIGH risk if:** Individual subject to corporate NDA terms with fixed liquidated damages (위약금).

**Flag as HIGH risk for individuals:** Fixed penalty amounts disproportionate to annual salary. Cap at 30–50% of salary or require actual damages proof.

#### Medical / Healthcare Data (RULE-014)

When NDA involves patient medical data or healthcare research data:

- [ ] Separate Personal Information Processing Agreement (PIPA Art. 26)
- [ ] Anonymization standards (K-Anonymous, differential privacy) or pseudonymization criteria (PIPA Arts. 28-2 through 28-7)
- [ ] Cross-border transfer consent if cloud processing (PIPA Art. 28-8)
- [ ] Concrete security controls (ISMS-P, ISO 27701, network segregation, encryption)
- [ ] Data breach notification: 72-hour written notice + PIPA Art. 34 subject notification
- [ ] Personal information protection liability insurance

**Flag as HIGH risk if:** Medical data treated as generic confidential information without separate processing agreement.

#### AI / Technology Collaboration (RULE-015)

When NDA involves AI model development, training data, or tech collaboration:

- [ ] IP ownership explicitly allocated (avoid joint ownership without commercial terms)
- [ ] Data provider retains data contributor rights; tech developer owns model IP with free non-exclusive usage license
- [ ] Sub-contractor liability succession clause
- [ ] Training data provenance documented
- [ ] Residuals clause essential (engineers can use general knowledge retained in memory)

**Flag as HIGH risk if:** "공동으로 보유한다" (joint ownership) of AI models, model weights, or clinical evaluation results — creates commercialization deadlock.

#### SaaS / Software Integration (RULE-016)

When NDA involves SaaS platform or API integration:

- [ ] Purpose scope specific (not "any business discussion")
- [ ] Residuals clause present ("본 계약은 메모리에 잔존하는 일반 지식의 사용을 금지하지 아니한다")
- [ ] Source code and technical specs receive highest protection
- [ ] Mutual form appropriate when both parties share technical information

#### Trade Secret NDA (RULE-017)

When NDA involves trade secrets (technical drawings, process specs, manufacturing know-how):

- [ ] **Dual-term structure:** fixed term (e.g., 3 years) for general info + indefinite protection for trade secrets
- [ ] Trade secret definition: (i) non-public assertion, (ii) economic utility, (iii) reasonable secrecy management
- [ ] Employee access restricted to "employees directly involved" + individual confidentiality agreements required
- [ ] Damages reference Unfair Competition Prevention Act (부정경쟁방지법) Art. 14-2
- [ ] Explicit injunctive relief clause (production prohibition, return of materials)
- [ ] Criminal prosecution rights preserved (UCPA Art. 18: up to 10 years imprisonment)

**Flag as HIGH risk if:** Trade secrets subject to fixed confidentiality term; employee access unrestricted; damages clause references only "실손해" without statutory presumption.

### Phase 6: Documentation & Communication

#### Check Notice Provision (RULE-011)

Notice clause should include:

- [ ] Both parties' addresses and emails (two-way)
- [ ] Accepted delivery methods (written, email)
- [ ] Default: email deemed received 5 business days after sending
- [ ] Breach, termination, and rescission notification methods

**Flag as LOW-MEDIUM risk if:** No notice provision, one-sided addresses, or email confirmation required for effectiveness.

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
