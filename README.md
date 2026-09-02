# Dot Coin Toss

픽셀 아케이드 스타일의 모바일 코인 토스 게임. Cordova 기반 하이브리드 앱.

## 자동 빌드
이 저장소는 GitHub Actions로 매 push 마다 Android APK를 자동 빌드합니다.

- 워크플로우: `.github/workflows/android-build.yml`
- 산출물: Actions 실행 결과의 **Artifacts** 항목 `DotCoinToss-debug-apk`
- 릴리스: `build-<번호>` 태그로 자동 릴리스에 첨부

빌드된 `app-debug.apk` 를 모바일에 설치하면 바로 실행됩니다 (Android 7.0 이상).

## 로컬 빌드
```
npm install
cordova platform add android@13
cordova build android --debug
```

## 프로젝트 구조
- `www/index.html` : 게임 본체 (단일 HTML, Web Audio, Canvas 2D)
- `config.xml` : Cordova 설정 (portrait, fullscreen)
- `.github/workflows/android-build.yml` : APK 자동 빌드

## 게임 요약
- 5x5 점수 보드 (홀 랜덤 1~3개)
- 코인 20개, 15초 턴, 스택 시 2배
- 15초 매치메이킹 후 봇 폴백
- 코인/보드/배경 각 10종 코스메틱
- Web Audio API 8-bit 효과음


## 현재 APK 빌드 동작
- 메인 로비에서 **랜덤 매치메이킹** 버튼을 누르면 현재 빌드에서는 즉시 BOT 퀵플레이로 진입합니다.
- 이유: 모바일 APK에서 가장 먼저 실제 플레이가 가능하도록 게임 진입을 우선 보장했습니다.
