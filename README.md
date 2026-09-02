# B2-2 Git 협업 & Python 유틸리티 프로젝트

4인 팀 **Kim, Kang, Joo, Kwon**이 GitHub Flow를 기반으로 실제 Git 협업 과정을 실습한 프로젝트입니다.

단순한 Python 기능 구현보다 **Issue 기반 작업 관리, Feature 브랜치, Pull Request, 코드 리뷰, 충돌 해결, Git 트러블슈팅 기록**을 중심으로 협업 워크플로우를 경험하고 문서화하는 것을 목표로 합니다.

---

## 👥 팀원 및 역할

| 이름           | 역할                     | Python 유틸리티                   | Git 트러블슈팅                     |
| :----------- | :--------------------- | :---------------------------- | :---------------------------- |
| **Kim (팀장)** | 저장소 관리 및 협업 가이드 작성     | 문자열 뒤집기 `src/string_utils.py` | `git commit --amend`          |
| **Kang**     | 프로젝트 구조화 및 메인 실행 코드 작성 | 단어 수 계산 `src/count_utils.py`  | `git reset --soft HEAD~1`     |
| **Joo**      | 충돌 시나리오 실습 및 기록        | 중복 제거 `src/list_utils.py`     | `git revert`                  |
| **Kwon**     | 트러블슈팅 문서화 및 제출 인덱스 작성  | 짝수 판별 `src/math_utils.py`     | `git stash` / `git stash pop` |

---

## 🌿 브랜치 전략

우리 팀은 **GitHub Flow**를 사용합니다.

* `main` 브랜치는 항상 정상 동작하는 상태를 유지합니다.
* 모든 작업은 `feature/*` 브랜치에서 진행합니다.
* 작업 완료 후 Pull Request와 코드 리뷰를 거쳐 `main`에 병합합니다.

GitHub Flow는 구조가 단순하고 Pull Request 중심으로 협업 과정을 명확하게 추적할 수 있어 이번 프로젝트의 협업 방식으로 선택했습니다.

브랜치 네이밍과 세부 협업 규칙은 [`docs/CONTRIBUTING.md`](docs/CONTRIBUTING.md)에서 확인할 수 있습니다.

---

## 🔄 협업 흐름

```text
Issue 생성
    ↓
feature/* 브랜치 생성
    ↓
작업 및 Commit
    ↓
원격 저장소 Push
    ↓
Pull Request 생성
    ↓
팀원 Code Review
    ↓
리뷰 내용 반영
    ↓
Approve
    ↓
main Merge
```

모든 주요 작업은 Issue와 연결하며 PR 본문에는 다음 내용을 기록합니다.

* 변경 사항(What)
* 변경 이유(Why)
* 테스트 및 검증 방법(How)
* `Closes #이슈번호`

---

## 📁 프로젝트 구조

```text
b2-2-git-conflict-craft/
├── docs/
│   ├── CONTRIBUTING.md
│   │   └── 브랜치 전략, 커밋 컨벤션, PR 및 리뷰 규칙
│   │
│   ├── conflict-resolution.md
│   │   └── 일반 충돌 및 비자명 충돌 해결 기록
│   │
│   ├── troubleshooting-log.md
│   │   └── Git 트러블슈팅 4종 실습 기록
│   │
│   └── git-log.txt
│       └── Git 브랜치 및 커밋 히스토리 증빙
│
├── src/
│   ├── main.py
│   │   └── 유틸리티 함수 실행 예제
│   │
│   ├── string_utils.py
│   │   └── [Kim] 문자열 뒤집기
│   │
│   ├── count_utils.py
│   │   └── [Kang] 단어 수 계산
│   │
│   ├── list_utils.py
│   │   └── [Joo] 리스트 중복 제거
│   │
│   └── math_utils.py
│       └── [Kwon] 짝수 판별
│
├── SUBMISSION.md
│   └── 팀원별 Issue / PR 및 제출물 인덱스
│
└── README.md
    └── 프로젝트 소개 및 실행 안내
```

---

## 🐍 Python 유틸리티

### Kim - 문자열 뒤집기

```python
from string_utils import reverse_string

print(reverse_string("abc"))
# cba
```

### Kang - 단어 수 계산

```python
from count_utils import count_words

print(count_words("Hello Python Git"))
# 3
```

### Joo - 리스트 중복 제거

