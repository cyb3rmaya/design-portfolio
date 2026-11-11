# 포트폴리오

기획부터 배포까지 혼자 맡아, AI(Claude Code·Codex)를 개발 파트너로 써서 만든 결과물입니다.
**AI가 코드를 쓰고, 저는 기획·설계·판단·검수를 맡습니다.** 명세 → 작업 계획 → 구현 → AI 다관점 검토 → 수정 순서로 반복합니다.

## 고용노동부 고용24 AI 해커톤 출품작

### 바로시작 — 국민취업지원제도 안내 시제품 (본선 진출 · 2차 심사 진행 중)
**https://cyb3rmaya.github.io/barosijak-demo/**

메뉴가 많아 막막한 구직자에게 나이 질문 하나로 시작해, 해야 할 일을 날짜별로 정리해 주는 안내 시제품입니다.

- **핵심 로직**: 대화로 상황 파악 → 수급자격 통지일 등 날짜로 이번 주 할 일·다가오는 기한·놓치면 사라지는 것 분류 → 큰 절차를 하루 한 가지 미션으로 쪼갬
- **신뢰 설계**: 금액·기한은 AI가 만들지 않고 사람이 원문과 대조한 고정표만 사용 · 모든 안내에 업무매뉴얼 쪽수 근거 표기 · 자격 판정이 아님을 명시(최종 판단은 고용센터)

| 시작 대화 | 내 날짜 일정 | 오늘의 미션 |
|---|---|---|
| <a href="https://cyb3rmaya.github.io/barosijak-demo/"><img src="shots/projects/barosijak/1-chat.png" width="220"></a> | <img src="shots/projects/barosijak/2-schedule.png" width="220"> | <img src="shots/projects/barosijak/3-mission.png" width="220"> |

---

## 대표 프로젝트

| | 서비스 | 링크 |
|---|---|---|
| 1 | **WorkSign** · 모바일 전자근로계약서 | https://worksign.co.kr |
| 2 | **청소년 주식 학습 모의투자 앱** | https://stockup.kratos1.cloud |
| 3 | **GTO KRATOS** · 포커 전략 학습·게임 웹앱 | https://kratos1.cloud/gtokrato |
| 4 | **무인 만화방 홈페이지** · 의뢰 제작 | https://eonyang-comic.pages.dev |
| 5 | **ZEUS(제우스)** · macOS 한국어 AI 음성 비서 | 개인 프로젝트 (데스크톱 앱) |

---

### 1. WorkSign — 모바일 전자근로계약서
**https://worksign.co.kr**

노무법인 의뢰로 만든 실서비스. 사업주가 한글·워드·PDF 계약서를 올려 입력칸을 지정하고 보내면, 근로자가 휴대폰으로 채우고 서명합니다. 서명 문서는 위·변조를 막도록 봉인됩니다. 랜딩은 4단계 흐름·기능 카드·근로자 휴대폰 시연 중심으로 개편했습니다.

- **핵심 로직**: 문서 변환 → 입력칸 지정(텍스트·날짜·금액·서명·도장) → 일괄 발송 → 모바일 서명 → 봉인·보관 · 발송 실적·비회신 추적
- **만든 방법**: Next.js 15 · Prisma · Postgres(Supabase) · 문서 처리 워커 · Docker · AWS 서울 서버
- **AI 활용**: 고객 지시를 AI 작업 지침서로 정리해 변경 요청마다 근거를 남기고, AI가 구현한 결과를 자동 검사로 검증 — 테스트 329개 · 접근성(WCAG 2.2) 위반 0건 · Lighthouse 100점

<a href="https://worksign.co.kr"><img src="shots/projects/worksign/landing.png" width="720" alt="WorkSign"></a>

