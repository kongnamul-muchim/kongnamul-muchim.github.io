---
title: ShotUp
type: unity
description: 마우스 조준/발사 전용 슈팅 게임. 타격 판정, 이펙트, 사운드 중심의 심플한 슈팅 게임.
image: /images/shotup.png
technologies:
  - Unity
  - C#
  - Top-down Shooter
  - 2D Physics
github: https://github.com/rlaehdduf/ShotUp
demo: https://rlaehdduf.github.io/ShotUp
featured: false
---

## 게임 개요

Unity 2D 로 개발한 마우스 전용 슈팅 게임입니다. 적이나 AI 는 없으며, 순수하게 마우스 조준과 발사, 타격감을 즐기는 게임입니다.

### 주요 기능

| 기능 | 설명 |
|------|------|
| **마우스 조준** | 커서 방향으로 캐릭터 회전 |
| **마우스 발사** | 클릭 시 총알 발사 |
| **충돌 판정** | 2D 물리 기반 탄착 검사 |
| **이펙트** | 총구 화염, 타격 효과 |
| **사운드** | 발사음, 충돌음 |

### 조작법

- **마우스 이동**: 캐릭터 방향 전환
- **왼쪽 클릭**: 총알 발사

### 폴더 구조

```
Assets/Scripts/
├── Config/      # 게임 설정
├── Core/        # 게임 매니저
├── Controllers/ # 플레이어/총알 제어
├── Events/      # 이벤트 시스템
└── Services/    # 서비스 로케이터
```

### 기술 스택

- Unity 2D 물리 시스템 (Rigidbody2D, Collider2D)
- 이벤트 기반 아키텍처
- 서비스 로케이터 패턴
- 객체 풀링 (총알 관리)
