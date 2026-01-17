# 05-1. 베스트 프랙티스

깃허브-위키독스 연동을 효과적으로 활용하기 위한 **베스트 프랙티스**를 정리합니다.

## 문서 구조

### DO: 명확한 번호 체계 사용

```
01-introduction.md
02-getting-started.md
03-basic-usage.md
```

### DON'T: 임의의 이름 사용

```
intro.md
start.md
usage.md
```

## 커밋 메시지

### DO: 의미 있는 메시지

```bash
git commit -m "docs: API 인증 섹션 추가"
git commit -m "fix: 설치 가이드 오타 수정"
```

### DON'T: 모호한 메시지

```bash
git commit -m "update"
git commit -m "fix"
```

## 브랜치 관리

### DO: 목적별 브랜치

```
feature/api-docs
fix/broken-links
refactor/toc-structure
```

### DON'T: 임시 브랜치

```
test
temp
my-branch
```

## 파일 관리

### DO: 일관된 구조

```
pages/          # 모든 문서
assets/         # 모든 이미지
```

### DON'T: 분산된 구조

```
docs/
images/
pages/
files/
```

## 협업 규칙

### 권장 사항

| 항목 | 권장 |
|------|------|
| PR 크기 | 작고 집중된 변경 |
| 리뷰 | 24시간 내 응답 |
| 커밋 | 논리적 단위로 분리 |
| 문서화 | 변경 시 즉시 업데이트 |

## 품질 관리

### 체크리스트

- [ ] 마크다운 문법 오류 없음
- [ ] 이미지 경로 정상
- [ ] 내부 링크 작동
- [ ] TOC.md 업데이트됨
- [ ] 오타 검사 완료

### 정기 점검

```
주간: 오타 및 오류 확인
월간: 내용 최신화
분기: 구조 검토 및 개선
```

## 자동화 팁

### GitHub Actions 활용

```yaml
# .github/workflows/docs-check.yml
name: Docs Check
on: [push, pull_request]
jobs:
  check:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Markdown Lint
        uses: DavidAnson/markdownlint-cli2-action@v9
```

## 핵심 원칙

1. **일관성**: 규칙을 정하고 일관되게 적용
2. **간결성**: 불필요한 내용 제거
3. **최신성**: 문서를 항상 최신 상태로 유지
4. **접근성**: 누구나 이해할 수 있게 작성

베스트 프랙티스를 따르면 문서의 품질과 유지보수성이 크게 향상됩니다.
