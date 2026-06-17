# 정책자금 AI 진단 - 배포 가이드

## 📁 폴더 구조
```
policy-fund-deploy/
├── api/
│   └── claude.js        ← Vercel Serverless Function (API 키 보관)
├── public/
│   └── index.html       ← 메인 홈페이지
├── vercel.json          ← Vercel 설정
└── README.md
```

---

## 🚀 배포 순서 (15분이면 완료)

### 1단계: GitHub에 올리기

1. [github.com](https://github.com) 로그인 → **New repository**
2. Repository 이름: `policy-fund-ai` (공개: Public)
3. **이 폴더 안의 파일들을 모두 업로드**
   - `api/claude.js`
   - `public/index.html`
   - `vercel.json`
   - `README.md`

### 2단계: Vercel에 배포하기

1. [vercel.com](https://vercel.com) → GitHub 계정으로 로그인
2. **Add New Project** → 위에서 만든 `policy-fund-ai` repository 선택
3. **Deploy** 클릭 (설정 변경 없이 바로)

### 3단계: API 키 등록 (핵심!)

1. Vercel 대시보드 → 프로젝트 선택
2. **Settings → Environment Variables**
3. 아래 값 추가:
   - **Name**: `ANTHROPIC_API_KEY`
   - **Value**: `sk-ant-api03-...` (본인의 Anthropic API 키)
   - **Environment**: Production, Preview, Development 모두 체크
4. **Save** → **Redeploy** (재배포 필요)

### 4단계: 완료!

- 주소: `https://policy-fund-ai.vercel.app` (자동 생성)
- 커스텀 도메인 연결도 가능 (Settings → Domains)

---

## 🔑 Anthropic API 키 발급

1. [console.anthropic.com](https://console.anthropic.com) 접속
2. **API Keys → Create Key**
3. 키 복사 후 Vercel 환경변수에 붙여넣기

---

## ⚠️ 주의사항

- API 키는 절대 `index.html`이나 GitHub에 직접 넣지 마세요
- Vercel Environment Variables에만 보관하면 안전합니다
- Anthropic API 사용량에 따라 비용이 발생할 수 있습니다
