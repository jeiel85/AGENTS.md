# HISTORY.md

## 2026-05-29
- 작업: Android/Play Store 릴리즈 TXT 내보내기 형식을 전역 규칙으로 고정
- 변경 파일:
  - AGENTS.md: 데스크톱 또는 `Build` 폴더용 `*-release-notes.txt`는 `<ko-KR>`/`<en-US>` 블록을 가진 짧은 Play Console용 노트로 작성하고, GitHub Release 본문/CHANGELOG 전체/CI 로그/산출물 경로를 섞지 않도록 규칙 추가. 각 언어 본문 500자 이하 실측 검증 규칙 추가
  - CHANGELOG.md: v0.1.4 변경 사항 추가
  - HISTORY.md: 작업 이력 기록
- 검증: `git diff`로 변경 내용 확인
- 결과: 성공
- 후속 작업: Android 릴리즈 작업 시 기존 프로젝트의 `play_store/release_notes`, `fastlane` changelog, 최근 `Build` 폴더 release-notes TXT를 먼저 참고

## 2026-05-29
- 작업: 사용자 제안과 수정 요청에 대한 비판적·객관적 판단 규칙을 공통 지침으로 추가
- 변경 파일:
  - AGENTS.md: 기본 커뮤니케이션 규칙에 자동 수용 금지, 사실과 근거 기반 판단, 반대 의견 및 대안 제시 원칙 추가
  - CHANGELOG.md: v0.1.3 변경 사항 추가
  - HISTORY.md: 작업 이력 기록
- 검증: `git diff`로 변경 내용 확인
- 결과: 성공
- 후속 작업: 각 프로젝트의 로컬 AGENTS.md에는 필요 시 공통 지침 동기화

## 2026-05-17
- 작업: `nightseed-survivor` 프로젝트의 모바일 배포 및 릴리즈 운영 규칙을 범용 규칙으로 반영
- 변경 파일:
  - AGENTS.md: AAB, 스토어 릴리즈 노트, 모바일 버전 동기화, 서명/외부 SDK/실기 검증 체크리스트 추가
  - CHANGELOG.md: v0.1.2 변경 사항 추가
  - HISTORY.md: 작업 이력 기록
- 검증: `git diff`로 변경 내용 확인
- 결과: 성공
- 후속 작업: 다른 모바일 프로젝트에 적용 시 프로젝트별 `Expected Assets`, 버전 파일, 스토어 노트 경로를 설정값에 맞게 조정

## 2026-05-13
- 작업: 소스 최신화 및 프로젝트 환경 점검
- 변경 파일:
  - AGENTS.md: 원격 저장소 변경 사항 반영 (git pull)
  - HISTORY.md: 이력 업데이트
- 검증: `git pull` 완료 및 파일 상태 확인
- 결과: 성공 (AGENTS.md 업데이트됨)
- 후속 작업: 사용자 요청에 따른 추가 작업 수행

## 2026-04-30
- 작업: 릴리즈 산출물 검증 규칙 강화 및 템플릿 업데이트
- 변경 파일:
  - AGENTS.md: 'Expected Assets' 설정 항목 추가 및 릴리즈 검증 체크리스트 구체화
- 검증: 파일 수정 확인
- 결과: 성공
- 후속 작업: 신규 규칙 적용 확인

## 2026-04-29
- 작업: 프로젝트 초기화 및 기본 문서 작성
- 변경 파일:
  - AGENTS.md: 범용 에이전트 규칙 작성 및 프로젝트 설정 업데이트
  - README.md: 프로젝트 소개 및 사용법 작성
  - HISTORY.md: 이력 관리 문서 생성
  - CHANGELOG.md: 변경 로그 문서 생성
- 검증: 로컬 파일 생성 확인
- 결과: 성공
- 후속 작업: GitHub 저장소 푸시 및 에이전트 연동 테스트
