# GitHub 연동

> 중요도: ⭐⭐⭐ — GitHub는 논문 폴더를 온라인에 백업해두는 곳이라고 생각하면 된다.

## GitHub는 왜 쓰나?

아주 간단히 말하면, **논문 작업 폴더를 인터넷에도 하나 더 저장해두는 것**이다.

그래서:

- 컴퓨터가 바뀌어도 이어서 작업할 수 있고
- 문제가 생겨도 백업이 남고
- 필요하면 다른 사람과도 공유할 수 있다

## 이 가이드에서는

GitHub 연결은 **SSH 키 방식만** 사용한다.

이 설정은 처음에 한 번만 해두면 된다.

## 초기 설정

처음 연결할 때는 아래 순서로 진행하면 된다.

### 1. GitHub 계정 만들기

[github.com](https://github.com)에서 계정을 만든다.

### 2. 새 저장소 만들기

GitHub에서 새 저장소를 만들고, 논문 프로젝트라면 보통 `Private`로 두면 된다.

### 3. SSH 키 만들기

에이전트에게 "GitHub SSH 키 설정 도와줘"라고 하면 된다.

직접 할 경우 보통 아래처럼 진행한다.

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

### 4. 공개 키를 GitHub에 등록하기

생성한 공개 키 내용을 GitHub의 SSH key 설정 화면에 등록한다.

이 단계도 에이전트에게 맡기면 훨씬 편하다.

### 5. 로컬 프로젝트와 연결하기

```bash
git remote add origin git@github.com:내아이디/masters-thesis.git
git push -u origin main
```

여기까지 끝나면 이후부터는 같은 프로젝트에서 계속 push/pull 하면서 쓰면 된다.

## 에이전트와 함께 쓸 때

실제로는 이렇게 맡기면 된다.

- "GitHub 저장소 연결해줘"
- "SSH 키 방식으로 GitHub 설정 도와줘"
- "이 프로젝트를 GitHub에 연결하고 push까지 해줘"
- "다른 컴퓨터에서도 쓸 수 있게 GitHub 연동 상태를 점검해줘"

사용자는 GitHub가 **온라인 백업 공간**이라는 점만 알고 있으면 충분하다.

## 이것만 기억하면 된다

- GitHub는 온라인 백업이다
- 프로젝트마다 한 번 연결해두면 된다
- 이후에는 커밋 후 바로 push 하면 된다
- 실제 설정은 에이전트에게 맡기면 된다

## 필요할 때 찾아보는 내용

### SSH 주소 예시

```bash
git remote add origin git@github.com:내아이디/masters-thesis.git
git push -u origin main
```

### 다른 컴퓨터에서 가져오기

```bash
git clone git@github.com:내아이디/masters-thesis.git
git pull
```

지금은 명령어를 외우기보다, 필요할 때 다시 찾아보는 정도면 충분하다.
