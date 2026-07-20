# community-board

Next.js + Tailwind CSS + Supabase로 만든 커뮤니티 게시판입니다.  
Vercel 배포를 전제로 한 단독 저장소입니다.

## 주요 기능

- 회원가입 / 로그인 / 로그아웃 (이메일·비밀번호)
- 내 정보(닉네임·소개) 수정
- 게시글 작성 · 수정 · 삭제 · 검색
- 게시글·댓글 이미지 첨부 (최대 5MB)
- 좋아요 / 싫어요
- 댓글 · 답글 (1단계)

## 기술 스택

- **Frontend** · Next.js (App Router) · Tailwind CSS · Pretendard
- **Backend** · Supabase Auth · Postgres · Storage · RLS
- **배포** · Vercel 권장

## 로컬 실행

```bash
npm install
cp .env.example .env.local
# .env.local에 Supabase URL / anon key 입력
npm run dev
```

http://localhost:3000 에서 확인합니다.

## 환경 변수

| 변수 | 설명 |
|------|------|
| `NEXT_PUBLIC_SUPABASE_URL` | Supabase Project URL |
| `NEXT_PUBLIC_SUPABASE_ANON_KEY` | Supabase anon / publishable key |

`.env.local`은 커밋하지 마세요. Vercel에서는 Project Settings → Environment Variables에 동일 키를 등록합니다.

## Supabase 준비

프로젝트가 이미 있다면 아래만 확인하면 됩니다.

1. **Authentication → Providers → Email**  
   개발 중에는 Confirm email을 끄면 가입 직후 로그인할 수 있습니다.
2. **테이블** · `profiles` · `posts` · `comments` · `post_reactions`
3. **Storage** · public bucket `post-images` (경로 `{userId}/...`)
4. **RLS** · 공개 읽기, 작성·수정·삭제는 본인만

## Vercel 배포

1. 이 저장소를 [Vercel](https://vercel.com)에 Import
2. Framework Preset: **Next.js** (자동 감지)
3. Environment Variables에 `NEXT_PUBLIC_SUPABASE_URL`, `NEXT_PUBLIC_SUPABASE_ANON_KEY` 추가
4. Deploy

배포 후 Supabase Authentication → URL Configuration에  
Vercel 도메인(`https://your-app.vercel.app`)을 Site URL / Redirect URLs에 추가하세요.

## 스크립트

```bash
npm run dev      # 개발 서버
npm run build    # 프로덕션 빌드
npm run start    # 빌드 결과 실행
```

## 라이선스

학습용 실습 프로젝트입니다.
