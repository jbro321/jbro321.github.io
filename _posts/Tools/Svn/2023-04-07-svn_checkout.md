---
layout: post
title:  "Svn checkout(가져오기)"
date:   2023-04-07 14:15:33 +0900
categories: Tools Svn
published: true
---
```
Svn Checkout(가져오기)
- Svn (형상관리툴)
- Checkout(가져오기)
```

# Svn (형상관리툴)

Svn(Subversion)은 버전, 소스관리 등 형상관리하는 툴입니다.
-   작업 이력 관리
-   문제 파악
-   이전 버전 파일 복원
-   수정한 부분 검증
-   협업

형상관리툴로 가장 유명한 2가지 툴이 있습니다.
- Svn
- git

요즘은 git을 많이 사용하는데, 오래전에 Svn을 많이 사용했었습니다.

## SVN 설치

[https://tortoisesvn.net/downloads.html](https://tortoisesvn.net/downloads.html)

본인 환경에 맞는 os와 버전을 선택합니다.

ex) Windows 64비트이면, Tortoise 1.14.5 - 64 bit 선택 > 자동으로 다운로드 진행된다.

![Svn_user](/assets/img/Tools/Svn/Checkout/Svn_user.png)

# SVN Checkout

## SVN을 통해서 폴더 및 파일을 Checkout(가져오기)

```
가져올 폴더로 이동 후 > 오른쪽 클릭
```

![Svn_Checkout1](/assets/img/Tools/Svn/Checkout/Svn_Checkout1.png)

## 가져올 폴더의 url을 입력

![Svn_Checkout2](/assets/img/Tools/Svn/Checkout/Svn_Checkout2.png)

- **URL of repository**
    - Svn에서 가져올 경로를 입력해줍니다.
    - ex) "192.168.0.123:1111/svn/practice/practice"

- **Checkout directory**
    - PC에 저장할 경로를 입력해줍니다.
    - ex) "D:\workspace\practice"

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 환영합니다~~ 감사합니다 :D