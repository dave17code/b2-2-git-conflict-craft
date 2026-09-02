# Conflict Resolution Log

## 충돌 기록 #1 - main.py 동일 영역 충돌

### 참여자
- Kim
- Kang

### 상황(What happened)
Kim과 Kang이 서로 다른 feature 브랜치에서 `src/main.py`의 동일한 실행 영역을 수정했다.

- Kim: `reverse_string()` 실행 결과 추가
- Kang: `count_words()` 실행 결과 추가

서로 다른 브랜치에서 같은 파일의 인접 영역을 수정하면서 병합 과정에서 충돌이 발생했다.

### 충돌 내용(Conflict)
Git이 두 변경 사항 중 어느 코드를 최종 결과로 사용할지 자동으로 결정하지 못해 충돌이 발생했다.

```text
<<<<<<< HEAD
현재 브랜치 변경 내용
=======
병합하려는 브랜치 변경 내용
>>>>>>> main
```

### 해결 과정(How)
한쪽 변경 사항을 삭제하지 않고 Kim과 Kang의 기능을 모두 유지하도록 `src/main.py`를 직접 수정했다.

최종적으로 두 유틸리티 함수를 모두 import하고 실행하도록 통합했다.

```python
from string_utils import reverse_string
from count_utils import count_words

if __name__ == "__main__":
    print("=== Python Utils Demo ===")
    print("Kim Result:", reverse_string("Hello World"))
    print("Kang Result:", count_words("Hello Python Git Collaboration"))
```

### 결과(Outcome)
Kim의 문자열 뒤집기 기능과 Kang의 단어 수 계산 기능이 모두 유지되었다.

- 관련 PR: #14, #15
- 충돌 해결 커밋: `abe92b8`

### 배운 점(Learnings)
같은 파일의 동일하거나 인접한 영역을 여러 브랜치에서 수정하면 Git이 자동 병합하지 못할 수 있다는 것을 확인했다.

충돌 해결 시 한쪽 변경을 삭제하는 것이 아니라 각 변경의 목적을 확인하고 필요한 기능을 모두 유지해야 한다.

---

## 충돌 기록 #2 - Rename / Modify 비자명 충돌

### 참여자
- Joo
- Kwon

### 상황(What happened)
서로 다른 feature 브랜치에서 동일한 문서 파일에 서로 다른 종류의 변경을 수행했다.

Joo는 파일명을 다음과 같이 변경했다.

```text
docs/old-guide.md
→
docs/new-file.md
```

동시에 Kwon은 기존 `docs/old-guide.md`의 내용을 수정했다.

한쪽에서는 파일이 이동되고 다른 쪽에서는 기존 경로의 파일 내용이 수정되면서 비자명 충돌이 발생했다.

### 충돌 내용(Conflict)
Git이 기존 파일의 이동과 기존 경로에서 발생한 내용 변경을 자동으로 하나의 결과로 판단하기 어려운 상황이 발생했다.

### 해결 과정(How)
새로운 파일명인 `docs/new-file.md`를 최종 파일로 유지했다.

기존 `docs/old-guide.md`에서 수정된 내용은 `docs/new-file.md`에 반영하여 두 변경 사항을 모두 유지했다.

### 결과(Outcome)
파일명 변경과 내용 수정이 모두 유지되었다.

- 관련 PR: #22, #24
- 충돌 해결 커밋: `fee0b98`

### 배운 점(Learnings)
Git 충돌은 동일한 코드 줄을 수정할 때뿐만 아니라 파일 이름 변경과 내용 수정이 서로 다른 브랜치에서 동시에 발생할 때도 생길 수 있다는 것을 확인했다.

Rename/Modify 충돌에서는 최종 파일 위치와 유지해야 할 내용을 개발자가 직접 판단하여 해결해야 한다.