---
layout: post
title:  "Python 경로 합치기 #os.path.join() #장점"
date:   2023-04-26 13:00:33 +0900
categories: Code Python
published: true
---
```
파일 경로 합치는 방법
- os.path.join() 사용하는 이유, 장점
- +로 합치기
```

# 파일 경로 합치는 방법

파일 디렉토리(경로)를 합치는 방법에는 여러가지 방법이 있습니다.

그 중에서, os.path.join()을 이용하여 합치는 방법을 말씀드리겠습니다.

수동으로 +로 합치는 방법은 구분자를 지정해서 입력해줘야하므로, 운영체제가 바뀌면 해당 경로 에러가 날 수 있습니다.


## `os.path.join()` 사용하는 이유, 장점

```
os.path.join() 의 장점은 운영체제에 맞게 폴더 구분자를 다뤄서 경로를 생성해줍니다.
```

- os.path.join(경로1, 중간경로1, 중간경로2, 파일)
    - 위와 같이 경로1 중간에 중간경로를 추가해도 같이 합쳐집니다.
- test경로와 test.py를 합쳐보겠습니다.

```python
import os

print(os.path.join('test', 'test.py'))
# 출력값
# test/test.py

print(os.path.join('test', 'aaa', 'bbb', 'test.py'))
# 출력값
# test/aaa/bbb/test.py
```
## `+`로 합치기

+로 수동으로 경로들을 합칠 수 있습니다. 하지만, 중간에 `'/'`와 같이 경로 구분자를 붙여줘야합니다.

이러한 경로 구분자는 운영체제에 따라 달라, 수동으로 구분자를 입력할 경우 에러가 날 가능성이 높습니다.
- ex) 윈도우, 리눅스 등

```python
print('test' + '/test.py')
# 출력값
# test/test.py

print('test' + '/aaa' + '/bbb' + '/test.py')
# 출력값
# test/aaa/bbb/test.py
```


감사합니다.

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 환영합니다~~ 감사합니다 :D