---
title: Mini Game Collection
type: web
description: Blazor WebAssembly 기반 미니게임 컬렉션. 6 개의 게임 (지뢰찾기, 스도쿠, 테트리스, 오목, 체스 등), SOLID 원칙, AI 포함.
image: /images/minigame-collection.png
technologies:
  - Blazor WebAssembly
  - .NET 8.0
  - C# 12
  - SOLID Architecture
  - Vercel
github: https://github.com/kongnamul-muchim/MiniGameCollection
demo: https://mini-game-collection-five.vercel.app/
featured: true
devPeriod: "2026-03-15 ~ 2026-04-02"
---

## 게임 개요

Blazor WebAssembly 기반으로 개발된 6 개의 미니게임 컬렉션입니다. SOLID 원칙과 DI 를 준수한 순수 C# Core 게임 로직으로 구성되었습니다.

### 포함 게임

| 게임 | 설명 | AI |
|------|-------------|----|
| Pattern Memory | 패턴 기억 게임 | ❌ |
| Minesweeper | 지뢰찾기 | ❌ |
| Sudoku | 스도쿠 퍼즐 | ❌ |
| Tetris | 테트리스 | ❌ |
| Gomoku | 오목 | ✅ Heuristic |
| Chess | 체스 | ✅ Minimax |

### 주요 기능

| 기능 | 설명 |
|------|------|
| **SOLID Architecture** | SRP, OCP, LSP, ISP, DIP 준수 |
| **DI Container** | 커스텀 의존성 주입 시스템 |
| **State Machine** | 게임 상태 관리 (Ready/Playing/Paused/GameOver) |
| **Event System** | EventBus 기반 이벤트 드라이븐 아키텍처 |
| **AI Systems** | 오목 (Heuristic), 체스 (Minimax + Alpha-Beta) |
| **Responsive Design** | HD / Mobile 대응 |

### 아키텍처

```
MiniGameCollection/
├── Core/                          # 공통 핵심 모듈
│   ├── Interfaces/                # IGame 등 공통 인터페이스
│   ├── State/                     # 상태 관리
│   ├── Events/                    # 이벤트 시스템
│   ├── Data/                      # 저장 시스템
│   ├── DI/                        # 의존성 주입
│   └── AI/                        # AI 모듈
│
├── Games/                         # 개별 게임 모듈
│   ├── PatternMemory/
│   ├── Minesweeper/
│   ├── Sudoku/
│   ├── Tetris/
│   ├── Gomoku/                    # AI 포함
│   └── Chess/                     # AI 포함
│
├── MiniGameCollection.Web/        # Blazor WebAssembly
│   ├── Pages/                     # 각 게임 페이지
│   └── Layout/                    # 레이아웃
│
└── Tests/                         # 단위 테스트
```

### 기술 스택

- **Blazor WebAssembly**: 클라이언트 측 WebAssembly 실행
- **.NET 8.0 / C# 12**: 최신 .NET 기능 활용
- **SOLID 원칙**: 유지보수 가능한 아키텍처
- **xUnit + Moq**: 단위 테스트
- **Vercel + GitHub Actions**: 자동 배포

### 실행 방법

```bash
cd MiniGameCollection.Web
dotnet run
```

브라우저에서 `http://localhost:5259` 접속.

### 테스트

```bash
dotnet test MiniGameCollection.sln
```
