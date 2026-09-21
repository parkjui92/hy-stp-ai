# 정책연구를 위한 AI 에이전트 설계와 활용

한양대학교 과학기술정책연구소 STP 워크숍 · 2026년 9월 21일(월) 19:30~21:00 · 온라인 · 박주이

챗봇에 묻고 답하는 데서 나아가, **조사 · 집필 · 검증까지 스스로 하는 AI 팀을 내 정책연구 업무에 들이는 법**을 다룹니다. 강의는 개념과 시연 위주이고, 실습은 이 자료를 보며 각자 따라 할 수 있게 만들었습니다.

## 자료

| 자료 | 링크 | 비고 |
|---|---|---|
| 강의 슬라이드 (웹) | **https://parkjui92.github.io/hy-stp-ai/** | 68장 · 브라우저에서 바로 열림 |
| 강의 슬라이드 (PDF) | **[PDF 내려받기](https://github.com/parkjui92/hy-stp-ai/raw/main/STP_AI_Agent_Workshop_20260921.pdf)** | 68쪽 · 글꼴 내장(한글 안 깨짐) · 인쇄용 |
| API · MCP 도구 모음 | **https://parkjui92.github.io/hy-stp-ai/tools.html** | 과학기술정책 연구 · 논문에 쓸 만한 자료 창구와 MCP 서버 한 장 정리 |
| 지난 학기 강의자료 | **https://hanyang2026-1.pages.dev** — 접속코드 `AISTP26` | 더 깊이 알아보고 싶을 때 (LLM 원리 · 한계 · 실습 전 과정) |

**슬라이드 조작** — `←` `→` 이동 · `O` 목차 · `T` 밝게/어둡게 · `F` 전체화면 · 슬라이드 안의 어두운 상자는 클릭하면 프롬프트가 복사됩니다.

## 오늘의 흐름

1. **챗봇에서 에이전트로** — 무엇이 달라졌고, 정책연구는 왜 에이전트와 잘 맞는가
2. **왜 Claude Code인가** — 코딩 에이전트가 내 폴더에서 일한다는 것
3. **Demo** — 정책연구 5인 팀이 주제 한 줄에서 브리프까지 도는 모습
4. **구성요소** — 모델 · 스킬 · API와 MCP · 서브에이전트 · 오케스트레이터(팀장), 실제 md 파일로
5. **Hands-on** — 나만의 정책연구 에이전트 만들기 (각자 따라 하기)
6. **개인에서 팀으로** — 우리 팀 방법론을 플러그인으로

## 실습 시작하기 (각자 · 약 60분)

**준비물** — Claude 데스크톱 앱(claude.com/download) · 클로드 코드가 포함되는 유료 계정 · 빈 실습 폴더

슬라이드 5부의 순서대로 한 장에 하나씩 따라 하면 됩니다. 각 장에 **붙여 넣을 프롬프트 · 성공 판정 · 막혔을 때**가 적혀 있습니다.

| 단계 | 할 일 |
|---|---|
| ① | CLAUDE.md — 연구 원칙 다섯 줄 |
| ② | 정책사례 조사 스킬 만들기 |
| ③ ④ | 자료 창구(API) 호출 · 법령 MCP 연결 |
| ⑤ | Researcher · Critic 서브에이전트 만들기 |
| ⑥ ⑦ | 과제 맡기기 → 계획 승인 → 검수 → 수정 지시 |
| ⑧ | 브리프 · 한글 문서로 변환 → 폴더에서 확인 |
| ⑨ | 정책연구 킷(플러그인) 설치 → 킥오프 |

**정책연구 킷 설치** — 앱의 설정 → [앱 및 확장 프로그램 열기] → 플러그인 → 마켓플레이스 추가에 `parkjui92/policy-research-kit` → 목록에서 연결(설치) → 재시작. 명령으로 하려면 입력창에 아래 두 줄을 차례로 넣습니다.

```
/plugin marketplace add parkjui92/policy-research-kit
/plugin install policy-research-kit@policy-research-kit
```

**스킬 · 도구 가져오기** — 깃허브 주소를 붙여 넣고 말로 시키면 됩니다. 예: `이 저장소를 클론해서 설치해줘 — https://github.com/parkjui92/deident`

**막혔을 때** — 오류 메시지를 그대로 붙여 넣고 "왜 안 되는지 설명하고 고쳐줘". 그래도 안 되면 화면 캡처와 함께 메일로 보내 주세요.

## 오늘 쓴 것들 — 전부 공개 (MIT)

| 저장소 | 무엇 |
|---|---|
| [policy-research-kit](https://github.com/parkjui92/policy-research-kit) | 정책연구 5인 에이전트 팀 플러그인 |
| [rnd-proposal-kit](https://github.com/parkjui92/rnd-proposal-kit) · [socsci-paper-kit](https://github.com/parkjui92/socsci-paper-kit) | 정부 R&D 제안서 팀 · 사회과학 논문 팀 |
| [paper-proofread](https://github.com/parkjui92/paper-proofread) | 한국어 학술 원고 교정 · 교열 스킬 |
| [doc-figure](https://github.com/parkjui92/doc-figure) | 한글이 깨지지 않는 삽도 생성 |
| [deident](https://github.com/parkjui92/deident) | 문서 민감정보 비식별 (전 과정 로컬) |
| [prism-db](https://github.com/parkjui92/prism-db) | 정부 발주 정책연구용역 7만여 건 로컬 DB |
| [korea-cabinet-stp](https://github.com/parkjui92/korea-cabinet-stp) | 국무회의 자료 아카이브 |
| [lecture-deck-kit](https://github.com/parkjui92/lecture-deck-kit) | 이 강의자료를 만들고 브라우저에서 고친 도구 |

외부 도구 — [kordoc](https://github.com/chrisryugj/kordoc)(한글 · PDF · 오피스 문서 읽기 MCP) · [korean-law-mcp](https://github.com/chrisryugj/korean-law-mcp)(법제처 법령 MCP, 무료 인증키 필요)

## 주의

- 프롬프트와 첨부 자료는 외부 서버로 전송됩니다. 미공개 과제 · 평가 원자료 · 개인정보 원본 · 인증키는 넣지 않고, 실습은 공개 자료와 본인이 쓴 문서로 합니다.
- 인증키는 `.env` 파일에 두고 문서 · 채팅에 적지 않습니다.
- 기관 도입은 개인 학습 → 팀 시험 운영 → 보안 심의 → 확산의 순서로.

## 문의

박주이 · 한양대학교 과학기술정책연구소 연구교수 · parkjui92@gmail.com · [github.com/parkjui92](https://github.com/parkjui92)

이 자료의 슬라이드와 문서는 자유롭게 열람 · 인용할 수 있습니다(출처 표기). 인용된 외부 자료의 저작권은 각 출처에 있습니다.
