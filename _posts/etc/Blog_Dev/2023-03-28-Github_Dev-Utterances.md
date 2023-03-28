---
layout: post
title:  "github pages 블로그 댓글 기능 Utterances"
date:   2023-03-28 14:00:36 +0900
categories: etc Blog_Dev
---
```
깃허브 블로그 댓글 기능 추가
- Utterances
- Disqus 비추
```

# Utterances

깃허브 블로그 댓글 기능 추가를 위해 찾아보다가, Utterances가 가장 심플하고 간단하여 적용해보았습니다.

깃허브로 로그인하여, 댓글이 reopository의 issues로 올라오는 시스템입니다요!

* ### Disqus 비추
    * 다른 댓글 플랫폼 중에서 Disqus도 있지만, 초반에는 광고가 붙지 않다가, 사용하다보면 댓글 위 아래로 큼지막한 광고가 붙어요!!
    * 광고를 없애려면 한달에 약 9달러씩 지불해야 없어진다라요...ㅠㅠ, 저는 추천드리지 않습니다!!

## 1. Utterances를 설치합니다.

![Utterances_page](/assets/img/230328_Blog_Dev_Utterances/Utterances_page1.png)

https://github.com/apps/utterances 링크로 이동하여 utterances 깃허브 어플을 설치합니다.

1.1 오른쪽에 보시면, Configure를 누릅니다.

1.2 설치할 계정을 선택합니다.
- ex) jbro321

1.3 어떤 repository에 설치할지 선택합니다.
- 깃허브 블로그에 적용할거니, 해당 레포지토리 선택
- ex) jbro321.github.io

1.4 repo: 네모박스에 "계정/레포" 입력합니다.
- ex) jbro321/jbro321.github.io

![Utterances_page](/assets/img/230328_Blog_Dev_Utterances/Utterances_page2.png)

1.5 Issue에 적용되는 타입 선택합니다.
- 댓글 이슈를 어디에 매핑시킬지 선택합니다.
- ex) 저는 pathname 선택했습니다.

1.6 Theme 타입을 선택합니다.
- ex) 저는 깔끔한 "Github Light" 화이트 선택했습니다.
- 어두운 테마이면, "Phanton Dark" 도 이쁠 것 같아요 :)

1.7 Utterances 코드 copy

![Utterances_page](/assets/img/230328_Blog_Dev_Utterances/Utterances_page3.png)

## 2. Utterances 코드 적용하기

저는 "Plainwhite-jekyll"를 베이스 테마로 사용하고 있습니다.

- 적용한 Theme 마다 위치가 다를 수 있으니 참고해주세요!

2.1 Utterances 코드 적용하기

저는 포스트 맨 밑에 댓글 기능을 추가하였습니다.

- _layouts/default.html 에서
- class="post" {{ content }} 에서 글이 작성되고, div가 끝나는 곳 밑에 적용해주었습니다.

![Utterances_page](/assets/img/230328_Blog_Dev_Utterances/Utterances_code_apply.png)

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 너무 환영합니다~~ 감사합니다 :D