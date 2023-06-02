---
layout: post
title:  "Tomcat manager 페이지 충돌 오류"
date:   2023-06-02 11:09:33 +0900
categories: Code Java Spring tomcat
published: true
---
```
톰캣 실행시, manager 페이지 오류
- "The page you tried to access does not exist"
- manager 페이지 충돌 오류
```

# Manager 페이지 충돌 오류

![Tomcat_manager_page_error1](/assets/img/Code/Java/Spring/2023-06-02-tomcat_manager_page_error/Tomcat_manager_page_error1.jpg)

톰캣으로 스프링 프로젝트를 배포하고 잘 실행되어서 문제 없구나 생각했지만, (/manager) 페이지에 접근하니 위와 같은 에러가 발생했어요!

저는 관리자페이지를 (/manager)로 만들어놔서, 접속하려니 위와 같은 에러가 발생했습니다.

# 해결방법

톰캣의 manager를 쓰지 않아, "/Apache Software Foundation/Tomcat 8.5/webapps/manager" 폴더를 아예 삭제했습니다.

삭제하니, 정상적으로 작동하니 뿌듯하더라구요 ㅎㅎ

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 환영합니다~~ 감사합니다 :D