| 4단계 발송 흐름 | 기능 한눈에 보기 |
|---|---|
| <img src="shots/projects/worksign/landing-flow.png" width="480"> | <img src="shots/projects/worksign/landing-features.png" width="480"> |
| **근로자 휴대폰 서명 안내 (앱 설치 없음)** | **입력칸 지정 에디터** |
| <img src="shots/projects/worksign/landing-worker.png" width="480"> | <img src="shots/projects/worksign/editor.png" width="480"> |
| **발송 마법사** | **발송 실적·비회신 추적** |
| <img src="shots/projects/worksign/send.png" width="480"> | <img src="shots/projects/worksign/reports.png" width="480"> |
| **모바일 랜딩** | **근로자 모바일 서명** |
| <img src="shots/projects/worksign/landing-m.png" width="220"> | <img src="shots/projects/worksign/sign.png" width="220"> |

<sub>화면 캡처는 가상 회사·가상 인물 데이터입니다.</sub>

### 2. 청소년 주식 학습 모의투자 앱
**https://stockup.kratos1.cloud**

만 15세 이상 청소년이 가상 자금으로 투자를 배우는 앱. 실제 시세로 연습하고, 레슨·퀴즈로 개념을 익힙니다.

- **핵심 로직**: 토스증권 실시세(국내·미국) → 종목 상세(차트·호가·수급) → 모의 주문(지정가·시장가, 수수료·체결 예상) → 레벨별 학습 51장
- **만든 방법**: Next.js 16 · 토스증권 Open API · 금융감독원 DART 재무 데이터 · Supabase · AWS 서울 서버
- **AI 활용**: 화면·버튼 단위로 AI가 여러 관점(학습자·보호자·규제)에서 비판 검토 → 확정된 문제만 고치는 루프로 품질 관리 · 학습 영상을 AI 음성과 Remotion으로 자동 생성하는 파이프라인 구축

| 홈 | 실시세 | 종목 상세 | 모의 주문 | 학습 |
|---|---|---|---|---|
| <a href="https://stockup.kratos1.cloud"><img src="shots/projects/stockup/home.png" width="150"></a> | <img src="shots/projects/stockup/market.png" width="150"> | <img src="shots/projects/stockup/detail.png" width="150"> | <img src="shots/projects/stockup/order.png" width="150"> | <img src="shots/projects/stockup/learn.png" width="150"> |

### 3. GTO KRATOS — 포커 전략 학습·코칭 웹앱
**https://kratos1.cloud/gtokrato**

포커 전략(GTO)을 레벨에 맞춰 배우고, 선택마다 채점받으며 실전처럼 연습하는 웹앱입니다.

- **강점**: 첫 방문 국가·언어 선택(시간대 자동 감지) · 수준을 고르면 첫 주 미션 3개와 단계별 커리큘럼(진단 → EV 입문 → GTO 입문 → 포스트플랍 → 승급 시험) 제안 · 선택마다 GTO 기준으로 채점하는 연습·코칭
- **만든 방법**: 외부 라이브러리 없는 Node 서버 · 게임·확률 엔진 · SQLite + Supabase 이중 저장
- **AI 활용**: 게임 규칙·확률 엔진과 학습 흐름을 AI와 함께 설계·구현하고, 버전마다 AI 검토로 규칙 오류를 잡아냄

<a href="https://kratos1.cloud/gtokrato"><img src="shots/projects/gtokrato/curriculum.png" width="720" alt="커리큘럼 제안"></a>

| 첫 방문 국가·지역 선택 (시간대 자동 감지) | 언어 선택 (14개 언어) |
|---|---|
| <img src="shots/projects/gtokrato/region.png" width="480"> | <img src="shots/projects/gtokrato/language.png" width="480"> |
| **학습 허브** | **연습 설정 (GTO 문제 훈련)** |
| <img src="shots/projects/gtokrato/study.png" width="480"> | <img src="shots/projects/gtokrato/practice.png" width="480"> |

### 4. 무인 만화방 홈페이지 — 의뢰 제작
**https://eonyang-comic.pages.dev/**

