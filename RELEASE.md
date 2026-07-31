# RELEASE.md

이 파일은 `AGENTS.md` §18(CHANGELOG 작성 규칙), §19(릴리즈 노트 작성 규칙), §20(버전 관리 규칙), §23(릴리즈 및 배포 확인)에서 참조하는 세부 규칙입니다. 릴리스를 준비하거나 마무리할 때만 읽습니다.

릴리스를 마무리할 때 하드닝 후보를 이슈로 등록하는 절차는 코어 §20에 그대로 있고, 모바일 스토어 배포 세부는 `MOBILE-RELEASE.md`, 릴리스 완료 체크리스트는 `GITHUB-COLLAB.md`(§36)에 있습니다.

---

### 18. CHANGELOG 작성 세부

- 사용자에게 영향이 있는 모든 변경을 기록하며, 내부 구현 변경도 유지보수·안정성·성능·보안·배포에 영향이 있으면 기록합니다.
- 커밋 메시지를 그대로 복사하거나, 내부 파일명만 적고 사용자 영향도를 설명하지 않거나, "수정함"·"개선함"처럼 목적이 불명확한 표현만 쓰지 않습니다.
- 최신 버전이 상단에 오도록 역순으로 쓰고, 날짜와 버전을 명확히 적습니다.

권장 버전 형식은 `## vX.Y.Z - YYYY-MM-DD`이며, 섹션은 아래를 씁니다.

`Added` / `Changed` / `Fixed` / `Removed` / `Security` / `Performance` / `Documentation` / `Build / CI` / `Verification`(실제 실행한 테스트·빌드·CI·산출물 확인)

---

### 19. 릴리즈 노트 작성 세부

GitHub Release 본문, 스토어 등록용 릴리즈 노트, 앱 내 공지 문구가 분리되어 있으면 목적에 맞게 따로 작성합니다.

권장 형식은 `## vX.Y.Z - YYYY-MM-DD` 제목 아래 주요 변경 / 수정 / 문서·빌드·배포 / 검증(로컬·CI·산출물) / 설치·업데이트 참고 사항입니다.

별도 파일로 관리하는 프로젝트는 GitHub Release 본문을 `docs/releases/vX.Y.Z.md`에 두고, 파일명을 태그 이름과 정확히 일치시킵니다(접두사 `v` 포함).

모바일 앱 스토어 등록용 릴리즈 노트의 경로·형식·글자 수 제한·금지 표현은 `Mobile Release Document`(§1)를 따릅니다.

---

### 20. 버전 동기화와 태그 세부

버전 변경 시 함께 갱신할 위치의 예: `package.json`, `pubspec.yaml`, `build.gradle`, `AndroidManifest.xml`, `export_presets.cfg`, 앱 버전 상수, README 배지, `CHANGELOG.md`. 프로젝트의 실제 목록은 `Version Files`(§1)에 정의합니다.

버전 태그는 SemVer 형식 `vX.Y.Z`를 씁니다. 태그를 만들기 전에 앱 내부 버전·문서 버전·태그 버전이 일치하는지 확인하고, **태그는 반드시 버전 변경 커밋 이후에 생성합니다.** 태그가 이전 커밋을 가리키면 릴리즈 버전과 앱 내부 버전이 달라집니다.

모바일 앱의 버전 코드·이름 일치(Android versionName/versionCode, iOS CFBundleShortVersionString/CFBundleVersion), 스토어 업로드 산출물(AAB/IPA), 디버깅 심볼(mapping/symbols/dSYM) 보존 확인은 `Mobile Release Document`(§1)를 따릅니다.

---

### 23. 산출물 확인 체크리스트

릴리즈 또는 주요 기능 푸시 후 확인에 쓰는 명령:

```bash
gh run list --limit 10
gh run view <RUN_ID> --log-failed
gh release view vX.Y.Z
```

- **구동 파일 존재**: `Expected Assets`(§1)에 명시된 APK, AAB, EXE, MSI, DMG, ZIP 등 실행 가능한 산출물이 릴리즈 애셋에 업로드되었는지
- **산출물 유효성**: 파일 크기가 0이 아니고 예상 확장자를 가지는지
- **스토어 제출 파일**: Play Store 용 AAB, App Store 용 IPA, Windows/MSIX 등
- **디버깅 산출물**: R8/ProGuard mapping, native symbols, dSYM 등 crash 분석에 필요한 파일
- 릴리즈 노트가 최신 변경을 반영하는지, `CHANGELOG.md`와 모순되지 않는지
- 배포 페이지 또는 문서 사이트가 의도한 소스를 서빙하는지

모바일 배포의 스토어 등록정보 일치, 서명 키 관리, 광고 테스트 ID, 실기 검증 체크리스트는 `Mobile Release Document`(§1)를 따릅니다.
