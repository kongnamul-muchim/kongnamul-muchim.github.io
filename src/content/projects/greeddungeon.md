---
title: GreedDungeon
type: unity
description: 2D 턴제 로그라이트 던전 크롤러. 행동 게이지 시스템, 장비/스킬/버프, 전투 비주얼 효과.
image: /images/greeddungeon.png
technologies:
  - Unity
  - C#
  - Roguelite
  - Turn-based Combat
github: https://github.com/rlaehdduf/GreedDungeon
demo: https://rlaehdduf.github.io/GreedDungeon
featured: true
devPeriod: 2026-03-19 ~ 2026-03-27
---

## 게임 개요

Unity 2D 로 개발한 턴제 로그라이트 던전 크롤러 RPG 입니다. 행동 게이지 기반 전투와 풍부한 비주얼 효과를 특징으로 합니다.

### 주요 시스템

| 시스템 | 설명 |
|--------|------|
| **행동 게이지** | Speed 스탯에 따라 게이지 증가, 1000 도달 시 행동 |
| **전투 시스템** | 속성/상태이상/스킬/버프 통합 관리 |
| **장비 시스템** | 장비 착용/해제, 스탯 캐시 무효화 |
| **던전 진행** | EncounterSystem, 보물방, 게임오버 처리 |

### 전투 비주얼

- 턴 전환 딜레이 및 공격 모션
- 데미지 텍스트 UI (플레이어 빨간색)
- 디버프 비네트 효과
- 스킬 이펙트 및 배경 스크롤

### 밸런스 데이터

| 분류 | 내용 |
|------|------|
| **플레이어** | HP 70, MP 40, ATK 8, DEF 3 |
| **장비** | HP/DEF 50% 감소 적용 |
| **몬스터** | HP/ATK/DEF 20% 상향 |
| **희귀도** | Legendary 2.0x 배율 |

### 기술 특징

- GameDevToolkit DI 시스템 사용
- CSV 데이터 워크플로우 (Excel → CSV → ScriptableObject)
- SOLID 원칙 준수 (클래스 300 행 제한)
- 전투 시뮬레이터로 밸런스 검증