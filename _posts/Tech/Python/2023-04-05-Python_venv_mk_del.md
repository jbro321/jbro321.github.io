---
layout: post
title:  "Python 가상환경 생성, 삭제"
date:   2023-04-05 23:20:36 +0900
categories: Tech Python
---
```
Python 가상환경
- venv
- 충돌방지
```

# 가상환경 생성 (venv)

venv는 Python에 내장된 모듈입니다.

python 3.3 부터 별도 설치 없이 사용이 가능해졌어요!

예전에는 virtualenv라는 외부 패키지를 사용해서 가상 환경을 구성했었습니다.

### 가상환경을 사용하는 이유는?

-   패키지 관리의 목적!
-   계속 업데이트되는 패키지를 pip install 로 한곳에 받으면, 관리하기도 힘들고 "**충돌**"이 발생합니다!!

## 1. 가상환경을 생성하고 싶은 폴더로 이동합니다

```
// 폴더 이동
cd "download"
```

## 2. 가상환경 생성

```
python -m venv .venv
```

일반적으로 ".venv"의 가상환경의 이름으로 생성해서 사용한다.  
다른 이름으로 가상환경을 만들고 싶으면 바꿔도 된다.

## 3. 가상환경 활성화

```powershell
//PowerShell
.venv/Scripts/Activate.ps1
```

## 4. 가상환경 비활성화

```
deactivate
```

## 5. 가상환경 삭제

가상환경 해당 폴더 삭제

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 너무 환영합니다~~ 감사합니다 :D