---
title: "내 컴퓨터 http 헤더 확인하고 요청시 헤더 전송하는 방법 파이썬 예시"
excerpt: "How to send my header and check my http header"
header:
  overlay_color: "#7515F2"
  overlay_filter: rgba(0, 0, 0, 0.5)
categories:
  - Web
tags:
  - 웹개발
---

아래 링크에 접속하면 HTTP 요청시 내가 포함하는 나의 HTTP 헤더 정보를 알 수 있다.

[나의 HTTP 헤더 확인하기](https://myhttpheader.com/)

그리고 http request 요청을 보낼 때 헤더를 포함하여 전송하는 방법 파이썬 예시는 아래와 같다.

```python
import requests

headers = {
        "User-Agent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/114.0.0.0 Safari/537.36",
        "Accept-Language": "en-US,en;q=0.9,ko;q=0.8"
}

response = requests.get(url="www.example.com", headers=headers)
response.raise_for_status()
print(response.text)
```
