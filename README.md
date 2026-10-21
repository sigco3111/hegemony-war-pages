# 패권의 시간 — 배포 저장소

「패권의 시간」을 GitHub Pages에 올리는 **배포 전용 저장소**입니다. 게임 소스 코드는 여기에 없습니다.

- **플레이:** https://sigco3111.github.io/hegemony-war-pages/
- **소스 저장소:** https://github.com/sigco3111/hegemony-war

## 역할

원작(OpenFrontIO) 포크 저장소에는 GitHub Pages를 켤 수 없어서(포크 정책), 배포만 담당하는 저장소를 분리했습니다.

이 저장소의 `.github/workflows/` 안 워크플로를 수동 실행(workflow_dispatch)하면:

1. 소스 저장소 `sigco3111/hegemony-war`의 main을 체크아웃하고,
2. 정적 싱글플레이 클라이언트를 빌드합니다(`PAGES_BASE=/hegemony-war-pages/`, `CDN_BASE=/hegemony-war-pages`, `GAME_ENV=prod`, `DOMAIN=sigco3111.github.io`로 `npx vite build --mode static`),
3. 빌드 결과물(`game/static`)을 GitHub Pages에 배포합니다.

## 배포 방법

1. 소스 저장소에 변경이 반영되었는지 확인합니다.
2. 이 저장소의 **Actions → build-and-deploy-pages → Run workflow**를 실행합니다.
3. 몇 분 뒤 https://sigco3111.github.io/hegemony-war-pages/ 에 반영됩니다. GitHub Pages가 index.html을 약 10분 캐시하므로, 바로 확인할 때는 `?v=임의숫자` 쿼리를 붙여 새로고침합니다.

## 개발·버그 제보

게임 개발과 이슈는 소스 저장소 [sigco3111/hegemony-war](https://github.com/sigco3111/hegemony-war)에서 다룹니다. 게임 설계와 개선 내역은 소스 저장소의 [docs/DESIGN.md](https://github.com/sigco3111/hegemony-war/blob/main/docs/DESIGN.md)와 README에 정리되어 있습니다.

## 라이선스

원작 [OpenFrontIO](https://github.com/openfrontio/OpenFrontIO)의 AGPLv3을 따르며 "© OpenFront and Contributors" 저작자 표시를 유지합니다. 원작 에셋은 CC BY-SA 4.0입니다.
