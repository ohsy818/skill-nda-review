---
name: nda-reviewer
description: NDA (Non-Disclosure Agreement) legal review skill. Review and analyze NDA contracts for risks, missing clauses, unfavorable terms, and compliance issues. Use when users ask to review, analyze, or check NDAs, confidentiality agreements, or secrecy contracts. Also use for "계약서 검토", "NDA 체크", "비밀유지계약 확인", "contract review", "legal check" — even when the user says "check this contract" or "review this agreement" if it's an NDA or confidentiality agreement. This skill covers M&A NDAs, SaaS/partnership NDAs, AI/medical data NDAs, trade secret NDAs, executive/individual NDAs, and any mutual or unilateral confidentiality agreements.
---

# NDA Review Skill

Review NDA (Non-Disclosure Agreement) contracts systematically. Apply the rules below to identify risks, missing clauses, unfavorable terms, and compliance gaps.

## Review Process

1. **Identify NDA type** — unilateral vs. mutual; M&A, SaaS, executive/individual, AI/medical, trade secret, etc.
2. **Scan each section** using the review checklist below
3. **Flag issues** with severity (High / Medium / Low)
4. **Provide specific rewrite suggestions** for each flagged item

## Core Rules

<!-- SLOW_UPDATE_START -->
### R-1: Confidential Information Must Be Reasonably Scoped

Definition must NOT capture "all forms of information" without limitation. Use a dual test:

1. Information **marked as "Confidential"** in writing, OR
2. If oral — identified as confidential at disclosure + confirmed in writing within 30 days

**Bad:** "모든 형태의 정보", "일체의 정보", "구두·서면·전자적 형식 등 모두"
**Good:** "서면으로 'Confidential' 표시를 한 정보, 또는 구두로 공개 시 즉시 비밀 표시 후 30일 이내 서면 확인"

### R-2: Confidentiality Period Must Have a Reasonable Maximum

| Context | Standard |
|---|---|
| General trade secrets / business info | 2–5 years (prefer 3 years) |
| M&A due diligence | ~3 years |
| True trade secrets (legal definition) | Indefinite only — must explicitly limit to statutory trade secrets |
| Individual (employee/candidate) | 3 years post-process, NOT indefinite |

**Red flags:** 7+ years → flag. Indefinite (무기한) → especially for individuals. No defined term → flag.

### R-3: All Four Statutory Exceptions Must Be Present

Every NDA must include EXACTLY these four exceptions:

1. **Publicly known** — was already public or became public through no fault of recipient
2. **Already known** — lawfully possessed before disclosure
3. **Independently developed** — by recipient without use of confidential information ← *most commonly omitted*
4. **Lawfully received from third party** — without confidentiality obligations

**Critical:** The "independently developed" exception is missing from virtually all reviewed NDAs. ALWAYS flag as HIGH if absent.

### R-4: Liability Must Have a Cap

Never accept unlimited liability. Must specify:

1. **Direct damages only** — exclude indirect/consequential damages
2. **Numerical or formula-based maximum**

Acceptable caps:
- Fixed amount (e.g., KRW 1B / USD 100K)
- Multiple of transaction value
- Fees paid/payable over a defined period
- **Mutual cap for mutual NDAs**

**Bad:** "직접·간접·결과적 손해 일체" without cap
**Good:** "배상 책임은 본 계약 직전 12개월 수수료 총액 또는 [정액]을 초과하지 않음"

### R-5: Governing Law Must Be Neutral or Favorable

**Ranking (best → worst):**

1. 🥇 Korean law + Seoul Central District Court (서울중앙지방법원)
2. 🥈 Singapore arbitration (SIAC)
3. 🥉 Korean law + SIAC arbitration
4. ❌ Counterparty's home jurisdiction (Delaware, California, etc.) → **HIGH severity risk**

### R-6: Return/Destruction Must Include Written Certification

When an NDA requires return or destruction, it must ALSO require:

> "Termination or request → within 30 days → written certificate of destruction, signed by authorized officer, confirming all confidential information and copies returned or destroyed."

**Bad:** "즉시 파기" without verification
**Good:** "파기 후 30일 이내 임원 서명 확인서 제출"
<!-- SLOW_UPDATE_END -->

### R-7: Permitted Recipients — Need-to-Know + Equivalent Obligations

Disclosure to employees, affiliates, or professional advisors should NOT require prior written consent. Instead:

1. Recipients must have **"need to know"** for the permitted purpose
2. Recipients must be bound by confidentiality obligations **at least as protective** as the NDA

### R-8: Permitted Purpose Must Be Narrowly Defined

Purpose must be **specific** to the actual business context — not "any business discussion" or "일체의 사업 협의".

**Good:** "SaaS platform API integration evaluation" / "M&A due diligence"
**Bad:** "일체의 사업 협의" (any business discussion)

### R-9: Notice Provisions Must Be Complete

Every NDA must include:

| Element | Requirement |
|---|---|
| Contact info | Address + email for **both** parties |
| Methods | Written, email specified |
| Deemed receipt | e.g., "Email deemed received 5 business days after sending" |

### R-10: Individual NDAs — Proportionality Requirements

When the receiving party is an **individual** (employee candidate, contractor):

| Provision | Rule |
|---|---|
| Non-solicitation | Separate agreement only; max 12 months; limited to contacts from the process |
| Non-compete | Separate employment agreement; must be reasonable (duration, geography, scope) |
| Liquidated damages | Cap at reasonable % of annual compensation (30–50%) or actual damages |
| Confidentiality period | Defined term only (e.g., 3 years post-process) — NEVER indefinite |
| Personal data | Comply with PIPA; de-identify PII when sharing |

