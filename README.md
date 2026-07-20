# Community Board 👩🏻‍💻

> [요즘 바이브 코딩 커서 AI 30가지 프로그램 만들기](https://product.kyobobook.co.kr/detail/S000217462860) 나만의 커뮤니티 게시판 만들기 실습

Next.js(App Router) + Tailwind CSS + Supabase로 만든 Reddit 스타일 커뮤니티 게시판입니다.  
이메일/비밀번호 인증과 글·댓글·반응·검색을 지원합니다.

---

## 주요 기능

- 회원가입 · 로그인 · 로그아웃 · 내 정보(닉네임·소개)
- 게시글 작성 · 수정 · 삭제 · 검색
- 게시글·댓글 이미지 첨부
- 좋아요 / 싫어요
- 댓글 · 답글 (1단계)

---

## 폴더 구조

```
community-board/
├── public/                 # 정적 자산
├── src/
│   ├── app/                # App Router 페이지
│   │   ├── page.tsx        # 홈 (게시글 목록)
│   │   ├── login/          # 로그인
│   │   ├── signup/         # 회원가입
│   │   ├── me/             # 내 프로필
│   │   └── posts/          # 게시글 상세 · 작성 · 수정
│   ├── components/         # Header · 사이드바 · PostCard · 댓글 · 반응 버튼
│   ├── actions/            # auth · posts · comments · reactions · profile
│   ├── lib/
│   │   ├── supabase/       # browser / server / middleware 클라이언트
│   │   ├── posts.ts
│   │   ├── profile.ts
│   │   └── types.ts
│   └── middleware.ts       # 세션 갱신
├── .env.example
├── next.config.ts
└── package.json
```

---

## 실행 방법

```bash
npm install

# .env.local 생성 (.env.example 참고)
# NEXT_PUBLIC_SUPABASE_URL=...
# NEXT_PUBLIC_SUPABASE_ANON_KEY=...

npm run dev
# http://localhost:3000 접속
```

---

## 참고

- **실습 기록** · [CursorAI-study](https://github.com/absolutelyfullycapable/CursorAI-study)
- **저자** · 박현규
- **출판** · 골든래빗(주), 2025
