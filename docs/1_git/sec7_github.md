# GitHub 연동

> 중요도: ⭐⭐⭐ — 백업과 공유. 논문이 날아가지 않도록 반드시 설정한다.

## GitHub이란

GitHub은 Git 저장소를 온라인에 올려두는 서비스다. 핵심 용도:

- **백업**: 컴퓨터 고장, 분실, 랜섬웨어로부터 논문 보호
- **공유**: 지도교수에게 URL 하나로 전달
- **어디서든**: 연구실, 집, 카페 어디서든 이어서 작업

## 초기 설정 (한 번만)

### 1. GitHub 계정 만들기

[github.com](https://github.com)에서 가입. 학교 이메일로 가입하면 [GitHub Education](https://education.github.com) 혜택을 받을 수 있다 (Private 저장소 무제한 등).

### 2. 새 저장소 만들기

GitHub 사이트에서:
1. 우측 상단 `+` → `New repository`
2. 이름 입력 (예: `masters-thesis`)
3. **Private** 선택 (논문은 비공개로)
4. `Create repository` 클릭

### 3. 내 컴퓨터와 연결

GitHub이 안내하는 명령어를 따라 하면 된다:

```bash
# 이미 로컬에 저장소가 있는 경우
git remote add origin https://github.com/내아이디/masters-thesis.git
git push -u origin main
```

### 4. 인증 설정

처음 push할 때 로그인을 요구한다. 방법은 두 가지:

**방법 A: HTTPS (간단)**
- push할 때 ID/비밀번호 입력
- Personal Access Token 필요 (GitHub Settings → Developer settings → Tokens)

**방법 B: SSH (한 번 설정하면 편함)**
- SSH 키 생성 후 GitHub에 등록
- 이후 비밀번호 입력 없이 push/pull 가능

AI에게 "GitHub SSH 키 설정 도와줘"라고 하면 단계별로 안내받을 수 있다.

## 일상 사용

### 작업 후 백업 (push)

```bash
git push
```

커밋한 내용을 GitHub에 올린다. **하루 작업 끝에 반드시 한 번.**

### 다른 곳에서 이어 작업 (clone & pull)

```bash
# 처음 다운로드할 때
git clone https://github.com/내아이디/masters-thesis.git

# 이후 최신 내용 가져올 때
git pull
```

## 지도교수와 공유

### Private 저장소에 초대

1. GitHub 저장소 → `Settings` → `Collaborators`
2. 지도교수 GitHub 아이디 입력 → 초대

지도교수가 직접 코멘트를 달거나, 변경 이력을 확인할 수 있다.

### 또는 단순 공유

GitHub에서 직접 파일을 볼 수 있으므로, 저장소 URL을 공유하기만 해도 된다. Markdown 파일은 GitHub에서 자동으로 예쁘게 렌더링된다.

## 핵심 습관

```
아침: git pull (최신 상태로 시작)
작업: 커밋 여러 번
저녁: git push (백업)
```

이 습관만 들이면 논문을 잃어버릴 일이 없다.
