---
title: Pathfinder
type: unity
description: 메트로바니아 2D 플랫포머. 능력 해금으로 백트래킹, 즉사 함정, DI Container.
image: /images/pathfinder.png
technologies:
  - Unity
  - C#
  - Metroidvania
  - Custom DI Container
github: https://github.com/rlaehdduf/Pathfinder
demo: https://rlaehdduf.github.io/Pathfinder
featured: false
devPeriod: 2026-03-16 ~ 2026-03-19
---

## 프로젝트 개요

메트로바니아 스타일의 2D 플랫포머 게임입니다. 능력을 해금하며 맵을 탐색하는 백트래킹 요소가 핵심입니다.

### 게임 메커니즘

| 요소 | 설명 |
|------|------|
| **즉사 시스템** | 함정/적 접촉 시 즉시 사망 (HP 없음) |
| **능력 해금** | 4 개 맵의 능력 획득으로 추가 |
| **백트래킹** | 이전 맵으로 돌아가 새 구역 탐색 |
| **포탈 시스템** | 맵 간 이동 |

### 획득 능력

| 능력 | 위치 | 효과 |
|------|------|------|
| **DoubleJump** | Map 2 | 2 단 점프로 높은 곳 접근 |
| **Dash** | Map 3 | 방향키 더블탭 빠른 이동 |

### 맵 구성

```
Map 1 (튜토리얼) → Map 2 (DoubleJump) → Map 1 (새 구역)
                                          ↓
                                    Map 3 (Dash) → Map 4 (클리어)
```

### 함정 종류

- **SpikeTrap**: 바닥/벽 가시 (즉사)
- **MovingPlatform**: X 축 왕복 이동 플랫폼

### 기술 특징

- Custom DI Container (Singleton, Transient, Constructor/Field Injection)
- SOLID 원칙 엄격 적용 (클래스 300 행/메서드 10 개 제한)
- 인터페이스 기반 설게 (switch/if-else 금지)
- Nine Pines Penguin 애니메이션 에셋