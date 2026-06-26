# CHANGELOG.md

## v0.2.0 - 2026-06-26

### Added
- GitHub 협업 및 공개 저장소 운영 방침을 `AGENTS.md` 공통 규칙으로 통합 (§30–§41)
  - Pull Request First, 의미 있는 변경 단위, Issue 기반 개발
  - 독립 리뷰, Pull Request 본문 품질 형식, 공개 저장소 완성도 점검
  - 릴리스 완료 기준, Upstream 기여 규칙
  - GitHub 지표 무결성 규칙 (통계·등급·기여 그래프를 개발 목표로 삼지 않음)
  - 자동화 규칙, 작업 완료 기준, 에이전트 의사결정 우선순위

### Changed
- §2 Automation First와 §21 커밋·푸시·배포 규칙에 Pull Request First 원칙을 반영하여, GitHub로 추적·공유·공개되는 변경은 작업 브랜치와 PR로 반영하고 `main` 직접 커밋은 예외로 한정하도록 명확화
- §22 브랜치/PR 규칙에 상세 PR 본문 형식(§34) 우선 적용 및 §30 Branch Naming 규칙 연결 명시

## v0.1.4 - 2026-05-29

### Changed
- Android/Play Store 릴리즈에서 데스크톱 또는 `Build` 폴더로 내보내는 `*-release-notes.txt`는 Play Console용 짧은 다국어 노트 형식으로 작성하도록 명시
- GitHub Release 본문, `CHANGELOG.md` 전체 섹션, CI 로그, 산출물 경로를 Play Console용 TXT에 섞지 않도록 금지 규칙 추가
- Play Console용 TXT의 `<ko-KR>`, `<en-US>` 각 본문을 실제로 세어 500자 이하인지 확인하는 규칙 추가
- Play Console 릴리즈 노트는 개발자 대상 설명이 아니라 일반 사용자가 체감하는 변화 중심으로 정제하도록 명시

## v0.1.3 - 2026-05-29

### Changed
- 사용자 제안과 수정 요청을 자동으로 수용하지 않고, 사실과 근거, 보편적 상식, 프로젝트 목표에 따라 객관적으로 판단하도록 커뮤니케이션 규칙을 강화

## v0.1.2 - 2026-05-17

### Added
- 모바일 배포 프로젝트를 위한 AAB, 스토어 업로드 산출물, mapping/symbols/dSYM 확인 규칙 추가
- GitHub Release 본문과 모바일 스토어용 릴리즈 노트를 분리해 관리하는 규칙 추가
- Android/iOS 버전명과 빌드 번호를 태그 및 문서 버전과 함께 확인하는 규칙 추가
- 외부 SDK, 광고, Play Games Services, 서명 키, 실기 검증 관련 배포 체크리스트 보강

## v0.1.1 - 2026-04-30

### Added
- `AGENTS.md` 프로젝트 설정값에 `Expected Assets` 항목 추가
- 릴리즈 시 APK, EXE 등 실제 구동 파일의 생성 및 유효성 확인 규칙 강화 (Section 23)

## v0.1.0 - 2026-04-29

### Added
- AI 코딩 에이전트를 위한 범용 작업 규칙 `AGENTS.md` 추가
- 프로젝트 개요 및 가이드를 담은 `README.md` 추가
- 이력 관리를 위한 `HISTORY.md` 및 `CHANGELOG.md` 구조화

### Documentation
- `AGENTS.md` 프로젝트 설정값 업데이트 (Repository URL 등)
