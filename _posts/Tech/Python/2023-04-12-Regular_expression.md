---
layout: post
title:  "정규식(Regular Expression)"
date:   2023-04-12 19:38:33 +0900
categories: Tech Python
published: true
---
```
Regular expression
- 정규식
- 문자 일반화
```

# 정규식 표현

정규식 표현을 통해 일반화하여 데이터를 수집할 때 주로 사용합니다.

```python
// ex)path23-289976

pattern = "/(^[a-z]{4})(\d{2})-{0,1}(\d+)/gi"
```

-   ^ : 맨 앞에 '^'는 문자 혹은 줄의 시작을 의미한다.
-   \[a-z\]{4} : 영어 a-z 문자 4자리
-   \\d{2} : decimal(십진수) 숫자 2자리
-   \-{0,1} : '-'가 0개 혹은 1개
-   \\d+ : decimal(십진수) 숫자로 끝까지
-   () : 각각의 괄호는 한 덩어리로 묶는다. 캡처
-   g : 전역검색, 발생할 모든 pattern 검색
-   i : 대소문자 구분 안함


![Regular_expression.png](/assets/img/Tech/Python/Regular_expression/Regular_expression.png)

출처 : [Microsoft Regular Expression](https://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.pdf)

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 환영합니다~~ 감사합니다 :D