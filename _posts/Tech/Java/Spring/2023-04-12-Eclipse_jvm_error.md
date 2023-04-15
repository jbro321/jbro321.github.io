---
layout: post
title:  "[해결] 이클립스 jvm is not suitable for this product."
date:   2023-04-12 19:20:33 +0900
categories: Tech Java Spring
published: true
---
```
Eclipse jvm error
- jvm version 오류
- eclipse.ini 오류 : 가상머신 추가
```

# 이클립스 실행 오류

이클립스 실행시 오류가 발생합니다.

![Eclipse_jvm_error1.jpeg](/assets/img/Tech/Java/Spring/Eclipse_jvm_error/Eclipse_jvm_error1.jpeg)

**JVM 버전 1.8.0_281은 해당 이클립스에 적합하지 않습니다**

# 해결방법

이클립스가 설치된 폴더 안에 **eclipse.ini**를 열어서 수정

![Eclipse_jvm_error2.png](/assets/img/Tech/Java/Spring/Eclipse_jvm_error/Eclipse_jvm_error2.png)

**eclipse.ini** 파일을 보면, 버전이 다르게 설정되어 있습니다.

이 버전을 1.8 버전으로 변경해야 합니다.

```java
// 수정 전
Dosgi.requiredJavaVersion=11

// 수정 후
Dosgi.requiredJavaVersion=1.8
```

그리고 다시 이클립스 실행합니다.

![Eclipse_jvm_error3.png](/assets/img/Tech/Java/Spring/Eclipse_jvm_error/Eclipse_jvm_error3.png)

...

이클립스가 실행이 안됩니다..

# 또 다른 오류

이는 IDE를 실행해주는 가상머신이 없어서 발생하는 오류입니다.

이클립스는 자바로 구성되어 있습니다.

이클립스를 돌리는 가상머신이 없으면 이클립스가 실행이 안됩니다.

**eclipse.ini**에 이클립스를 실행하는 가상머신의 경로를 설정하면 됩니다.

```
// -vm 밑에 가상머신 경로를 입력 
-vm
C\Program Files\Java\jdk-15.0.2\bin\javaw.exe
```

본인의 jdk가 설치되어 있는 경로를 **eclipse.ini**의 맨 위에 추가하면 됩니다.

**성공**

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 환영합니다~~ 감사합니다 :D