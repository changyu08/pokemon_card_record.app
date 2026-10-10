# 포켓몬 카드 전적 일지 — Android APK 프로젝트

기존 모바일 최적화 HTML을 Android WebView 앱으로 감싼 프로젝트입니다. 앱 데이터는 WebView 내부의 브라우저 저장소에 저장됩니다.

## APK 빌드
이 실행 환경에는 Android SDK/Gradle 빌드 도구가 설치되어 있지 않아 APK 바이너리를 이 자리에서 직접 컴파일할 수 없습니다. 대신 GitHub Actions에서 APK를 자동으로 빌드하도록 설정했습니다.

1. 이 ZIP을 풀고 **전체 파일을 GitHub 저장소 최상위에 업로드**합니다.
2. 저장소의 `Actions` 탭을 열어 `Build Android APK` 워크플로를 선택합니다.
3. `Run workflow`를 누릅니다. `main` 또는 `master`에 push해도 자동 빌드됩니다.
4. 빌드가 끝나면 해당 실행 페이지 하단의 `Artifacts`에서 `pokemon-card-record-debug-apk`를 내려받습니다.
5. ZIP을 풀어 `app-debug.apk`를 Android 휴대전화로 옮긴 뒤 설치합니다. 알 수 없는 앱 설치 권한을 요구할 수 있습니다.

## 프로젝트 설정
- 앱 이름: 포켓몬 카드 전적 일지
- applicationId: `kr.co.ptcg.record` (debug 빌드에는 `.debug`가 추가됨)
- 최소 Android: Android 6.0 (API 23)
- target/compile SDK: 35
- 앱 화면: 기존 HTML 로컬 WebView
- 네트워크 권한: 선언하지 않음
- 빌드 결과: 테스트용 서명된 debug APK

## 데이터 관련 주의
- 기록은 앱 내부 WebView 저장소에 보관됩니다. 앱을 삭제하거나 앱 데이터를 지우면 기록이 사라질 수 있으므로 앱 내 JSON 백업 기능을 사용하세요.
- 이 빌드 설정은 디버그 APK를 만듭니다. 공개 배포용 정식 서명 APK/AAB가 필요하면 별도 서명 키 설정이 필요합니다.
- 기존 HTML에서 참조하던 일부 선택적 글꼴/포켓몬 스프라이트 원본 파일은 제공된 최신 프로젝트에 포함되어 있지 않아 일부 장식이 대체 표시될 수 있습니다.
