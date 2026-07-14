# MOBILE-RELEASE.md

이 파일은 `AGENTS.md` §19(릴리즈 노트 작성 규칙)·§20(버전 관리 규칙)·§23(릴리즈 및 배포 확인)에서 참조하는 모바일 앱스토어 배포 전용 세부 규칙입니다. 모바일 스토어 배포가 없는 프로젝트는 읽지 않아도 됩니다.

---

## Play Console용 릴리즈 노트 (§19 관련)

- 모바일 스토어 등록용 본문: `play_store/release_notes/vX.Y.Z.txt`
- 스토어 등록용 본문은 플랫폼 제한을 지킵니다. 예: Play Console 릴리즈 노트는 언어별 태그와 글자 수 제한을 확인합니다.

Android/Play Store 릴리즈에서 데스크톱 또는 `Build` 폴더로 내보내는 `*-release-notes.txt`는 GitHub Release 본문이나 `CHANGELOG.md` 전체가 아니라 **Play Console용 짧은 스토어 릴리즈 노트**여야 합니다.

Play Console용 릴리즈 노트의 대상 독자는 개발자가 아니라 일반 사용자입니다. 사용자가 업데이트 후 체감하는 안정성, 사용성, 개인정보 보호, 오류 수정, 화면 변화 중심으로 정제합니다.

Play Console용 TXT 기본 형식:

```text
<ko-KR>
vX.Y.Z 한 줄 요약

변경
• 사용자에게 보이는 변경 1
• 사용자에게 보이는 변경 2

개선
• 사용자에게 보이는 개선 1
• 사용자에게 보이는 개선 2
</ko-KR>
<en-US>
vX.Y.Z one-line summary

Changed
• User-facing change 1
• User-facing change 2

Improved
• User-facing improvement 1
• User-facing improvement 2
</en-US>
```

금지 사항:

- 데스크톱/`Build` 폴더용 `*-release-notes.txt`에 GitHub Release URL, 로컬 산출물 경로, CI 로그, manifest 검증 로그, `CHANGELOG.md` 전체 섹션을 붙이지 않습니다.
- GitHub Release 본문과 Play Console용 TXT를 같은 파일로 재사용하지 않습니다.
- Play Console용 TXT에 `CI`, `unit test`, `integration test`, `manifest`, `versionCode`, `BuildConfig`, 내부 클래스명, provider 제거, API fallback 제거처럼 개발자에게나 의미 있는 표현을 그대로 쓰지 않습니다. 필요하면 "안정성 개선", "앱 내부 처리 정리", "개인정보 보호 흐름 강화"처럼 사용자 관점으로 바꿉니다.
- 기존 프로젝트에 `play_store/release_notes/vX.Y.Z.txt`, `fastlane/metadata/android/*/changelogs/*.txt`, `docs/release-notes/*release-notes.txt`가 있으면 그 형식을 먼저 참고합니다.
- Play Console용 TXT를 내보낸 뒤에는 `<ko-KR>`와 `<en-US>` 각 블록의 태그 제외 본문 길이를 실제로 세고, 각 언어가 500자 이하인지 확인합니다. 하나라도 500자를 넘으면 내보내기 완료로 보고하지 않습니다.

---

## 버전 확인 체크리스트 (§20 관련)

모바일 앱에서는 아래 항목도 함께 확인합니다.

- Android `versionName` 또는 iOS `CFBundleShortVersionString`이 태그 버전과 일치하는지
- Android `versionCode` 또는 iOS `CFBundleVersion`이 이전 릴리즈보다 증가했는지
- 스토어 업로드용 AAB/IPA와 테스트 배포용 APK/기타 산출물이 같은 커밋에서 생성되었는지
- 난독화 또는 축소 빌드를 사용한다면 mapping, symbols, dSYM 같은 디버깅 산출물을 보존했는지

---

## 릴리즈 배포 확인 체크리스트 (§23 관련)

모바일 배포 프로젝트는 추가로 아래를 확인합니다.

- 스토어 등록정보의 앱 이름, 패키지명, 버전, 지원 언어, 광고 포함 여부가 실제 빌드와 일치하는지
- Play App Signing 또는 iOS signing을 사용하는 경우, 업로드 키와 최종 배포 서명 키의 차이를 문서화했는지
- 키스토어, 인증서, provisioning profile, API 키, 광고 ID, OAuth client ID 같은 민감 정보가 저장소에 커밋되지 않았는지
- 외부 SDK가 포함된 경우 필요한 스토어 정책 고지, 권한, 개인정보 처리방침, 테스트 계정, 콘솔 설정이 준비되었는지
- 광고는 실제 광고 ID로 셀프 테스트하지 않습니다. 개발/내부 테스트 단계에서는 공식 테스트 ID 또는 테스트 모드를 사용합니다.
- 실기 검증이 필요한 UI, 결제, 광고, 로그인, 리더보드, 푸시 알림은 에뮬레이터 또는 로컬 빌드만으로 완료 처리하지 않습니다.
- 헤드리스/CI 빌드가 네이티브 플러그인, AAR, entitlement, capability, asset pack 등을 누락할 수 있는 프로젝트는 산출물 내부 또는 실기 동작으로 포함 여부를 확인합니다.
