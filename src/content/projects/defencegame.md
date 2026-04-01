---
title: DefenceGame
type: unity
description: 타워 디펜스 게임. 4 종 타워 (궁수/마법사/레이저/메이지타워) 배치, 레벨업, 특수 능력 해금 시스템.
image: /images/defencegame.png
technologies:
  - Unity
  - C#
  - Tower Defense
  - Special Ability System
github: https://github.com/rlaehdduf/DefenceGame
demo: https://rlaehdduf.github.io/DefenceGame
featured: true
devPeriod: 2026-03-09 ~ 2026-03-12
---

## 게임 개요

Unity 엔진으로 개발한 타워 디펜스 게임입니다. 적의 웨이브를 방어하며 타워를 성장시키는 전략 게임입니다.

### 주요 타워

| 타워 | 특수 능력 |
|------|----------|
| **Archer** | Lv.3 관통 1, Lv.5 관통 2, Lv.7 공격속도 20% |
| **Mage** | Lv.3 광역 1 칸, Lv.5 광역 2 칸, Lv.7 공격력 30% |
| **MageTower** | Lv.3 공격력 버프 10%, Lv.5 적 이동속도 30% 감소, Lv.7 범위 +1 |
| **Laser** | Lv.3 사거리 +1, Lv.5 사거리 +2, Lv.7 관통 |

### 주요 기능

- **타워 배치 및 드래그**: 직관적인 타워 배치 시스템
- **레벨업 시스템**: 타워 클릭으로 레벨업, 특수 능력 해금
- **특수 능력 매니저**: 타워별 고유 능력 관리 (SlowEffect, Buff 등)
- **가챠 시스템**: SpaceBar 로 타워 소환
- **점수 및 웨이브 시스템**: 진행 상황 저장

### 기술 특징

- `SpecialAbilityManager` 를 통한 능력 관리
- `TowerLevelManager` 의 레벨 데이터 영속화
- `Unit.cs` 의 이벤트 기반 능력 적용
- `Bullet.cs` 의 광역/관통 공격 처리
