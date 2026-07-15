# GITHUB-COLLAB.md

이 파일은 `AGENTS.md` §30(Pull Request 활용), §34(Pull Request Quality), §35(Public Repository Readiness), §36(Release Completion), §37(Upstream Contribution)에서 참조하는 세부 규칙입니다. Pull Request를 열 때, 릴리스를 마무리할 때, 공개 저장소를 점검할 때, 업스트림 오픈소스에 기여할 때 읽습니다.

---

### 30. 대규모 변경 예시와 Branch Naming

- 대규모 또는 영향이 큰 변경의 예:
  - 아키텍처, 폴더 구조, 핵심 모듈의 큰 변경
  - 광범위한 리팩터링 또는 대량 파일 변경
  - 호환성, 데이터 마이그레이션, 릴리스에 영향을 주는 변경
  - 되돌리기 어렵거나 별도 리뷰가 필요한 변경
  - 공개·공유 저장소에서 협업자 리뷰가 필요한 변경

#### Branch Naming

권장 브랜치 이름:

```text
feat/<short-description>
fix/<short-description>
refactor/<short-description>
docs/<short-description>
chore/<short-description>
release/<version>
```

---

### 34. Pull Request 본문 템플릿

```md
## Summary

변경 목적과 핵심 내용을 설명한다.

## Motivation

왜 이 변경이 필요한지 설명한다.

## Changes

구현된 변경 사항을 항목별로 기록한다.

## Validation

실행한 테스트, 빌드, 정적 분석 결과를 기록한다.

## Risks

회귀 가능성, 호환성 문제, 알려진 제한 사항을 기록한다.

## Screenshots

UI 변경이 있는 경우 전후 화면을 첨부한다.

## Related Issues

Closes #123
```

---

### 35. Public Repository Readiness 체크리스트

- README가 현재 기능과 일치하는가
- 프로젝트 목적이 README 첫 화면에서 명확한가
- 설치 및 실행 절차가 실제로 재현 가능한가
- 스크린샷, GIF, 배너가 현재 UI와 일치하는가
- 다운로드, Store, Releases 링크가 정상인가
- 지원 플랫폼과 최소 요구사항이 명시되어 있는가
- 라이선스가 명확한가
- 개인정보 처리 방식이 설명되어 있는가
- 알려진 제한 사항과 미구현 기능이 구분되어 있는가
- CONTRIBUTING 문서 또는 기여 방법이 제공되는가
- Issue Template과 Pull Request Template이 준비되어 있는가
- 보안 취약점 신고 방법이 필요한 프로젝트인지 검토했는가
- 저장소 설명, Topics, 홈페이지 URL이 최신 상태인가

#### Recommended Public Files

`README.md`, `LICENSE`, `CHANGELOG.md`, `CONTRIBUTING.md`, `SECURITY.md`, `CODE_OF_CONDUCT.md`, `.github/ISSUE_TEMPLATE/`, `.github/PULL_REQUEST_TEMPLATE.md` — 프로젝트 성격에 따라 불필요한 파일은 생략할 수 있지만, 생략 이유가 명확해야 합니다.

---

### 36. Release Completion 체크리스트

- 버전 번호가 모든 관련 파일에서 일치합니다.
- CHANGELOG를 사용자 관점에서 갱신했습니다.
- Release Notes를 작성했습니다.
- 태그가 올바른 커밋을 가리킵니다.
- GitHub Actions가 성공했습니다.
- APK, AAB, 설치 파일, 패키지 또는 배포 산출물이 실제로 생성되었습니다.
- 산출물의 파일명과 버전을 확인했습니다.
- 필요한 경우 파일 크기와 체크섬을 확인했습니다.
- README의 다운로드 및 설치 링크를 점검했습니다.
- 릴리스 후 주요 설치 경로를 최소 1회 검증했습니다.
- 알려진 제한 사항을 Release Notes에 기록했습니다.
- 롤백 또는 긴급 수정 절차가 필요한지 검토했습니다.

#### Release Notes Minimum Structure

`Highlights`(체감 핵심 변경) / `Added` / `Changed` / `Fixed` / `Known Issues`(알려진 문제·제한 사항) / `Installation`(설치·업데이트 방법)

---

### 37. Upstream Contribution 절차

- 프로젝트가 의존하는 오픈소스에서 재현 가능한 문제를 발견하면 기존 upstream Issue가 있는지 먼저 확인합니다.
- 로컬 우회 코드만 추가하기 전에 upstream 수정 가능성을 검토합니다.
- 외부 저장소에 기여할 때는 해당 저장소의 다음 문서를 우선합니다.
  - `AGENTS.md`
  - `CONTRIBUTING.md`
  - `CODE_OF_CONDUCT.md`
  - Issue 및 Pull Request 템플릿
- 외부 Pull Request는 다음 내용을 포함해야 합니다.
  - 재현 절차
  - 변경 이유
  - 변경 범위
  - 테스트 결과
  - 호환성 영향
- 단순 기여 수 증가를 목적으로 사소하거나 의미 없는 변경을 제출하지 않습니다.
- 외부 Pull Request 또는 코드 리뷰를 수행한 경우 관련 링크와 결과를 프로젝트 기록에 남깁니다.
