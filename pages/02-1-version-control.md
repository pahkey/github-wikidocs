깃허브 연동의 가장 큰 장점 중 하나는 **Git의 버전 관리 기능**을 문서에 적용할 수 있다는 것입니다.

## 변경 이력 추적

모든 수정 사항이 커밋(commit)으로 기록됩니다. 누가, 언제, 무엇을 변경했는지 명확하게 확인할 수 있습니다.

```bash
# 변경 이력 확인
git log --oneline

# 출력 예시
a1b2c3d docs: API 문서 업데이트
e4f5g6h docs: 설치 가이드 추가
i7j8k9l docs: 초기 문서 작성
```

## 버전 비교

두 버전 간의 차이를 쉽게 비교할 수 있습니다. 어떤 내용이 추가되고 삭제되었는지 한눈에 파악할 수 있습니다.

```bash
# 특정 커밋과 현재 상태 비교
git diff a1b2c3d

# 두 커밋 간 비교
git diff a1b2c3d e4f5g6h
```

## 롤백 기능

실수로 잘못된 내용을 작성했다면 이전 버전으로 쉽게 되돌릴 수 있습니다.

```bash
# 특정 파일을 이전 버전으로 복원
git checkout a1b2c3d -- pages/02-setup.md

# 전체를 특정 커밋으로 되돌리기
git revert a1b2c3d
```

## 브랜치를 통한 실험

새로운 내용을 시험적으로 작성할 때 브랜치를 활용할 수 있습니다.

```bash
# 새 브랜치 생성
git checkout -b feature/new-chapter

# 작업 후 병합
git checkout main
git merge feature/new-chapter
```

## 버전 관리의 이점 정리

| 기능 | 활용 |
|------|------|
| 커밋 이력 | 변경 사항 추적 및 기록 |
| diff | 버전 간 차이 확인 |
| revert | 실수 복구 |
| branch | 독립적인 작업 공간 |
| tag | 중요 버전 표시 (v1.0, v2.0) |

버전 관리를 통해 문서의 품질과 안정성을 크게 높일 수 있습니다.