**Warning:** Non-compete clauses embedded in an NDA are viewed negatively by Korean courts. Force separate agreements.

### R-11: Residuals and Change-of-Control Must Be Addressed

**Residuals clause:** For technical/engineering contexts, explicitly permit or prohibit use of residuals (general knowledge retained in unaided memory).

**Change of Control:** Address what happens on M&A or acquisition — either:
- NDA automatically terminates, OR
- Successor assumes obligations, OR
- Written consent required

### R-12: No-Binding and Employment Relationship Must Be Clarified

**No-binding clause:** "본 계약은 어떠한 거래 의무도 발생시키지 않으며, 양 당사자는 언제든 협상을 중단할 수 있다."

**Employment NDA:** When signed during hiring, clarify its future relationship:
- Automatically terminates upon employment? OR
- Absorbs into employment contract? OR
- Continues independently?

## Domain-Specific Checks

Read the referenced documents below for domain-specific rules.

## AI / Medical / Health Data NDA

- **R-AI-1:** PIPA Art. 26 — separate Data Processing Agreement (개인정보 처리 위·수탁 계약) required for patient/medical data
- **R-AI-2:** Anonymization standard must be specified — K-anonymity (k≥5) or differential privacy criteria
- **R-AI-3:** Cross-border cloud transfer requires PIPA Art. 28-8 prior patient consent. Prefer domestic-only cloud
- **R-AI-4:** Security measures must be specific — ISMS-P, ISO 27701, network segregation, access logs (3+ years), encryption at rest and in transit
- **R-AI-5:** Incident notification — "72-hour written notice + first report" (PIPA Art. 34)
- **R-AI-6:** IP ownership — no vague "joint ownership." Clear split: hospital/originator keeps data rights, AI vendor keeps model IP with free non-exclusive license
- **R-AI-7:** Insurance obligation (PIPA liability insurance) stated in main text, not just attachment

## Trade Secrets / Manufacturing NDA

- **R-TS-1:** Trade secret definition must include 3 elements: non-publicity (신규성), economic utility (경제적 유용성), secret management (비밀관리 조치)
- **R-TS-2:** Technical drawings must carry "Trade Secret" watermarks
- **R-TS-3:** Unfair Competition Act Art. 14-2 — damages presumed equal to infringer's profit; Art. 18 — criminal complaint (up to 10 years)
- **R-TS-4:** Re-subcontracting requires prior written consent; second-tier subcontractors must have equal obligations
- **R-TS-5:** Employee access restricted to directly involved staff; each must sign a separate confidentiality agreement

## SaaS / Software NDA

- **R-SAAS-1:** Purpose clause must be specific (e.g., "PoC/API integration review") — not "any business discussion"
- **R-SAAS-2:** Residuals clause — allow engineers to use general knowledge and skills not specific to disclosed information
- **R-SAAS-3:** IP split must be clear — no joint ownership of pre-existing IP
- **R-SAAS-4:** Change of Control provision for M&A scenarios — allow assignment to successor

## M&A / Due Diligence NDA

- **R-MA-1:** Confidentiality period = 3 years (not 5–7+ years)
- **R-MA-2:** Non-solicitation max 12 months, limited to employees encountered during due diligence
- **R-MA-3:** Affiliated entities and advisors must receive info under equivalent obligations without prior consent from discloser
- **R-MA-4:** Amendment clause must specify notice methods and effective date

## Executive / Individual NDA

- **R-EXEC-1:** No embedded non-compete — force to separate employment agreement
- **R-EXEC-2:** No indefinite confidentiality — max 3 years post-process
- **R-EXEC-3:** Liquidated damages capped at reasonable % of annual compensation
- **R-EXEC-4:** Personal data compliance with PIPA; de-identify PII

## Output Format

After reviewing an NDA, ALWAYS provide your findings in this structure:

```markdown
# NDA Review Report

**NDA Type**: [unilateral / mutual] — [context: e.g., M&A, SaaS, AI medical, trade secret, executive]

---

## Executive Summary

[2-3 sentences summarizing overall risk level and top 3 critical findings]

---

## Detailed Findings

### [Section Name]

**Severity**: HIGH / MEDIUM / LOW
**Issue**: [What is wrong]
**Current Text**: [Quote the problematic clause]
**Recommendation**: [Specific rewrite suggestion in Korean]

---

## Checklist Summary

| Check | Status | Notes |
|-------|--------|-------|
| Confidential Info Definition | ⚠️ FLAGGED | ... |
| 4 Standard Exceptions | ✅ PASS | ... |
| Confidentiality Period | ⚠️ FLAGGED | ... |
| Liability Cap | ❌ MISSING | ... |
| Governing Law | ⚠️ FLAGGED | ... |
| [etc.] | | |

---

## Summary of Changes Needed

1. **[HIGH]** ...
2. **[HIGH]** ...
3. **[MEDIUM]** ...
```

## Severity Guidelines

- **HIGH**: Fundamental risk to Korean party — missing critical protections, unlimited liability, unfavorable foreign law, missing independent development exception, indefinite confidentiality for individuals
- **MEDIUM**: Significant improvement needed — vague provisions, excessive periods, missing certificates, unclear IP ownership, residuals/change-of-control gaps
- **LOW**: Procedural improvements — notice provisions, formatting, minor clarifications
