---
title: "스위프트 Array 배열 자주쓰는 코드 모음"
excerpt: "스위프트 배열을 다루면서 자주 사용하게 되는 배열 요소 추가, 삽입, 삭제, 교체, 스왑, Array의 프로퍼티와 메서드, for loop 에서 사용법 등을 정리했다."
header:
    overlay_color: "#F66E2A"
    overlay_filter: rgba(0, 0, 0, 0.5)
categories:
- iOS
tags:
- Swift
- 모바일앱
---


```swift
// var myArr: Array<Int> = [1, 2, 3]
var myArr: [Int] = [1, 2, 3]

// 배열 마지막에 요소 추가
myArr.append(4) // [1, 2, 3, 4]
myArr.append(contentsOf: [5, 6]) // [1, 2, 3, 4, 5, 6]
myArr += [7, 8, 9] // [1, 2, 3, 4, 5, 6, 7, 8, 9]

// 원하는 인덱스의 요소 추가, 삭제
myArr.insert(0, at: 0) // [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
myArr.remove(at: 0) // [1, 2, 3, 4, 5, 6, 7, 8, 9]

// 교체
myArr[0] = 10 // [10, 2, 3, 4, 5, 6, 7, 8, 9]
myArr[1...4] = [11, 12, 13, 14] // [10, 11, 12, 13, 14, 6, 7, 8, 9]

// 스왑(바꾸기)
myArr.swapAt(0, 1) // [11, 10, ...]

// 일부를 제거한 배열을 반환
// myArr 변수 자체를 수정하지는 않는다.
let dropped1 = myArr.dropLast(3) // [11, 10, 12, 13, 14, 6]
let dropped2 = myArr.dropFirst(3) // [13, 14, 6, 7, 8, 9]
// myArr 는 그대로 [11, 10, 12, 13, 14, 6, 7, 8, 9]


// 자주 쓰는 배열의 프로퍼티와 메서드
myArr.count // 9
myArr.isEmpty // false

myArr.first // 11
myArr.last // 9

myArr.min() // 6
myArr.max() // 14

myArr.contains(11) // true
myArr.contains(100) // false


// for Loop 에서 배열의 인덱스와 요소 뽑아 쓰는 방법
for (index, element) in myArr.enumerated() {
    print("Index: \(index), element: \(element)")
}

```
