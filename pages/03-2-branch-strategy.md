체계적인 문서 관리를 위한 **브랜치 전략**을 알아봅니다.

## 브랜치란?

브랜치(Branch)는 독립적인 작업 공간입니다. 메인 브랜치에 영향을 주지 않고 새로운 작업을 진행할 수 있습니다.

## 추천 브랜치 전략

### 메인 브랜치 (main)

- 항상 배포 가능한 상태 유지
- 위키독스와 동기화되는 브랜치
- 직접 커밋 대신 PR을 통해 병합

### 기능 브랜치 (feature/*)

새로운 챕터나 기능을 추가할 때 사용합니다.

```bash
# 새 기능 브랜치 생성
git checkout -b feature/chapter-04

# 작업 완료 후 main에 병합
git checkout main
git merge feature/chapter-04
```

### 수정 브랜치 (fix/*)

오타나 오류를 수정할 때 사용합니다.

```bash
git checkout -b fix/typo-chapter-02
# 수정 후 병합
```

## 브랜치 네이밍 규칙

| 접두사 | 용도 | 예시 |
|--------|------|------|
| feature/ | 새 기능/챕터 | feature/api-docs |
| fix/ | 버그/오타 수정 | fix/broken-link |
| refactor/ | 구조 개선 | refactor/toc-structure |
| docs/ | 문서 개선 | docs/readme-update |

## PR 기반 워크플로우

팀 협업 시 권장되는 워크플로우입니다.

```
1. 브랜치 생성
   git checkout -b feature/new-chapter

2. 작업 및 커밋
   git add .
   git commit -m "docs: 새 챕터 작성"

3. 푸시
   git push origin feature/new-chapter

4. PR 생성
   GitHub에서 Pull Request 생성

5. 리뷰 및 수정
   팀원 리뷰 후 필요시 수정

6. 병합
   승인 후 main에 병합

7. 브랜치 삭제
   git branch -d feature/new-chapter
```

## 브랜치 전략의 이점

- **격리**: 작업 중인 내용이 배포에 영향 없음
- **리뷰**: 병합 전 검토 가능
- **실험**: 안전하게 새로운 시도 가능
- **병렬 작업**: 여러 작업 동시 진행

## 간단한 전략 vs 복잡한 전략

| 팀 규모 | 권장 전략 |
|---------|----------|
| 1인 | main 직접 커밋 가능 |
| 2-5인 | feature 브랜치 + PR |
| 5인 이상 | 상세 브랜치 규칙 + 리뷰어 지정 |

팀 상황에 맞는 적절한 전략을 선택하세요.
