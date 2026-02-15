---
name: biz-email-writer
description: "**비즈니스 이메일/공문 작성기**: 한국어 비즈니스 이메일의 격식 수준 자동 조절, 제목 구조화, 한영 이메일 작성을 지원합니다. 업무 요청, 회신, 감사, 미팅 요청, 공지, 거절 등 다양한 유형을 지원합니다.\n  - MANDATORY TRIGGERS: 이메일, 메일, email, 비즈니스 메일, 업무 메일, 공문, 회신, 답장, 메일 작성, 영문 이메일, 메일 쓰기"
---

# 비즈니스 이메일/공문 작성기

## Overview

한국 비즈니스 이메일의 핵심인 존대말 수준 조절, 격식 구조, CC/BCC 가이드를 내장한 이메일 생성 스킬입니다.

## 지원 이메일 유형

| 유형 | 설명 | 격식 수준 |
|------|------|-----------|
| 업무 요청 | 협조/자료 요청, 작업 의뢰 | 중~높음 |
| 회신/답변 | 문의 답변, 요청 회신 | 상대에 맞춤 |
| 감사 | 감사 인사, 협조 감사 | 중~높음 |
| 사과 | 실수/지연 사과 | 높음 |
| 미팅 요청 | 회의/미팅 일정 조율 | 중 |
| 공지/안내 | 부서/전사 공지 | 중 |
| 거절 | 정중한 거절 | 높음 |
| 영문 이메일 | 영어 비즈니스 이메일 | Formal/Semi-formal |

## 격식 수준 가이드

### Level 1: 최고 격식 (임원, 외부 고객사 대표)
```
제목: [요청] OO 관련 협조 요청의 건

OOO 대표님/전무님께

안녕하십니까, OOO 회사 OOO부 OOO입니다.
항상 귀사의 발전을 기원합니다.

다름이 아니오라, ...에 대해 협조를 요청드리고자 메일 드립니다.

...

상기 건에 대해 검토하여 주시면 감사하겠습니다.
바쁘신 중에도 시간 내어 주심에 감사드리며,
귀사의 무궁한 발전을 기원합니다.

OOO 회사 OOO부
OOO 드림
연락처: 000-0000-0000
```

### Level 2: 높은 격식 (타 부서 팀장급, 외부 담당자)
```
제목: [요청] OO 관련 자료 요청 건

OOO 팀장님께

안녕하세요, OO팀 OOO입니다.
다름이 아니라 OO 건으로 연락드립니다.

...

확인 부탁드리며, 궁금하신 사항은 편하게 연락 주세요.
감사합니다.

OO팀 OOO 드림
```

### Level 3: 보통 격식 (같은 부서 동료, 가까운 팀)
```
제목: OO 관련 확인 요청

OOO님 안녕하세요,
OO팀 OOO입니다.

OO 건 관련하여 확인 부탁드립니다.

...

확인 후 회신 부탁드립니다.
감사합니다.
```

## 이메일 구조 규칙

### 제목 작성법
```
[카테고리] 핵심 내용 - 부가 정보

카테고리 예시:
[요청] [회신] [공유] [안내] [긴급] [확인] [보고] [FYI]

좋은 예:
✅ [요청] 2026년 상반기 마케팅 예산안 검토 요청
✅ [회신] 신규 프로젝트 일정 관련 회신 드립니다
✅ [긴급] 클라이언트 미팅 일정 변경 안내

나쁜 예:
❌ 안녕하세요
❌ 문의드립니다
❌ 확인 부탁
```

### 본문 구조
```
1. 인사 + 자기소개 (1줄)
2. 메일 목적 (1~2줄)
3. 본문 내용 (핵심만 간결하게)
4. 요청/기대사항 (1~2줄)
5. 마무리 인사 (1줄)
6. 서명
```

### CC/BCC 가이드
- **CC**: 내용을 알아야 하는 관련자 (직속 상사, 프로젝트 멤버)
- **BCC**: 대량 발송 시 수신자 보호, 참조 사실을 알리지 않을 때
- **원칙**: 불필요한 CC는 최소화, 의사결정권자는 반드시 포함

## 영문 이메일 템플릿

### Formal Request
```
Subject: Request for [Specific Item/Action]

Dear Mr./Ms. [Name],

I hope this email finds you well.

I am writing to request [specific request].
[Provide context and details in 2-3 sentences.]

Would it be possible to [specific action] by [deadline]?

I appreciate your time and consideration.
Please do not hesitate to reach out if you need any further information.

Best regards,
[Your Name]
[Title], [Department]
[Company]
```

### Follow-up
```
Subject: Follow-up: [Original Subject]

Dear [Name],

I hope you are doing well.
I am following up on my previous email regarding [topic], sent on [date].

[Brief reminder of what was requested.]

Could you please provide an update at your earliest convenience?

Thank you for your attention to this matter.

Kind regards,
[Your Name]
```

## 출력 형식

기본적으로 텍스트로 출력하며, 사용자가 요청 시 .txt, .md, .docx 파일로 생성합니다.
클립보드에 바로 붙여넣을 수 있도록 깔끔한 텍스트 형태가 기본입니다.

## 워크플로우

```
사용자 요청 → 이메일 유형 파악 → 격식 수준 결정
→ 수신자/내용 확인 → 이메일 생성 → 출력
```
