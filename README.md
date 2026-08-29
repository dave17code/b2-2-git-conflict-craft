# B2-2 Git 협업 & Python 유틸리티 프로젝트

4인 팀(Kim, Kang, Joo, Kwon)의 실전 Git 협업 워크플로우 및 트러블슈팅 실습 저장소입니다.  
GitHub Flow 브랜치 전략, 코드 리뷰 기반 PR 머지, 충돌(Conflict) 해결, 그리고 Git 복구 명령어 실습을 다룹니다.

---

## 👥 팀원 소개 및 역할

| 이름 | 역할 | 유틸리티 함수 | 트러블슈팅 실습 |
| :--- | :--- | :--- | :--- |
| **Kim (팀장)** | 저장소 설정, 협업 가이드 작성 | 문자열 뒤집기 (`src/string_utils.py`) | `git commit --amend` |
| **Kang** | 프로젝트 구조화, 메인 러너 개발 | 단어 수 계산 (`src/count_utils.py`) | `git reset --soft` |
| **Joo** | 충돌 시나리오 관리 및 기록 | 중복 제거 (`src/list_utils.py`) | `git revert` |
| **Kwon** | 트러블슈팅 문서화, 최종 인덱스 | 짝수 판별 (`src/math_utils.py`) | `git stash` |

---

## 📁 프로젝트 구조

```text
b2-2-git-collaboration/
├── docs/
│   ├── CONTRIBUTING.md          # 브랜치 전략 및 커밋 컨벤션
│   ├── conflict-resolution.md   # 일반/비자명 충돌 해결 기록
│   └── troubleshooting-log.md   # 4종 Git 트러블슈팅 실습 로그
├── src/
│   ├── main.py                  # 전체 유틸 함수 통합 실행 파일
│   ├── string_utils.py          # [Kim] 문자열 유틸
│   ├── count_utils.py           # [Kang] 단어 수 유틸
│   ├── list_utils.py            # [Joo] 리스트 유틸
│   └── math_utils.py            # [Kwon] 수학 유틸
├── SUBMISSION.md                # 최종 제출 인덱스 및 Git Graph 증빙
└── README.md                    # 프로젝트 소개 문서