무인 만화방 의뢰로 만든 홈페이지. 도서 검색·이용 요금·오시는 길을 한 화면에 담았습니다.

<a href="https://eonyang-comic.pages.dev/"><img src="shots/designs/eonyang/home.png" width="49%" alt="무인 만화방"></a>

### 5. ZEUS(제우스) — macOS 한국어 AI 음성 비서
**개인 프로젝트 · macOS 데스크톱 앱**

호출어나 박수로 부르면 듣고, Claude로 생각해 한국어로 대답하는 맥 AI 비서 '제우스'. 잠든 상태에서는 바탕화면 아이콘으로 깨우고, 깨어나면 날씨·메일을 정리한 음성 브리핑으로 하루를 시작합니다. 날씨·유튜브·음악·연락처·전화·메일·캘린더를 말로 다루고, 되돌리기 어려운 작업은 "실행 확인"이라고 말해야만 실행합니다.

- **핵심 로직**: 호출어 감지 → 받아쓰기(맥 내장, 온디바이스 한국어) → Claude 스트리밍 응답 → 문장 단위로 끊어 음성 합성(다음 문장을 미리 합성) → 아이언맨 MK42 스타일 관제 화면 · "화면 작게"로 오브+자막 패널로 접힘
- **만든 방법**: Electron + TypeScript · Swift 네이티브 헬퍼(macOS 26 SpeechTranscriber) · openWakeWord ONNX 호출어 모델 · Claude Agent SDK + MCP 도구 서버 5개(날씨·미디어·연락·화면·캘린더) · ElevenLabs·Typecast 제우스 음성(실패 시 맥 내장 Yuna) · LaunchAgent 상시 실행
- **안전 설계**: 두뇌는 MCP 도구만 쓸 수 있고 셸·파일 도구는 차단 · 전화·메일·일정 추가는 30초 안에 "실행 확인"을 말해야 통과 · 삭제류 캘린더 도구는 두뇌에 아예 노출하지 않음 · API 키는 키체인 암호화 저장
- **AI 활용**: 설계 명세를 AI가 13개 관점으로 비판 검토해 112건을 반영한 뒤 구현 · 상태 전이표·음성 명령 매칭·호출어 파이프라인을 테스트 104개로 고정

<img src="shots/projects/jarvis/hud.png" width="720" alt="ZEUS 관제 화면">

| 시스템 상태 (마이크·호출어·두뇌·목소리) | 연결 현황 (MCP 도구 7종) |
|---|---|
| <img src="shots/projects/jarvis/status.png" width="480"> | <img src="shots/projects/jarvis/links.png" width="480"> |
| **환경 설정 (날씨·위치·메일 브리핑)** | **실시간 위치 (GPS · OpenStreetMap)** |
| <img src="shots/projects/jarvis/settings.png" width="480"> | <img src="shots/projects/jarvis/geo.png" width="480"> |

<sub>위치·메일·뉴스 등 개인 정보는 블러 처리했습니다.</sub>


<sub>캡처는 실제 HUD 렌더러 코드에 시연용 상태값을 넣어 찍었습니다. 앱과 연결되는 부분만 대체했습니다.</sub>

<details>
<summary><b>주요 코드</b></summary>

<sub>핵심 줄만 남겨 줄여 옮겼습니다.</sub>

**쓰기 게이트** — 두뇌가 도구를 부를 때마다 거치는 관문. MCP 도구가 아니면 거부하고, 쓰기 도구는 음성 확인을 받아야 통과합니다.

```ts
export function makeCanUseTool(h: GateHooks): CanUseTool {
  return async (toolName, input, { signal }) => {
    if (!isMcpTool(toolName)) return { behavior: 'deny', message: '내장 도구는 쓸 수 없습니다' }
    if (!WRITE_TOOLS.has(toolName)) return { behavior: 'allow', updatedInput: input }
    const ok = await h.askConfirm(toolName, input, signal) // 30초 안에 "실행 확인"
    return ok ? { behavior: 'allow', updatedInput: { ...input, confirmation: `hud:${Date.now()}` } }
              : { behavior: 'deny', message: '보스가 실행을 확인하지 않았습니다. 취소합니다.' }
  }
}
```

