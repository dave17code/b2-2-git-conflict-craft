# Contributing Guide

## 1. 브랜치 전략 (GitHub Flow)

- `main`: 상시 배포 가능하며 항상 동작하는 기준 브랜치
- `feature/*`: 기능 및 문서 작업용 임시 브랜치
- **우리 팀이 GitHub Flow를 선택한 이유 (3줄)**:
  1. 복잡한 릴리즈 브랜치 없이 구조가 단순하여 팀원 간 학습 및 적응이 빠릅니다.
  2. `main` 브랜치를 상시 안정 상태로 유지하여 충돌 위험을 줄입니다.
  3. Pull Request 기반으로 코드 리뷰와 품질 검증을 신속하게 진행할 수 있습니다.

## 2. 브랜치 네이밍 규칙

- 형식: `feature/<작업자이름>-<기능명>` (예: `feature/kim-string-utils`)

## 3. 커밋 메시지 컨벤션

- 접두사: `feat:`, `fix:`, `docs:`, `refactor:`, `test:`, `chore:`
- 금지 사항: 변경 대상이 불분명한 단어(`update`, `fix`, `temp`, `wip` 등) 단독 사용 금지

## 4. PR 및 리뷰 규칙

- PR 본문에 `Closes #이슈번호`, `What`, `Why`, `How` 필수 포함
- 최소 1명 이상의 승인(Approve) 및 실질적 개선 코멘트 필수 (단순 "LGTM" 금지)

## 5. 충돌 대응 흐름

- 충돌 발생 ➔ 슬랙/디스코드 공유 ➔ 로컬에서 main pull 후 해결 ➔ `docs/conflict-resolution.md` 기록
