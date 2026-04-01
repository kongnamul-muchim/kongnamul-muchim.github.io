---
title: Community Board
type: web
description: Next.js 커뮤니티 게시판. NextAuth 인증, Prisma ORM, CRUD, 반응형 UI.
image: /images/community-board.png
technologies:
  - Next.js 14
  - TypeScript
  - Tailwind CSS
  - Prisma
  - NextAuth
github: https://github.com/rlaehdduf/CommunityBoard
featured: false
devPeriod: 2026-03-30
---

## 프로젝트 개요

Next.js App Router 기반의 커뮤니티 게시판 시스템입니다.

### 주요 기능

| 기능 | 설명 |
|------|------|
| **인증 시스템** | NextAuth 기반 사용자 인증 |
| **게시글 CRUD** | 작성/조회/수정/삭제 |
| **사용자 인터랙션** | 댓글, 좋아요 |
| **반응형 UI** | Tailwind CSS 모바일 지원 |

### 폴더 구조

```
src/
├── app/             # Next.js App Router
├── components/      # 재사용 UI 컴포넌트
├── lib/             # 유틸리티
├── pages/           # 페이지 라우트
├── repositories/    # Prisma 데이터 접근
├── services/        # 비즈니스 로직
├── types/           # TypeScript 타입
└── validators/      # 입력 검증 (Zod)
```

### 기술 스택

- **Next.js 14 App Router**: 서버 컴포넌트
- **TypeScript**: 타입 안정성
- **Tailwind CSS**: 유틸리티 퍼스트 스타일링
- **Prisma ORM**: 타입세이프 DB 접근
- **NextAuth**: 인증 처리
- **Zod**: 스키마 검증

### 주의사항

서버/데이터베이스가 필요하여 GitHub Pages 에서는 동작하지 않습니다.