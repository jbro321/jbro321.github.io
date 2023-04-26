---
layout: post
title:  "Python 경로에 파일, 폴더 있는지 확인 #isdir() #isfile()"
date:   2023-04-26 15:00:33 +0900
categories: Code Python
published: true
---
```
경로에 파일 혹은 디렉토리가 존재하는지 확인
- os.path.isdir()
- os.path.isfile()
```

# os.path.isdir()
- 해당 경로에 디렉토리가 존재하는지 확인하는 명령어입니다.
- 출력값은 `True` or `False` 입니다.
- 경로(디렉토리)만 확인이 가능하고, 파일은 확인이 불가능합니다.
- 주의할 점은, `'~/'` 와 같이 Home경로를 나타내주는 경로는 사용이 불가능합니다.

`test/test.py` 의 예시로 진행해보겠습니다.
```python
import os

os.path.isdir('test')
# 출력값
# >> True

os.path.isdir('test.py')
# 출력값
# >> False
```

# os.path.isfile()

- 해당 파일이 존재하는지 확인하는 명령어입니다.
- 출력값은 `True` or `False` 입니다.
- 파일만 확인이 가능하고, 경로(디렉토리)는 확인이 불가능합니다.

`test/test.py` 의 예시로 진행해보겠습니다.
```python
import os

os.path.isfile('test.py')
# 출력값
# >> True

os.path.isfile('test')
# 출력값
# >> False
```

감사합니다.

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 환영합니다~~ 감사합니다 :D