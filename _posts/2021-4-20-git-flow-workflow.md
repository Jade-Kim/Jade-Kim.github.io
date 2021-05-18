---
title: "깃플로우 git flow 를 활용한 개발 과정 워크플로우 순서"
excerpt: "GIT의 프레임워크 중에 하나인 git flow 를 활용하여 형상 관리하는 개발 과정 워크플로우 순서를 정리해보았다."
header:
  overlay_color: "#7515F2"
  overlay_filter: rgba(0, 0, 0, 0.5)
categories:
- Web
tags:
- 웹개발
- 프론트엔드
- Git
---


## 일반적인 git flow 기능 개발 및 릴리즈 워크플로우

1. 기능 개발 시작
`git flow feature start 기능이름`

2. 기능 개발이 끝나면
`git flow feature finish 기능이름`

3. 릴리즈 준비
`git flow release start 릴리즈버전`

4. 앱 버전 수정하기
	* iOS 는 Xcode 에서 버전 수정 및 빌드 넘버 수정
	* Android 의 `build.gradle` 파일에 앱 버전코드와 앱 버전 수정
	* 앱 정보의 버전 수정

5. 테스트 빌드 발행
`npm run build`

앱을 출시 또는 패치하기 전에 내부적으로 발행하는 dev 빌드

6. 디버깅
	- 필요시 4번~5번 계속 반복

7. 릴리즈 빌드 발행
`npm run build-adr`
`npm run build-ios`

8. 구글플레이스토어 및 앱스토어에 앱 업로드 진행

9. 릴리즈 마치기
`git flow release finish 릴리즈버전 `

10. master 브랜치에 merge 하고 Tag `v_릴리즈버전` 달기
11. 다시 1번부터 개발 시작하기

---

## 갑작스런 핫픽스 hot fix 워크플로우

1. 핫픽스 브랜치 시작
`git flow hotfix start 릴리즈버전`

2. 앱 버전 수정하기
	* iOS 는 Xcode 에서 버전 수정 및 빌드 넘버 수정
	* Android 의 `build.gradle` 파일에 앱 버전코드와 앱 버전 수정
	* 앱 정보의 버전 수정

3. 테스트 빌드 발행
`npm run build`

4. 디버깅
5. 릴리즈 빌드 발행
`npm run build-adr`
`npm run build-ios`

6. 구글플레이스토어 및 앱스토어에 앱 업로드 진행

7. 핫픽스 브랜치 마치기
`git flow hotfix finish 릴리즈버전`

8. master 브랜치에 merge 하고 Tag `v_릴리즈버전` 달기
