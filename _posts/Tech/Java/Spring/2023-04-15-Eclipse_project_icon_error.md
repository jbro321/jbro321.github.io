---
layout: post
title:  "Eclipse project icon 오류"
date:   2023-04-15 16:53:33 +0900
categories: Tech Java Spring
published: true
---
```
Eclipse project icon error
- Java Build Path에 Maven Dependencies 오류
- Target runtime Apache Tomcat v8.0 is not defined 오류
```

# Eclipse project icon 오류

![Eclipse_project_icon_error1](/assets/img/Tech/Java/Spring/Eclipse_project_icon_error/Eclipse_project_icon_error1.png)

- 위 아이콘이 나올 시, 프로젝트에 오류가 있다는 것입니다.
- 위 아이콘이 나와도 프로젝트 실행은 될 수 있습니다.

## Problems를 확인
    
![Eclipse_project_icon_error2](/assets/img/Tech/Java/Spring/Eclipse_project_icon_error/Eclipse_project_icon_error2.png)

### 1. Java Build Path에 Maven Dependencies가 없을시
- 프로젝트 오른쪽 클릭 > Maven > Update Project > 업데이트할 프로젝트 선택합니다.
    
### 2. Target runtime Apache Tomcat v8.0 is not defined 오류가 발생시
- problems > Description > 해당 problem에서 오른쪽 클릭 > Quick Fix

- Create a new runtime environment > 사용중인 Tomcat 선택합니다.

- 해당 프로젝트 오른쪽 클릭 > properties > Project Facets에서, 오른쪽에 Runtime > Tomcat 선택합니다.

    ![Eclipse_project_icon_error3](/assets/img/Tech/Java/Spring/Eclipse_project_icon_error/Eclipse_project_icon_error3.png)

## 성공

- 'x' 표시가 사라진 것을 볼 수 있습니다.
    ![Eclipse_project_icon_error4](/assets/img/Tech/Java/Spring/Eclipse_project_icon_error/Eclipse_project_icon_error4.png)

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 환영합니다~~ 감사합니다 :D