---
title: "스위프트 inout 키워드"
excerpt: "스위프트 Swift 함수 파라미터에 사용되는 inout 키워드와 스위프트의 copy-in, copy-out에 대해 알아보자."
header:
    overlay_color: "#F66E2A"
    overlay_filter: rgba(0, 0, 0, 0.5)
categories:
- iOS
tags:
- Swift
- 모바일앱
---

: 함수 파라미터에 들어온 변수를 복사본이 아닌 원본을 직접 넣어, 파라미터 원본을 수정 가능하도록 해주는 키워드 (즉, 스위프트의 기본적인 copy-in, copy-out 을 무시하는 키워드)

### 스위프트의 copy-in, copy-out 이란?
: 기본적으로 함수의 파라미터는 함수내에 복사되어 들어오고(copy-in) 복사본을 내보낸다(copy-out). 파라미터는 `let` 상수로 취급되기 때문에 변경이 불가능하다. 즉, 함수의 파라미터로 변경 가능한 변수를 넘겨줘도 함수 내에서는 상수 취급되어 수정이 안되는 것이다. 함수의 파라미터 값을 변경 가능하도록 해주는 키워드가 inout 키워드이다.

아래 예시에서 abc 는 var 변수이다. plusOne 함수를 정의할 때 파라미터로 변수 abc 를 받아 abc 값을 직접 변경 시키려고 한다면 `abc: inout Int` 처럼 inout 키워드를 명시해줘야 한다.

만약 inout 키워드를 추가하지 않는다면 Xcode 에서 파라미터 ‘abc’는 상수이기 때문에 변경할 수 없다는 에러 메세지를 띄운다.
`Left side of mutating operator isn't mutable: 'abc' is a 'let' constant`

함수를 호출할 때는 파라미터 앞에 &를 붙인다. `plusOne(&abc)`

```swift
var abc = 1
func plusOne(_ abc: inout Int) {
    abc += 1
}

// 함수를 호출할 때 파라미터 앞에 &를 붙인다.
plusOne(&abc)
print(abc) // 2
```
