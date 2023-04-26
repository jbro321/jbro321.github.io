---
layout: post
title:  "Python으로 파일 확장자 변환 #pathlib.Path #stem #split"
date:   2023-04-26 11:00:33 +0900
categories: Code Python
published: true
---
```
파일 확장자 변경 방법
- Path 모듈
- splitext, split
```

# 파일 확장자 바꾸는 방법

파일 확장자를 Python 코드를 통해서 바꾸는 방법을 알려드릴려고 합니다.
1. `pathlib.Path().stem` 이용
2. `os.path.splitext` 이용
3. `split` 이용

## 0. 사전지식
### 전역변수 `__file__`
우선, python의 기본 설정인 __file__을 통해서 설정을 해보겠습니다.
- `Python` `__file__`은 수행중인 파일의 상대경로를 출력해주는 기본 설정 전역변수입니다.
- 추가내용은 아래 글을 참고해주세요 **☟**
[![python_filename_extension.png](/assets/img/Code/Python/2023-04-26-%08%08python_filename_extension/%08%08python_filename_extension1.png)](https://jbro321.github.io/code/python/2023/04/26/python_file_def.html)

    **☝︎ 그림 클릭 :)**

### `os.path.basename(__file__)`

- 현재 파일은 `test`폴더의 `test.py`파일입니다. (`test/test.py`)

```python
os.path.basename(__file__)
# 출력값
# >> test.py
```
- 위와 같이, basename은 해당 파일의 이름을 출력해줍니다.

## 1. `pathlib.Path().stem`이용

제가 제일 선호하는 방법으로 `pathlib`의 `Path` 모듈을 이용하는 방법입니다.
- `Pathlib.Path().stem`을 이용하면, 확장자명을 제외한 파일명이 출력됩니다.
- 그 후, 원하는 확장자명을 +로 붙이면 됩니다.
- 저는 '`test.py`'를 '`test.log`'로 log파일을 만들어 보겠습니다.

```python
import os
from pathlib import Path

print(os.path.basename(__file__))
# 출력값
# >> test

print(Path(os.path.basename(__file__)).stem)
# 출력값
# >> test

print(Path(os.path.basename(__file__)).stem + '.log')
# 출력값
# >> test.log
```

## 2. os.path.splitext() 이용

다음은 `os` 모듈의 `os.path.splitext()`를 이용하는 방법입니다.
- `os.path.splitext()`을 이용하면, 파일명과 확장자가 나뉘어 리스트로 출력됩니다.
- 그 후, 첫번째 인자만 가져오고, 원하는 확장자명을 +로 붙이면 됩니다.
- 저는 '`test.py`'를 '`test.log`'로 log파일을 만들어 보겠습니다.

```python
import os

print(os.path.basename(__file__))
# 출력값
# >> test

print(os.path.splitext(os.path.basename(__file__)))
# 출력값
# >> ['test', '.py']

print(os.path.splitext(os.path.basename(__file__))[0]+'.log')
# 출력값
# >> test.log
```

## 3. split() 이용

다음은 `python` 기본 함수로 `split()`을 이용하는 방법입니다.
- `split()`을 이용하면, 원하는 문자를 기준으로 분리해주는 함수입니다. `split('.')`을 통해서 `'.'`을 기준으로 분리하면 됩니다.
    - 주의할점은, 해당 파일명에 이미 '.'이 포함되어 있는 경우, 오류가 날 가능성이 높아 추천드리는 방법은 아닙니다.
    - ex) `test_22.01.01.py`의 경우, '.'으로 분리되는 부분이 많아 오류 발생
- 첫번째 인자만 가져오고, 원하는 확장자명을 +로 붙이면 됩니다.
- 저는 '`test.py`'를 '`test.log`'로 log파일을 만들어 보겠습니다.

```python
import os

print(os.path.basename(__file__))
# 출력값
# >> test

print(os.path.basename(__file__).split('.'))
# 출력값
# >> ['test', 'py']

print(os.path.basename(__file__).split('.')[0]+'.log')
# 출력값
# >> test.log
```

감사합니다.

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 환영합니다~~ 감사합니다 :D