# .gitignore

> 중요도: ⭐ — 처음에 한 번 설정하면 끝.

## .gitignore란

Git에게 "이 파일은 추적하지 마"라고 알려주는 설정 파일이다.

논문 폴더에는 Git으로 관리할 필요 없는 파일들이 있다:

- OS가 자동 생성하는 파일 (`.DS_Store`, `Thumbs.db`)
- 편집기 설정 파일
- PDF 빌드 결과물 (원본 Markdown만 추적하면 됨)
- 임시 파일

## 논문 프로젝트용 .gitignore 예시

프로젝트 루트에 `.gitignore` 파일을 만들고 아래 내용을 넣는다:

```
# OS 자동 생성 파일
.DS_Store
Thumbs.db

# 편집기 설정
.vscode/
.idea/

# 빌드 결과물
*.pdf
output/

# 임시 파일
*.tmp
*.bak
*~

# OpenCode 작업 파일
.opencode/
```

## 사용법

1. 프로젝트 폴더에 `.gitignore` 파일 생성
2. 위 내용 붙여넣기
3. 필요에 따라 추가/수정

이후 `git add .`을 해도 무시 목록에 있는 파일은 추적되지 않는다.

## 팁

- PDF를 Git으로 관리하고 싶다면 `*.pdf` 줄을 삭제
- 나중에 추가해도 되지만, **이미 커밋된 파일**은 `.gitignore`에 넣어도 계속 추적된다. 이 경우 `git rm --cached 파일명`으로 추적을 해제해야 한다.
