---
title: Kirdia Simulator
type: docs
description: 웹소설 세계관 시뮬레이터. AI GM 시스템, 캐릭터 Role-play, 분기 스토리.
image: /images/defult.jpeg
technologies:
  - Markdown
  - Worldbuilding
  - AI Agent System
  - Event-driven Design
github: https://github.com/rlaehdduf/KirdiaSimulator
featured: false
devPeriod: 2026-03-30
---

## 프로젝트 개요

키르디아 웹소설 세계관을 기반으로 한 인터랙티브 스토리 시뮬레이터입니다.

### 주요 시스템

| 시스템 | 설명 |
|--------|------|
| **GM 시스템** | 이벤트 주도 + 사용자 주도 스토리 진행 |
| **캐릭터 시스템** | 카렌, 하리, 셀린, 가른 Role-play |
| **NPC 템플릿** | 마을 주민, 상인, 여행자 자동 생성 |
| **신들 템플릿** | 실바누스, 비탈리스, 파툼 신 Role-play |

### 아키텍처

```
docs/
├── characters/      # 메인/서브 캐릭터 템플릿
├── locations/       # 맵/지역 정보
├── simulation/      # 상태/이벤트 로그
├── story/           # 에피소드/플롯
├── systems/         # 아이템/매직 시스템
├── timeline/        # 연대기 (고대/현대)
└── world/           # 신들/종족/역사
```

### 특징

- **AI Agent 기반**: 상황별 자동 캐릭터 매칭
- **분기 스토리**: 선택에 따른 다른 결말
- **이벤트 로그**: 시간순 기록 관리
- **상태 추적**: 캐릭터 상태 변화 관리

### 캐릭터

- **메인**: 주인공, 카렌 (검사), 하리 (바람 정령), 셀린 (치료사), 가른 (드워프)
- **신들**: 실바누스, 비탈리스, 파툼, 마신