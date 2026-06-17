---
name: skill-nda-review
description: NDA(Non-Disclosure Agreement, 비밀유지계약서)를 검토하고 위험 요소를 분석합니다. 비밀정보 정의의 균형, 예외 조항(4대 요소), 비밀유지 기간, 책임상한, 준거법/관할, 파기확인서, 비차단선언 등 15개 핵심 검토 규칙을 적용하여 NDA 계약서를 체계적으로 검토합니다. NDA 검토, 계약서 검토, 비밀유지계약서 분석, NDA clause review, NDA contract review가 필요할 때 이 스킬을 사용하세요.
---

# NDA Review Skill (NDA 검토 스킬)

## Purpose
NDA(비밀유지계약서)의 법적 리스크를 체계적으로 검토하고, 이슈를 severity 등급별로 분류하여 수정 협상점을 제공하는 법률 문서 검토 스킬입니다.

## Trigger Conditions
- NDA, 비밀유지계약서, NDAs, Non-Disclosure Agreement 관련 문서 검토 요청
- 계약서 검토, 법적 검토, 법적 리스크 평가 관련 요청
- 한국어/영어 NDA 문서 분석 요청

## Inputs
- **document**: 검토할 NDA 문서 (문서 파일 또는 텍스트)
- **transaction_type**: 거래 유형 (선택사항) — M&A, SaaS/API, 연구협력/PoC, 일반협력
- **party_role**: 당사자 위치 — Disclosing Party(공여자), Receiving Party(수령자), Mutual(양측)

## Review Framework

문서를 검토할 다음 23개 규칙을 체계적으로 적용합니다.

### Phase 1: Preliminary Assessment (Pre-Check)

1. **계약서 유형 식별** — 단독(N unilateral) / 상호(Mutual) / 혼합
2. **거래 유형 파악** — M&A 실사 / SaaS API 통합 / 연구협력(PoC) / 일반 협력
3. **당사자 위치 파악** — 우리가 주로 정보를 공개하는지 수령하는지
4. **데이터 유형 확인** — 일반비밀정보 / 개인정보 / 의료데이터 / 금융데이터

### Phase 2: Core NDA Review — 15 General Rules

다음 일반 NDA 검토 규칙을 적용합니다 (5개 High, 5개 Medium, 2개 Low 우선, 나머지 Medium/Low는 상황별):

#### 🔴 High Severity Rules (반드시 검토)

**R01: Confidential Information Definition Narrowing**
- `"모든 형태"`, `"일체의 정보"` 등 포괄적 표현 확인
- 서면 "Confidential" 표시 요건 존재 여부
- 구두 공개 시 30일 내 서면 확인 절차 존재 여부
- **권장**: "비밀로 표시되었거나 합리적으로 비밀로 인식될 수 있는 정보"로 한정

**R02: Four Standard Exceptions + Independently Developed**
- 4대 표준 예외: (1) 공개정보 (2) 기존 보유 (3) 제3자 적법 취득 (4) 법적 의무
- ⚠️ "독자개발(Independently Developed)" 예외 누락 check — **모든 문서에서 발견됨**
- **권장**: 5번째 예외로 "공개 전후 모두 독자적으로 개발한 정보" 추가

**R04: Liability Cap**
- 손배 상한(Liability Cap) 부재 check
- "직접·간접·결과적 손해 일체" 등 포괄적 표현 확인
- **권장**: 직접손해만 배상, 상한금액은 거래규모 또는 정액(10억원/USD 100K)

**R05: Non-Solicitation Period**
- 비권유 기간이 12개월 초과 check (문서1: 24개월 — 과도)
- 적용 대상이 "모든 임직원"이 아닌 "본 계약으로 알게 된 임직원"으로 한정되어야 함
- 공정거래법·노동법상 무효 가능성 확인

**R06: Governing Law**
- 준거법이 상대방 본사 소재지 법(델라웨어, 캘리포니아 등)인지 check
- **1순위**: 대한민국법 + 서울중앙지방법원
- **2순위**: 싱가포르 중재(SIAC)
- 상대방 소재지 법은 반드시 협상

**R10: No-Binding Clause**
- "본 계약은 거래 의무를 발생시키지 않는다" 조항 존재 check
- 누락 시 상대방이 거래 강제 또는 우선협상권 주장 가능

#### 🟡 Medium Severity Rules (상황에 따라 검토)

**R03: Confidentiality Period**
- 일반 비밀정보: 시장 표준 **3년** (범위 2-5년)
- 영업비밀: 무기한 별도 규정
- 5년 이상인 경우 3년으로 단축 협상 권장

**R07: Advisory/Employee Disclosure**
- "사전 서면 동의" 요건 확인 — 실무상 불리함
- **권장**: 동등 비밀유지 의무 부과 시 동의 없이 제공 가능하도록 완화

**R08: Purpose Narrowing**
- "any business discussion", "일체의 사업 협의" 등 광범위한 표현 check
- 구체적 목적 ("M&A 실사", "SaaS API 통합 검토")으로 한정 권장

**R11: Mutual NDA vs Unilateral Flow**
- "Mutual" 표기지만 실제 정보 비대칭 확인
- 우리가 더 많이 공개하면 단독 NDA 전환 검토

**R12: Residuals Clause**
- 잔존 지식(Residuals) 사용 가능 여부 확인
- 기술 협력 NDA에서는 "Residuals 허용"이 유리할 수 있음

**R13: Destruction Certificate**
- 비밀정보 반환/파기 의무 + **파기 확인서 제출** 의무
- 파기 후 30일 이내, 임원 서명, 서면 제출

