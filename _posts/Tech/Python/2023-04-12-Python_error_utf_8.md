---
layout: post
title:  "Python Error : non-utf-8 code starting with ' xc6'"
date:   2023-04-12 21:25:33 +0900
categories: Tech Python
published: true
---
```
Python Error
- Non-UTF-8 code error
- pep-0263
```

# 에러 발생

```
SyntaxError: Non-UTF-8 code starting with '\xed' in file <FilePath> but no encoding declared; see http://python.org/dev/peps/pep-0263/ for details
```

-   Python 실행시 작업 중 SyntaxError 발생
-   한글 인코딩 문제가 발생

# 에러 해결

-   코드 맨 윗줄에 "# -_- coding: utf-8 -_-" 삽입

```python
# -*- coding: utf-8 -*-
# 라이브러리 import
import pymysql
import os, json
import glob
import shutil as sh

... <이하 생략>
```

# Reference

- [Python pep-0263](https://peps.python.org/pep-0263/)

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 환영합니다~~ 감사합니다 :D