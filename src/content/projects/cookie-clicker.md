---
title: Cookie Clicker
type: server
description: Node.js + Express + SQLite 쿠키클리커. 세션 관리, 인메모리 DB, 자동 생산 업그레이드.
image: /images/cookie-clicker.png
technologies:
  - Node.js
  - Express.js
  - SQLite (sql.js)
  - express-session
github: https://github.com/rlaehdduf/CookieClicker
featured: false
devPeriod: 2026-03-30 ~ 2026-03-31
---

## 게임 개요

Node.js 기반 서버에서 실행되는 쿠키클리커 인크리멘털 게임입니다.

### 주요 기능

| 기능 | 설명 |
|------|------|
| **쿠키 클릭** | 클릭당 쿠키 획득 |
| **업그레이드** | 자동 생산 건물 구매 |
| **스킬 트리** | 능력 강화 시스템 |
| **세션 저장** | SQLite 기반 진행 상황 저장 |

### 아키텍처

```
src/
├── config/          # 설정 관리
├── containers/      # DI 컨테이너
├── models/          # 데이터 모델
├── repositories/    # SQLite 데이터 접근
├── routes/          # API 엔드포인트
├── services/        # 비즈니스 로직
├── validators/      # 입력 검증
└── interfaces/      # 인터페이스 정의
```

### 기술 스택

- **Express.js**: 웹 서버 및 라우팅
- **express-session**: 세션 관리
- **sql.js**: 인메모리 SQLite
- **connect-sqlite3**: 세션 스토어
- **cookie-parser**: 쿠키 처리

### 실행 방법

```bash
npm install
npm start  # http://localhost:3000
```