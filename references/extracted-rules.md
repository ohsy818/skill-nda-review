# NDA Review Rules (Extracted from Training Documents)

> **Source**: 3 NDA documents (Korean M&A, Mutual SaaS, Executive hiring)
> **Annotations analyzed**: 29 review comments from legal counsel
> **Generated**: Rule-extraction pipeline

---

## R1 — Confidential Information Definition Must Be Reasonably Scoped

**Severity**: HIGH | **Frequency**: 2/3 docs

### The Rule
Never accept an NDA with a confidentiality definition that encompasses "all forms" or "all information" without a reasonable marking or identification requirement.

### Trigger
Look for definitions using phrases such as:
- "모든 형태의 정보" (all forms of information)
- "구두·서면·전자적 형식 등" (oral, written, electronic, etc.)
- "일체의 정보" (all information)

### Expected Fix
Require that confidential information be either:
1. Marked as "Confidential" in writing, OR
2. If disclosed orally, identified as confidential at the time of disclosure and confirmed in writing within a reasonable period (e.g., 30 days)

### Counter-example
> "비밀정보"라 함은 공개자가 수령자에게 제공하는 구두·서면·전자적 형식 등 모든 형태의 정보로서 ... 일체의 정보를 의미한다.
>
> **Annotation**: Definition is overly broad — "all forms" effectively covers every piece of information. Recommend: limit to information that is "marked confidential or that a reasonable person would recognize as confidential at the time of disclosure."

---

## R2 — Confidentiality Period Must Have a Reasonable Maximum

**Severity**: HIGH | **Frequency**: 3/3 docs

### The Rule
Always check that confidentiality obligations have a defined maximum term. Indefinite or excessively long periods (over 5 years for general information) should be flagged and capped.

### Acceptable Standards
| Context | Standard |
|---|---|
| General trade secrets / business info | 2–5 years (prefer 3 years) |
| M&A due diligence | ~3 years |
| Trade secrets (true) | Indefinite, must be explicitly limited to legally-defined trade secrets |
| Individual (employee/candidate) | 3 years post-process (not indefinite) |

### Triggers
- "7년간" (7 years) or longer → flag
- "무기한" (indefinite) → flag, especially for individuals
- No defined term → flag

### Counter-example
> 비밀유지 기간 7년은 시장 표준(2~5년)을 초과 → 3년으로 단축 협상
> 기간의 정함 없이(무기한) → 개인에 대해 무기한 의무는 사실상 이행 불가

---

## R3 — All Four Statutory Exceptions to Confidentiality Must Be Present

**Severity**: HIGH | **Frequency**: 3/3 docs

### The Rule
Every NDA must contain exactly four standard exceptions to confidential information:

1. **Publicly known** — Information that was already public at disclosure or became public through no fault of the receiving party
2. **Already known** — Information the receiving party already lawfully possessed before disclosure
3. **Independently developed** — Information independently developed by the receiving party without use of confidential information
4. **Lawfully received from third party** — Information received from a third party without confidentiality obligations

### Expected Fix
If any exception is missing, require its addition. The "independently developed" and "already known" exceptions are the most commonly omitted.

### Counter-example
> 4대 예외 중 "독자개발(Independently developed)" 누락 → 반드시 추가
> 4대 예외 중 "독자 보유(Already known)" 누락 → 예외 조항에 추가

---

## R4 — Liability Must Have a Cap

**Severity**: HIGH | **Frequency**: 2/3 docs

### The Rule
Never accept unlimited liability. The NDA must specify:
1. A cap on damages (preferably limited to direct damages only, excluding indirect/consequential damages)
2. A numerical or formula-based maximum

### Acceptable Standards
- Cap at a fixed amount (e.g., KRW 1 billion / USD 100,000)
- Cap at a multiple of transaction value
- Cap at fees paid/payable over a defined period
- Mutual cap for mutual NDAs

### Triggers
- "직접·간접·결과적 손해 일체" (all direct, indirect, consequential damages) without cap
- "모든 손해" (all damages) without limitation
- No mention of liability cap anywhere in the document

### Counter-example
> 책임 상한(Liability Cap) 부재. 위반 시 손해배상이 무한정으로 노출됨 → "직접손해에 한정하고, 본 거래 규모 또는 정액을 상한으로 한다" 추가 필수

---

## R5 — Governing Law and Jurisdiction Must Be Neutral or Favorable

**Severity**: HIGH | **Frequency**: 2/3 docs

### The Rule
Flag any NDA where governing law and jurisdiction favor the counterparty's home jurisdiction. Require negotiation toward:
1. **Preferred**: Korean law + Korean court (서울중앙지방법원)
2. **Acceptable alternative**: Singapore arbitration (SIAC)
3. **Avoid**: Counterparty's home state/country court

### Triggers
- Foreign governing law (Delaware, California, etc.)
- Exclusive jurisdiction in foreign courts
- No specified governing law

### Counter-example
> 준거법이 상대방 본사 소재지(델라웨어주) 법으로 되어 있음 → 대한민국법으로 변경 우선 요구. 차선: 싱가포르 중재(SIAC)

---

## R6 — Return/Destruction Must Include Certification

**Severity**: MEDIUM | **Frequency**: 3/3 docs

### The Rule
When an NDA requires return or destruction of confidential information, it must also require a written certification of destruction within a defined timeframe (e.g., 30 days).