```python
from list_utils import remove_duplicates

print(remove_duplicates([1, 2, 2, 3]))
# [1, 2, 3]
```

### Kwon - 짝수 판별

```python
from math_utils import is_even

print(is_even(4))
# True
```

---

## ▶️ 실행 방법

프로젝트 루트에서 다음 명령을 실행합니다.

```bash
python3 src/main.py
```

실행 예시:

```text
=== Python Utils Demo ===
Kim Result: dlroW olleH
Kang Result: 4
```

---

## 💥 충돌 해결 실습

팀 전체에서 총 2회의 충돌 해결 과정을 기록했습니다.

### 충돌 1 - 동일 파일의 인접 영역 수정

* 참여자: Kim / Kang
* 파일: `src/main.py`
* 유형: 동일 파일의 같은 실행 영역 수정
* 해결 방법: 두 기능을 모두 유지하도록 코드 통합

### 충돌 2 - Rename / Modify 비자명 충돌

* 참여자: Joo / Kwon
* 파일: `docs/old-guide.md` → `docs/new-file.md`
* 유형: 한쪽 브랜치에서는 파일명 변경, 다른 브랜치에서는 기존 파일 내용 수정
* 해결 방법: 새로운 파일명을 유지하면서 기존 수정 내용을 새 파일에 반영

상세 과정은 [`docs/conflict-resolution.md`](docs/conflict-resolution.md)에 기록했습니다.

---

## 🧯 Git 트러블슈팅 실습

팀원별로 다음 Git 트러블슈팅 시나리오를 수행했습니다.

| 담당자  | 명령                            | 실습 내용                        |
| :--- | :---------------------------- | :--------------------------- |
| Kim  | `git commit --amend`          | 최근 커밋 수정                     |
| Kang | `git reset --soft HEAD~1`     | 최근 로컬 커밋 취소 후 변경 내용 유지       |
| Joo  | `git revert`                  | 원격에 공유된 커밋을 새로운 커밋으로 안전하게 취소 |
| Kwon | `git stash` / `git stash pop` | 작업 중인 변경 사항 임시 보관 및 복원       |

상세 과정은 [`docs/troubleshooting-log.md`](docs/troubleshooting-log.md)에 기록했습니다.

---

## 💬 코드 리뷰 규칙

모든 Feature 작업은 Pull Request를 통해 `main`에 병합합니다.

코드 리뷰에서는 단순히 `LGTM`, `좋아요`와 같은 의견만 남기지 않고 다음과 같은 실질적인 리뷰를 작성합니다.

* 특정 코드 또는 파일을 근거로 한 질문
* 개선 가능한 코드 제안
* 예외 상황 또는 위험 요소 확인
* 함수명 및 가독성 개선 의견
* 테스트 방법 및 추가 검증 제안

PR 작성자는 리뷰 내용을 확인하고 필요한 경우 추가 커밋 또는 답글을 통해 반영합니다.

---

## 📝 커밋 메시지 규칙

커밋 메시지는 변경 목적을 알 수 있도록 작성합니다.

예시:

```text
feat: add string reverse utility
fix: handle empty string input
docs: update contributing guide
refactor: simplify list utility
```

다음과 같이 변경 내용을 알기 어려운 메시지는 사용하지 않습니다.

```text
update
fix
temp
wip
final
edit file
```

---

## 📚 주요 문서

* [협업 가이드](docs/CONTRIBUTING.md)
* [충돌 해결 기록](docs/conflict-resolution.md)
* [Git 트러블슈팅 기록](docs/troubleshooting-log.md)
* [Git 히스토리 증빙](docs/git-log.txt)
* [최종 제출 인덱스](SUBMISSION.md)

---

## ✅ 프로젝트 완료 항목

* GitHub Flow 적용
* Feature 브랜치 기반 작업
* Issue 기반 작업 관리
* Issue와 Pull Request 연동
* 팀원별 Pull Request 작성
* 팀원별 코드 리뷰 수행
* 리뷰 피드백 반영
* 커밋 메시지 컨벤션 적용
* 일반 Git 충돌 해결
* Rename / Modify 비자명 충돌 해결
* `git commit --amend` 실습
* `git reset --soft HEAD~1` 실습
* `git revert` 실습
* `git stash` / `git stash pop` 실습
* Python 유틸리티 함수 팀원별 구현
* 협업 및 트러블슈팅 과정 문서화
