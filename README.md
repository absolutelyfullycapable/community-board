# community-board

Next.js + Supabase로 만든 커뮤니티 게시판입니다.  
게시글, 댓글, 좋아요/싫어요를 지원합니다.

## 환경 변수

`.env.example`을 참고해 `.env.local`에 아래 값을 넣습니다.

| 변수 | 설명 |
|------|------|
| `NEXT_PUBLIC_SUPABASE_URL` | Supabase Project URL |
| `NEXT_PUBLIC_SUPABASE_ANON_KEY` | Supabase anon key |

## 로컬 실행

```bash
npm install
cp .env.example .env.local
npm run dev
```

## 배포 (Vercel)

1. 이 저장소를 Vercel에 Import
2. 위 환경 변수를 등록한 뒤 Deploy
3. Supabase → Authentication → URL Configuration에 Vercel 도메인 추가

가입 직후 로그인이 안 되면 Supabase Email 설정의 Confirm email을 끄면 됩니다.
