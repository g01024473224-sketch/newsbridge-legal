# 뉴스브릿지 법적 고지 (Legal)

뉴스브릿지(NewsBridge) 앱의 **이용약관**과 **개인정보처리방침** 정적 HTML 페이지.

GitHub Pages 로 자동 배포되어 앱 / Play Console / App Store Connect 의 외부 링크로 사용됩니다.

## 파일 구조

```
legal/
├── index.html        # 진입점 (이용약관 / 개인정보처리방침 링크 모음)
├── privacy.html      # 개인정보처리방침
├── terms.html        # 이용약관
├── .github/
│   └── workflows/
│       └── deploy.yml  # main 브랜치 push 시 GitHub Pages 로 자동 배포
└── README.md
```

## 배포 URL

배포 완료 후 다음 URL 로 접근 가능:

| 페이지 | URL |
| --- | --- |
| 진입점 | `https://g01024473224.github.io/newsbridge-legal/` |
| 이용약관 | `https://g01024473224.github.io/newsbridge-legal/terms.html` |
| 개인정보처리방침 | `https://g01024473224.github.io/newsbridge-legal/privacy.html` |

## 최초 배포 절차 (한 번만)

### 1. 새 GitHub 리포지토리 생성

[github.com/new](https://github.com/new) 에서 **Public** 리포지토리 `newsbridge-legal` 생성. README 자동 생성 옵션은 꺼둡니다 (덮어쓰기 충돌 방지).

### 2. 로컬 리포지토리 초기화 + 푸시

`C:\Users\g0102\Desktop\newsbridge\legal\` 에서:

```bash
git init -b main
git add .
git commit -m "feat: initial legal pages"
git remote add origin https://github.com/g01024473224/newsbridge-legal.git
git push -u origin main
```

### 3. GitHub Pages 활성화

리포지토리 페이지에서:

1. **Settings** → **Pages**
2. **Source**: `GitHub Actions` 선택 (기본 deploy from branch 가 아닌 Actions 사용)
3. 저장하면 첫 푸시에 자동으로 `.github/workflows/deploy.yml` 가 트리거되어 1~2분 내 배포 완료
4. 배포 완료 후 위 표의 URL 들이 활성화됨

### 4. 이후 변경

`legal/` 폴더에서 파일 수정 → `git add . && git commit -m "..."` → `git push`.
push 마다 workflow 가 자동 실행되어 갱신된 페이지가 1~2분 내 반영됩니다.

## 앱 / 스토어에서 연결

배포 URL 들을 다음 위치에 등록합니다:

- **Google Play Console** → 앱 콘텐츠 → 개인정보처리방침 → privacy.html URL
- **App Store Connect** → 앱 정보 → 개인정보 처리방침 URL → privacy.html URL
- 앱 내 설정 화면의 "이용약관" / "개인정보처리방침" 행이 in-app 화면 대신 외부 브라우저로 이 URL 열도록 변경 가능 (선택)

## 변경 이력

- 2026-05-20 — 초안 작성 (시행)