**스트리밍 → 문장 단위 음성** — 대답이 다 끝나길 기다리지 않고, 문장이 완성되는 즉시 말하기 시작합니다.

```ts
for await (const msg of q) {
  if (msg.type === 'stream_event' && msg.event.delta?.type === 'text_delta') {
    for (const s of stream.push(msg.event.delta.text)) this.cb.onSentence(s) // 완성된 문장만
  }
  if (msg.type === 'result') for (const s of stream.flush()) this.cb.onSentence(s)
}

// 입: 지금 문장을 재생하는 동안 다음 문장을 미리 합성한다
while (this.queue.length || next) {
  const { s, mp3 } = await (next ?? take())
  next = this.queue.length ? take() : null
  mp3 ? await this.play('afplay', [mp3]) : await this.play('say', ['-v', 'Yuna', s])
}
```

**호출어 감지** — 80ms 조각마다 앞 조각의 꼬리 30ms를 붙여 멜 스펙트로그램을 계산합니다. 이 꼬리가 빠져 있을 때는 시간축이 압축돼 점수가 0이었고, 붙인 뒤 합성 음성 기준 0.998이 나왔습니다.

```ts
async pushPcm16k(frame: Float32Array): Promise<number> {
  const scaled = new Float32Array(480 + frame.length)   // 직전 꼬리 480샘플 + 이번 1280샘플
  scaled.set(this.tail.map((v) => v * 32768)); scaled.set(frame.map((v) => v * 32768), 480)
  this.tail = frame.slice(frame.length - 480)
  // mel(마지막 8프레임) → 76프레임 창마다 임베딩 → 최근 임베딩 16개 → hey_jarvis 점수
  ...
}
```

**음성 명령은 완전일치만** — "그만", "실행 확인" 같은 명령은 문장 안에 섞여 있어도 오작동하지 않도록 정규화 후 완전일치로만 받습니다.

```ts
export function matchLocalIntent(utterance: string, enabled: readonly LocalIntent[]) {
  const n = normalizeUtterance(utterance) // 공백·문장부호 제거
  for (const intent of enabled) if (LOCAL_INTENTS[intent].some((p) => normalizeUtterance(p) === n)) return intent
  return null
}
```

</details>

---

## 그 밖의 프로그램

### 넷플릭스 영어 단어장 (크롬 확장)
넷플릭스 영어 자막에서 모르는 단어를 눌러 저장하고, 토익·비즈니스 빈출 등급까지 함께 보여 주는 단어장입니다.

- **기능**: 자막 단어 클릭·드래그로 뜻·발음 저장 · 토익/비즈니스 태그와 ★ 중요도 · SM-2 간격 반복 복습 · Anki 내보내기 · 모바일 이어 복습
- **만든 방법**: Chrome 확장(Manifest V3) · 바닐라 JS · Supabase 동기화

<img src="shots/projects/netflix-vocab/vocab.png" width="480" alt="단어장 화면">

---

## 웹사이트 디자인 시안

링크나 이미지를 누르면 실제 사이트가 열립니다.

> 고객사의 공개 동의를 받지 못한 시안은 캡처의 로고·회사명을 블러 처리했고, 이름도 일반 명칭으로 바꿨습니다. 모든 시안은 직접 작성한 소스코드로 만들어 제 도메인(kratos1.cloud 등)에 올린 것입니다.

### 크라토스 (외주 개발사 홈페이지)
외주 개발사 소개·견적 상담 사이트. 체험형 데모 10종을 함께 운영.

<a href="https://kratos1.cloud/"><img src="shots/designs/kratos/home.png" width="49%" alt="홈"></a>
<a href="https://kratos1.cloud/demos"><img src="shots/designs/kratos/demos.png" width="49%" alt="데모 모음"></a>

