# 브랜치 기초

> 중요도: ⭐⭐ — 초고와 수정본을 분리해서 관리할 때 유용하다.

## 브랜치란?

한 줄로: **같은 논문의 다른 버전을 동시에 갖고 있는 것.**

```
main (원본)
  │
  ├── 서론 초안 작성
  ├── 본론 추가
  │
  └──── feedback-round1 (브랜치)
          ├── 서론 논증 구조 변경
          └── 2장 사례 추가
```

`main`은 안정적인 원본이고, `feedback-round1`에서 지도교수 피드백을 반영한다. 문제가 생기면 `main`은 그대로 있으니 안전하다.

## 언제 쓰나?

| 상황 | 브랜치 이름 예시 |
|---|---|
| 지도교수 1차 피드백 반영 | `feedback-round1` |
| 실험 방법론 대폭 수정 | `methodology-revision` |
| 영어 버전 작성 | `english-version` |
| 새로운 접근법 시험 | `alternative-approach` |

핵심: **큰 변경을 시도할 때**, 원본을 건드리지 않고 실험할 수 있다.

## 기본 명령어

### 브랜치 만들기 & 이동

```bash
# 새 브랜치 만들고 이동
git checkout -b feedback-round1
```

이 순간부터 작업하는 내용은 `feedback-round1` 브랜치에만 기록된다. `main`은 영향받지 않는다.

### 브랜치 확인

```bash
git branch
```

```
  main
* feedback-round1    ← 현재 여기
```

### 브랜치 간 이동

```bash
# main으로 돌아가기
git checkout main

# 다시 작업 브랜치로
git checkout feedback-round1
```

### 브랜치 합치기 (Merge)

피드백 반영이 끝나면 원본에 합친다.

```bash
# main으로 이동
git checkout main

# 브랜치 합치기
git merge feedback-round1
```

```
main
  ├── 서론 초안 작성
  ├── 본론 추가
  ├── 서론 논증 구조 변경    ← feedback-round1에서 온 변경
  └── 2장 사례 추가          ← feedback-round1에서 온 변경
```

## 실전 패턴: 피드백 반영 사이클

```
1. 현재 상태를 커밋해둔다
   git add .
   git commit -m "피드백 미팅 전 상태"

2. 피드백용 브랜치를 만든다
   git checkout -b feedback-round1

3. 피드백을 반영한다
   (작업...)
   git add .
   git commit -m "서론 논증 구조 변경"

4. 지도교수 확인 후, 원본에 합친다
   git checkout main
   git merge feedback-round1

5. 다음 피드백을 위해 반복
   git checkout -b feedback-round2
```

## 처음엔 이것만

브랜치가 복잡하게 느껴지면, 처음엔 **`main` 하나로만 작업**해도 충분하다. 커밋만 잘 해두면 되돌리기가 가능하니까.

브랜치는 "큰 수정을 할 때 원본을 보호하고 싶다"는 필요가 생겼을 때 도입하면 된다.
