---
title: "python pandas read_csv unicode decode error"
excerpt: "판다스에서 read_csv 유니코드 디코드 에러 해결 방법  UnicodeDecodeError: 'utf-8' codec can't decode byte 0xc7 in position 0: invalid continuation byte"
header:
  overlay_color: "#4B8BBE"
  overlay_filter: rgba(0, 0, 0, 0.5)
categories:
  - Python
tags:
  - 문제 해결
  - Data Analysis
---

파이썬 판다스에서 자료가 한글로 된 csv 파일을 불러오고자 할 때 유니코드 에러 문제로 파일을 불러오지 못하는 경우가 있다.

```python
import pandas as pd
file = "file_path.csv"
data = pd.read_csv(file)
```

에러 내용은 아래와 같다.

`UnicodeDecodeError: 'utf-8' codec can't decode byte 0xc7 in position 0: invalid continuation byte`

이 문제를 해결하기 위해 우선 파일이 어떤 형식으로 인코딩 되었는지 확인 해본다.

```python
import chardet

with open(file, 'rb') as rawdata:
    result = chardet.detect(rawdata.read(100000))

print(result)
```

위 코드를 실행하면 해당 파일의 인코딩 타입을 알 수 있다.

`{‘encoding’: ‘EUC-KR’, ‘confidence’: 0.99, ‘language’: ‘Korean’}`

인코딩이 `‘EUC-KR’` 로 되어 있습니다. 이제 `pandas.read_csv()` 를 할 때 이 인코딩 정보를 넣어주면 문제없이 파일을 불러들일 수 있다.

```python
import pandas as pd
file = "file_path.csv"
data = pd.read_csv(file, encoding='EUC-KR')
data.head()
```
