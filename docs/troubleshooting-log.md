# Troubleshooting Log

## 1. git commit --amend (최근 커밋 메시지 수정)
- **참여자**: Kim
- **상황**: 커밋 메시지에 오타(`contriibuting typo`)가 발생함.
- **해결 명령**: `git commit --amend -m "docs: add contributing guide and team rules"`
- **주의점**: 원격(Remote)에 이미 푸시된 커밋은 로컬 상태에서만 amend하는 것이 안전함.

## 2. git reset --soft HEAD~1 (로컬 커밋 취소 + 변경사항 유지)
- **참여자**: Kang
- **상황**: 미완성 파일을 실수로 커밋했으나 작업 코드는 그대로 보존해야 함.
- **해결 명령**: `git reset --soft HEAD~1`
- **결과**: 스테이징(Staged) 상태로 되돌려져 코드를 보완 후 재커밋함.

## 3. git revert (원격에 푸시된 커밋 안전 취소)
- **참여자**: Joo
- **상황**: 원격 저장소에 잘못 푸시된 커밋을 히스토리 보존 상태로 취소해야 함.
- **해결 명령**: `git revert <commit-hash> --no-edit`
- **선택 이유**: 히스토리를 덮어쓰지 않고 "취소 커밋"을 새로 생성하여 협업 브랜치에 안전함.

## 4. git stash / git stash pop (작업 임시 보관 후 복원)
- **참여자**: Kwon
- **상황**: 작업 미완료 상태에서 긴급 브랜치 전환 필요.
- **해결 명령**: `git stash` ➔ (브랜치 전환/작업) ➔ `git stash pop`
- **결과**: 미완성 커밋 없이 작업 상태를 깔끔하게 복원함.