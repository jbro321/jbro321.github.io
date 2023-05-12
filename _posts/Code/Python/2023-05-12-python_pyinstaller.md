---
layout: post
title:  "Python exe 파일로 배포하는 방법 #pyinstaller #exe배포"
date:   2023-05-12 09:10:33 +0900
categories: Code Python
published: true
---
```
Python pyinstaller
- python exe파일
- pyinstaller --onefile 파일명.py
```

# pyInstaller 설치

pyInstaller는 python으로 작성한 코드를 exe로 배포하는 라이브러리입니다. pip로 라이브러리를 설치해봅니다.

```python
pip install pyInstaller
```

- 보통은 gui파일을 exe로 만들기 위해 사용합니다.
- 파이썬 GUI 프로그램은 thkinter, PyQt5 등이 있습니다.

# pyinstaller 실행

```python
pyinstaller -w -F test.py
```
- .exe 하나의 파일로 만드는 커맨드입니다.
    - -F 혹은 --onefile을 pyinstaller 뒤에 띄어쓰기로 붙여줍니다.
- 콘솔창 없는 실행파일로 만드는 커맨드입니다.
    - -w 혹은 --windowed 혹은 --noconsole

위와 같이 작성시, exe파일을 만드는 프로세스가 진행되고, 완료가 되면 현재 경로에서 dist폴더가 생기고, 그 안에 실행파일이 만들어집니다.

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 환영합니다~~ 감사합니다 :D