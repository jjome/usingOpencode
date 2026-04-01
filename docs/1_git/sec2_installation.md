# 설치 & 초기 설정

> 중요도: ⭐ — 한 번 하면 다시 볼 일 없다.

## Git 설치

### Windows

[git-scm.com](https://git-scm.com/download/win)에서 다운로드 후 설치. 설치 옵션은 전부 기본값으로 진행하면 된다.

### macOS

터미널을 열고 입력:

```bash
xcode-select --install
```

### 설치 확인

```bash
git --version
```

버전 번호가 나오면 성공.

## 초기 설정

Git을 처음 쓸 때 **딱 한 번만** 설정하면 된다. 커밋에 남는 이름과 이메일이다.

```bash
git config --global user.name "홍길동"
git config --global user.email "hong@university.ac.kr"
```

학교 이메일을 쓰면 나중에 누가 작업했는지 구분하기 쉽다.

## 확인

```bash
git config --list
```

설정한 이름과 이메일이 보이면 완료.
