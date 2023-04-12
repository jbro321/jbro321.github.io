---
layout: post
title:  "hasattr, getattr, setattr"
date:   2023-04-12 21:30:33 +0900
categories: Tech Python
published: true
---
```
object의 attribute(속성)
- hasattr, getattr
- setattr
```

# hasattr(object, name)

- object의 속성(attribute) 존재를 확인합니다.
- school에 apple이라는 멤버가 존재하면 True, 아니면 False로 출력됩니다.

```python
hasattr(school, 'apple')
>>> True
```

# getattr(object., name)

- object에서 name의 값 가져옵니다.
- school에서 apple변수의 값 가져옵니다.

```python
getattr(school, 'apple')
>>> 1
```

# setattr(object, name, value)

- object의 name이라는 변수에 값 value 설정합니다.
- school에서 apple이라는 변수에 값 5 설정합니다.

```python
setattr(school, 'apple', 5)
```

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 환영합니다~~ 감사합니다 :D