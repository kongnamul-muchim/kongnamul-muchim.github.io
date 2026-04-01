---
title: ShotUp
type: unity
description: 공을 발사하여 골에 넣는 게임. 마우스 조준/파워 조절, 물리 기반 공 운동.
image: /images/shotup.png
technologies:
  - Unity
  - C#
  - Physics-based
  - 2D Physics
github: https://github.com/rlaehdduf/ShotUp
demo: https://rlaehdduf.github.io/ShotUp
featured: false
---

## 게임 개요

Unity 2D 로 개발한 물리 기반 공 슈팅 게임입니다. 공을 발사하여 골에 넣는 것이 목표입니다.

### 주요 기능

| 기능 | 설명 |
|------|------|
| **마우스 조준** | 커서 방향으로 발사 각도 조절 |
| **파워 조절** | 드래그 거리로 발사 세기 조정 |
| **물리 운동** | Rigidbody2D 기반 공 운동 |
| **충돌 판정** | 골/벽/장애물과 충돌 처리 |
| **이펙트** | 발사/충돌 효과 |

### 조작법

- **마우스 이동**: 발사 각도 조절
- **드래그 & 놓기**: 파워 조절 후 발사

### 폴더 구조

```
Assets/Scripts/
├── Config/      # 게임 설정
├── Core/        # 게임 매니저
├── Controllers/ # 공/발사 제어
├── Events/      # 이벤트 시스템
└── Services/    # 서비스 로케이터
```

### 기술 스택

- Unity 2D 물리 시스템 (Rigidbody2D, Collider2D)
- 물리 기반 운동 (중력, 반동, 마찰)
- 이벤트 기반 아키텍처
- 서비스 로케이터 패턴
