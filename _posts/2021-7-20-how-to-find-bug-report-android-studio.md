---
title: "안드로이드 스튜디오 버그 리포트 확인 방법"
excerpt: ""
header:
    overlay_color: "#15F215"
    overlay_filter: rgba(0, 0, 0, 0.5)
categories:
- Android
tags:
- 안드로이드 스튜디오
- 모바일앱
---

안드로이드 스튜디오에서 릴리즈 빌드시 다음과 같은  lintVitalRelease 에러가 발생했다.

```
Execution failed for task ':app:lintVitalRelease'.
> Lint found fatal errors while assembling a release target.
```

버그 리포트는 android > app > build > reports 폴더에서 확인할 수 있다.

`lint-results-release-fatal.xml `

버그 리포트 파일을 확인해보니 notification.png 파일의 default 폴더로 지정된 drawable 폴더의 위치나 연결 등이 문제인 것 같았다.

android > app > src > main > res > drawable 폴더에 notification.png 파일을 추가하여 문제 해결했다.
