---
layout: post
title:  "git github 연동"
date:   2023-04-11 18:40:33 +0900
categories: Tools Git
published: true
---
```
git & github config
- git bash
- git config username & email
```

# 1. Git Bash 실행

```
$ git config --global [user.name](http://user.name) "이름"
$ git config --global user.email "이메일"
```

# 2. Github repository 생성

github 홈페이지 로그인 후 > Repositories 접속 > New

![github_connect1](/assets/img/Tools/Git/2023-04-11-github_connect/github_connect1.png)

README.md 등 본인 선택에 따른 옵션 선택합니다.

![github_connect2](/assets/img/Tools/Git/2023-04-11-github_connect/github_connect2.png)

# 3. terminal 접속 및 연동

```
$ cd "연동하고 싶은 폴더" # 폴더 이동
$ git init
$ git add .
$ git commit -m "커밋 메시지"
$ git remote add origin " https 주소"
$ git push origin main
```

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 환영합니다~~ 감사합니다 :D