- 홈: https://kratos1.cloud/
- 데모 모음: https://kratos1.cloud/demos

### 토너먼트 홀덤 트레이너
랜덤 스팟마다 한 수를 고르면 GTO·ICM 기준으로 채점·해설하고, 봇과 실제 핸드를 치며 실시간 코치를 받는 학습 앱.

- 트레이너: https://holdem-trainer-8hzx.onrender.com/

<a href="https://holdem-trainer-8hzx.onrender.com/"><img src="shots/designs/holdem/trainer.png" width="32%" alt="스팟 채점"></a>
<a href="https://holdem-trainer-8hzx.onrender.com/"><img src="shots/designs/holdem/bot.png" width="32%" alt="봇 대전·실시간 코치"></a>
<a href="https://holdem-trainer-8hzx.onrender.com/"><img src="shots/designs/holdem/home.png" width="32%" alt="학습 홈"></a>

### 에스컬레이터 제조사 홈페이지 (시안 3종)
같은 회사를 세 가지 방향(기본·현대형·백과사전형)으로 제안한 시안.

<a href="https://kratos1.cloud/escalator/"><img src="shots/designs/k-escalator/base.png" width="32%" alt="기본형"></a>
<a href="https://kratos1.cloud/p/ke-hyundai/"><img src="shots/designs/k-escalator/hyundai.png" width="32%" alt="현대형"></a>
<a href="https://kratos1.cloud/p/ke-hpedia/"><img src="shots/designs/k-escalator/hpedia.png" width="32%" alt="백과사전형"></a>

- 기본형: https://kratos1.cloud/escalator/
- 현대형: https://kratos1.cloud/p/ke-hyundai/
- 백과사전형: https://kratos1.cloud/p/ke-hpedia/

### 인사·조직 컨설팅사 홈페이지 (시안 2종)
컨설팅 회사의 신뢰감을 살린 두 가지 레이아웃 시안.

<a href="https://kratos1.cloud/p/epic/"><img src="shots/designs/epic/a.png" width="49%" alt="1안"></a>
<a href="https://kratos1.cloud/p/epic-jbfg-1009/"><img src="shots/designs/epic/b.png" width="49%" alt="2안"></a>

- 1안: https://kratos1.cloud/p/epic/
- 2안: https://kratos1.cloud/p/epic-jbfg-1009/

### 노무법인 홈페이지 · 자가진단 · 관리자
노무법인 홈페이지 리뉴얼. 관리자 대시보드와 AI 노무 자가진단까지 한 세트로 설계.

- 홈페이지: https://kratos1.cloud/p/klabor-7f3c9a/
- AI 노무 자가진단 (8문항으로 위험 항목 진단 → 상담 연결): https://kratos1.cloud/p/klabor-7f3c9a/ai-check/
- 관리자 대시보드 (신청·상담·유입 통계 + AI 분석 챗봇, 입력 없이 로그인): https://kratos1.cloud/p/klabor-7f3c9a/admin/

<a href="https://kratos1.cloud/p/klabor-7f3c9a/"><img src="shots/designs/k-labor/home.png" width="32%" alt="홈페이지"></a>
<a href="https://kratos1.cloud/p/klabor-7f3c9a/ai-check/"><img src="shots/designs/k-labor/ai-check.png" width="32%" alt="AI 노무 자가진단"></a>
<a href="https://kratos1.cloud/p/klabor-7f3c9a/admin/"><img src="shots/designs/k-labor/admin.png" width="32%" alt="관리자 대시보드"></a>

### 웰니스 쇼핑몰
식품·바디케어 웰니스 쇼핑몰.

<a href="https://cyb3rmaya.github.io/egattoc-wellness/"><img src="shots/designs/egattoc/home.png" width="49%" alt="웰니스 쇼핑몰"></a>

- 쇼핑몰: https://cyb3rmaya.github.io/egattoc-wellness/
