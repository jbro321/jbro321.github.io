---
layout: post
title:  "Python 기본 설정 '__file__'이란?"
date:   2023-04-26 10:00:33 +0900
categories: Code Python
published: true
---
```
Python 기본설정 __file__
- 수행중인 파일 경로
- 상대경로
```

# Python에서 __file__의 의미

Python 코드를 보다보면 __file__이라고 적힌 부분이 있는데, 이는 Python 기본으로 설정되어 있는 전역변수입니다.

```
__file__은 수행중인 파일의 상대경로를 출력해줍니다.
```

## 예시로 해당 경로를 출력해봤습니다.
- 경로가 `test/test.py` 인 경우
    - test 폴더에서 `test.py` 를 실행시킨 경우
        ```python
        print(__file__)
        
        # 출력값
        # >> test.py
        ```
    - base 폴더에서 `test/test.py` 를 실행시킨 경우
        ```python
        print(__file__)

        # 출력값
        # >> test/test.py
        ```

        위와 같이 해당 폴더가 기준점이 되어, 실행시킨 파일의 파일명이 출력됩니다. 즉, 상대경로를 출력해주는걸 확인할 수 있습니다.

감사합니다.

p.s. __file__을 응용하여 os.path 모듈의 realpath, abspath, basename 등에 응용하여 사용됩니다.

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 환영합니다~~ 감사합니다 :D