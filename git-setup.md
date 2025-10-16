# GitHub 설정 가이드

이 파일은 GitHub에 웹사이트를 업로드하기 위한 단계별 가이드입니다.

## 1. GitHub 저장소 생성

1. [GitHub.com](https://github.com)에 로그인
2. "New repository" 클릭
3. 저장소 설정:
   - Repository name: `metaqlab-website` (또는 원하는 이름)
   - Description: `천연물소재 분석 및 표준화 연구실 공식 웹사이트`
   - Public 선택 (무료 GitHub Pages 사용을 위해)
   - "Add a README file" 체크 해제 (이미 있음)
   - "Create repository" 클릭

## 2. 로컬 Git 저장소 초기화

PowerShell에서 다음 명령어들을 순서대로 실행하세요:

```powershell
# MetaQLab Home 폴더로 이동
cd "G:\내 드라이브\ChatGPT\cursorstudy\MetaQLab Home"

# Git 저장소 초기화
git init

# 모든 파일 추가
git add .

# 첫 번째 커밋
git commit -m "Initial commit: 천연물소재 분석 및 표준화 연구실 웹사이트"

# 메인 브랜치 설정
git branch -M main

# GitHub 저장소와 연결 (YOUR_USERNAME을 실제 GitHub 사용자명으로 변경)
git remote add origin https://github.com/YOUR_USERNAME/metaqlab-website.git

# GitHub에 업로드
git push -u origin main
```

## 3. GitHub Pages 활성화

1. GitHub 저장소 페이지에서 "Settings" 탭 클릭
2. 왼쪽 메뉴에서 "Pages" 클릭
3. Source를 "GitHub Actions"로 설정
4. "Save" 클릭

## 4. 웹사이트 접속

몇 분 후 다음 URL에서 웹사이트에 접속할 수 있습니다:
`https://YOUR_USERNAME.github.io/metaqlab-website`

## 5. 향후 업데이트

웹사이트를 수정한 후 업데이트하려면:

```powershell
cd "G:\내 드라이브\ChatGPT\cursorstudy\MetaQLab Home"

# 변경사항 추가
git add .

# 커밋
git commit -m "Update: 웹사이트 업데이트 내용"

# GitHub에 푸시
git push origin main
```

## 6. 고급 설정 (선택사항)

### 커스텀 도메인 설정
1. 도메인을 구매한 경우
2. GitHub Pages 설정에서 "Custom domain" 입력
3. 도메인 제공업체에서 DNS 설정

### Google Scholar ID 업데이트
`index.html` 파일에서 `YOUR_SCHOLAR_ID`를 실제 Google Scholar ID로 변경하세요.

### SEO 최적화
`index.html`의 `<head>` 섹션에 메타 태그를 추가할 수 있습니다:

```html
<meta name="description" content="경희대학교 약학대학 천연물소재 분석 및 표준화 연구실">
<meta name="keywords" content="천연물, 대사체학, 약학, 경희대학교, 장영표">
<meta property="og:title" content="천연물소재 분석 및 표준화 연구실">
<meta property="og:description" content="경희대학교 약학대학 천연물소재 분석 및 표준화 연구실 공식 웹사이트">
```

## 문제 해결

### 권한 오류가 발생하는 경우
GitHub에서 Personal Access Token을 생성하여 사용하세요:
1. GitHub Settings > Developer settings > Personal access tokens
2. "Generate new token" 클릭
3. 권한에서 "repo" 선택
4. 생성된 토큰을 비밀번호로 사용

### 파일이 업로드되지 않는 경우
- 파일 경로에 한글이나 특수문자가 있는지 확인
- 파일 크기가 100MB를 초과하지 않는지 확인
- .gitignore 파일에 해당 파일이 제외되어 있지 않은지 확인
