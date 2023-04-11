---
layout: post
title:  "Python 폴더 생성 os.mkdir() vs os.makedirs()"
date:   2023-04-11 21:00:33 +0900
categories: Tech Python
published: true
---
```
os.mkdir과 os.makedirs 차이
- os.mkdir()
- os.makedirs()
```

# os.mkdir()

- os.mkdir(path)
- mkdir은 folder 하나만 생성 가능합니다.

```python
import os

path = './workspace/test'
os.mkdir(path)
```
위의 경우, test 폴더만 생성됩니다.

- 'workspace'의 상위 폴더가 없을 경우, error가 뜹니다.
- folder 내의 folder 등은 생성 할 수 없습니다.

## os.mkdir() 이용해 여러 폴더 생성 방법

```python
import os

path_list = ['./workspace/test1', './workspace/test2', './workspace/test2']

for path in path_list:
    os.mkdir(path)
```
반복문을 이용해 os.mkdir()에 경로를 하나씩 불러와서 folder를 생성하는 방법입니다.

# os.makedirs()

- os.makedirs(path)
- makedirs는 './a/b/c' 처럼 원하는 만큼 folder(directory)를 생성 가능합니다.

```python
import os

path = './workspace/dir/test'
os.makedirs(path, exist_ok=True)
```

- 'exist_ok=True' parameter를 안넣을 경우, 지정한 경로에 folder가 이미 생성되어 있다면, error가 발생합니다.

- 'exist_ok=True' parameter를 넣어주면, 해당 경로에 folder가 존재해도 error 없이 작동합니다.

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 환영합니다~~ 감사합니다 :D