#### 🟢 Low Severity Rules

**R09: Notice Clause**
- 통지 방법(서면/이메일), 도달 시점 기준 명시
- 이메일 시 "발신 5영업일 후 도달 의제" 규정 권장

**R14: Change of Control**
- No-assignment 조항과 별개로 Change of Control 규정
- M&A 시 자동 종료 또는 본인 동의 필요

**R15: Return/Deletion Deadline**
- 반환/파기 기한 "즉시" → "10-30영업일"로 구체화 권장

### Phase 3: Domain-Specific Review — 8 Data Privacy Rules

거래 유형에 따라 추가로 적용:

#### 의료/헬스케어 데이터 포함 시 (연구협력/PoC)

**DR01: Separate Data Processing Agreement**
- 환자 의료데이터 포함 시 별도 개인정보 처리 위·수탁 계약 필수 (PIP A Art. 26)
- 의료법 제19조 + 개인정보보호법 제23조 동시 적용

**DR02: Anonymization Standards**
- 익명화 방식·기준 명시 필요
- K-익명성, 차분 프라이시 등 기술적 기준 첨부

**DR03: Specific Security Requirements**
- "합리적인 수준"의 추상적 표현 대신 구체적 기준: ISMS-P, ISO 27701, 망분리, 암호화

**DR04: Cross-Border Data Transfer**
- 해외 클라우드 리전 시 PIPA Art. 28-8 준수
- 환자 동의 확보 또는 국내 리전 한정 의무

**DR06: IP Ownership Clarity**
- "공동 보유"는 상업화 장애 → 명확한 IP 분할 권장
- 데이터 제공자: 데이터 제공 권리만 / 기술 제공자: 모델 IP 단독 + 무료 비독점 라이선스

**DR07: Subcontractor Liability Chain**
- 재위탁 시 책임 승계 조항 필수
- 하수급인도 동등 이상의 비밀유지 의무

#### 모든 민감 데이터 포함 시 공통

**DR05: Breach Notification Timeline**
- "72시간 이내 서면 통지 + 1차 보고서" 명시
- 개인정보보호법 제34조 정보주체 통지 의무 포함

**DR08: Insurance Requirement**
- 데이터보호 책임보험 가입 의무 — 시장 표준

## Output Format

검토 결과는 다음 형식으로 출력합니다:

```
# NDA 검토 결과

## 📋 기본 정보
- **계약서 유형**: [단독/상호/혼합]
- **거래 유형**: [M&A/SaaS/연구협력/기타]
- **당사자 위치**: [공여자/수령자/양측]
- **데이터 유형**: [일반/개인정보/의료데이터/기타]

## 🔴 High Severity Issues ([X]건)

### [문제 조항 인용]
- **규칙**: [RXX 규칙명]
- **위험도**: High
- **문제점**: [구체적 문제 설명]
- **권장 수정안**: [구체적 수정 제안]

(중복 — 동일 형식)

## 🟡 Medium Severity Issues ([X]건)

### [문제 조항 인용]
- **규칙**: [RXX 규칙명]
- **위험도**: Medium
- **문제점**: [구체적 문제 설명]
- **권장 수정안**: [구체적 수정 제안]

(중복 — 동일 형식)

## 🟢 Low Severity Issues ([X]건)

### [문제 조항 인용]
- **규칙**: [RXX 규칙명]
- **위험도**: Low
- **문제점**: [구체적 문제 설명]
- **권장 수정안**: [구체적 수정 제안]

(중복 — 동일 형식)

## 📊 검토 요약

| Severity | Count |
|----------|-------|
| 🔴 High   | X     |
| 🟡 Medium | X     |
| 🟢 Low    | X     |
| **Total** | **X** |

## 💡 종합 의견

[전반적인 평가 및 협상 우선순위 제안 — 가장 중요한 수정항목부터 순서대로 요약]
```

## Execution Steps

1. **문서 수신**: NDA 문서 수신 → 텍스트 추출
2. **타입 분류**: 계약서 유형, 거래 유형, 당사자 위치, 데이터 유형 식별
3. **패스 1 — 기본 구조 검토**: R01-R15 일반 규칙 적용
4. **패스 2 — 도메인 규칙 검토**: DR01-DR08 (해당 시) 적용
5. **이슈 분류**: High/Medium/Low severity로 분류
6. **보고서 생성**: 지정된 출력 형식으로 검토 결과 생성
7. **협상 우선순위**: 종합 의견에 협상 우선순위 명시

## Best Practices

- **문구 인용 필수**: 각 이슈는 계약서에서 문제가 되는 **원문 구절을 정확히 인용**해야 함
- **규칙 매핑**: 각 이슈에 매핑된 규칙 번호(RXX)를 명시
- **수정안 제공**: 단순 지적이 아닌 **구체적 수정 제안 문구** 제공
- **교차 검증**: 여러 규칙이 중첩되는 경우 모두 명시 (예: "독자개발 예외 누락" + "책임상한 부재")
- **상호성 고려**: 상호 NDA인 경우 양측 관점 모두 검토
- **법령 참조**: 가능하면 관련 법령 조항(PIP A, 의료법 등) 명시

## Notes

- 이 스킬은 NDA(비밀유지계약서) 전문 검토에 특화됨
- M&A, SaaS/API 통합, 연구협력(PoC) 등 다양한 거래 유형 지원
- 의료데이터 등 민감정보 포함 시 별도 데이터 처리 계약 검토 필요
- 전체 23개 규칙 (일반 15개 + 도메인 8개) 기반
- High Severity 항목은 협상에서 최우선 처리 권장