### Expected Fix
Add provision: "Within 30 days of termination or request, the receiving party shall deliver a written certificate of destruction, signed by an authorized officer, confirming that all confidential information and copies have been returned or destroyed."

### Triggers
- "반환 또는 파기" (return or destroy) appears without "파기 확인서" (destruction certificate)
- "즉시 파기" (immediate destruction) without follow-up verification

### Counter-example
> 파기 의무는 있으나 파기 확인서(Destruction Certificate) 제출 의무 누락 → 종료 후 30일 이내 임원 서명 확인서 제출 조항 추가

---

## R7 — Permitted Recipients Must Have Equivalent Obligations (Not Prior Consent)

**Severity**: MEDIUM | **Frequency**: 1/3 docs

### The Rule
The NDA should not require the disclosing party's prior written consent for releasing information to employees or professional advisors. Instead, require that:
1. Recipients have a "need to know" for the permitted purpose
2. Recipients are bound by confidentiality obligations at least as protective as the NDA

### Triggers
- "사전의 서면 동의" (prior written consent) required before sharing with affiliates/advisors
- No obligation on affiliates/advisors to maintain confidentiality

### Counter-example
> 임직원·자문사 제공 시 "사전 서면 동의" 요건은 실무상 이행 어려움 → "동등한 비밀유지 의무 부과를 조건으로 제공 가능"으로 완화

---

## R8 — Permitted Purpose Must Be Narrowly Defined

**Severity**: MEDIUM | **Frequency**: 1/3 docs

### The Rule
The NDA's stated purpose for using confidential information must be specific and limited to the actual business context. Broad purpose clauses create excessive liability exposure.

### Triggers
- "일체의 사업 협의" (any business discussion)
- Vague or unspecified purpose
- Purpose broader than the actual engagement

### Expected Fix
Replace broad language with specific purpose (e.g., "SaaS platform API integration evaluation" / "M&A due diligence").

### Counter-example
> 목적이 "any business discussion"으로 광범위 → PoC·API 통합 검토라는 본래 목적으로 한정 권장

---

## R9 — Notice Provisions Must Be Complete and Practical

**Severity**: MEDIUM | **Frequency**: 3/3 docs

### The Rule
Every NDA must include:
1. Contact information (address + email) for BOTH parties
2. Acceptable notice methods (written, email)
3. A deemed-delivery rule (e.g., email deemed received after 5 business days)

### Triggers
- Notice clause mentions only one party's address
- Notice requires receipt confirmation (uncertain delivery timing)
- No notice clause at all
- Email mentioned without deemed-receipt provision

### Counter-example
> 통지(Notice) 조항 누락 / 한쪽 주소만 기재 / 수신 확인 회신을 요구해 실무상 발효 시점이 불명확

---

## R10 — Individual NDA Terms Must Be Proportionate and Separated

**Severity**: HIGH | **Frequency**: 1/3 docs

### The Rule
When the receiving party is an individual (employee candidate, contractor), the NDA must be adjusted for fairness. Certain provisions must NOT be included in the NDA:

| Provision | Treatment |
|---|---|
| Non-solicitation | Separate agreement only; max 12 months; limited to contacts from the process |
| Non-compete | Separate employment agreement; must meet reasonableness (duration, geography, scope, consideration) |
| Liquidated damages | Cannot be excessive; cap at reasonable % of annual compensation (30–50%) or actual damages |
| Indefinite confidentiality | Must have defined term (e.g., 3 years post-process) |
| Personal data | Must comply with PIPA; de-identify PII when sharing |

### Triggers
- NDA is between "회사 대 개인" (company and individual)
- Non-compete clauses embedded in NDA
- Indefinite confidentiality for individual
- Excessive liquidated damages for individual

### Counter-example
> 본 조항은 사실상 경업금지 약정. 우리나라 법원은 NDA에 경업금지를 끼워넣는 것에 부정적 → 별도 약정으로 분리

---

## R11 — Residuals and Change-of-Control Clauses Must Be Addressed

**Severity**: MEDIUM | **Frequency**: 1/3 docs each

### The Rule
**Residuals clause**: For technical/engineering contexts, the NDA must either:
- Explicitly permit use of residuals (general knowledge retained in unaided memory), OR
- Explicitly prohibit residuals

**Change of Control**: The NDA must address what happens if a party undergoes a change of control (M&A, acquisition):
- Either the NDA automatically terminates, or
- The successor must assume obligations, or
- Written consent is required

### Triggers
- Technical collaboration involving source code, APIs, or engineering
- No mention of residuals / general knowledge
- No-assignment clause without Change of Control exception

---

## R12 — No-Binding and Employment-Contract Relationship Must Be Clarified

**Severity**: MEDIUM | **Frequency**: 1/3 docs each

### The Rule
**No-binding clause**: Clarify that the NDA creates no obligation to transact, no exclusive negotiation rights, and either party may walk away at any time.

**Employment NDA**: When an NDA is signed during a hiring process, clarify its relationship with the future employment contract — does it:
- Automatically terminate upon employment, OR
- Absorb into the employment contract, OR
- Continue independently?

### Triggers
- No clause stating "this agreement does not create any obligation to proceed with transactions"
- NDA signed during recruitment with no transition clause
