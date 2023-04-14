---
layout: post
title:  "깃허브 블로그 plainwhite 테마 검색바 안됨 (Simple-Jekyll-Search)"
date:   2023-04-14 09:30:33 +0900
categories: etc Blog_Dev
published: true
---
```
github blog Simple-Jekyll-Search
- plainwhite-jekyll theme 검색 기능 안됨
- search.json 파일 content 수정
```

# 문제 발생

plainwhite-jekyll 테마를 기본으로 깃허브 블로그를 운영하고 있는데요!

카테고리 기능을 추가해서 사용하던 중에, 검색을 하려고 했는데...

갑자기 검색에 "no result..."

카테고리를 커스텀화해서 추가한 탓인가 오만가지 생각이 났습니다.

# 문제 탐색 과정

- 저의 깃허브 블로그 테마인 **"plainwhite-jekyll"** 테마는 **"Simple-Jekyll-Search"** 를 사용하고 있었습니다.
- **관련 파일들** : [search.js, simple-jekyll-search.min.js, search.json]
- **참고 문서** : [Simple-Jekyll-Search](https://github.com/christian-fei/Simple-Jekyll-Search/blob/master/README.md)

## search.js 확인

- search.js파일을 확인해보니, json에 "/search.json"으로 되어 있었습니다.

![SimpleJekyllSearch1.png](/assets/img/etc/Blog_Dev/SimpleJekyllSearch_notworking/SimpleJekyllSearch1.png)

- 해당 주소를 깃허브 블로그(혹은 로컬에서 테스트)에서 확인해 봤습니다.
    - ex) "jbro321.github.io/search.json"
    - ex) "127.0.0.1:4000/search.json"

![SimpleJekyllSearch2.png](/assets/img/etc/Blog_Dev/SimpleJekyllSearch_notworking/SimpleJekyllSearch2.png)

- 정상적으로 json 형식으로 나오는 것을 확인했습니다.
- 해당 내용이 안나온다면, 기존 경로가 다를 수 있으니 확인해주세요!
    - baseurl을 수정한 경우 다를 수 있습니다.

# 문제 해결

search.json 파일에서 content를 post에서 page로 바꾸어주니 해결되었습니다!!

## search.json 파일 확인

### 수정 전

![SimpleJekyllSearch3](/assets/img/etc/Blog_Dev/SimpleJekyllSearch_notworking/SimpleJekyllSearch3.png)

- content에 "post.content"로 되어있습니다.

### 수정 후

![SimpleJekyllSearch4](/assets/img/etc/Blog_Dev/SimpleJekyllSearch_notworking/SimpleJekyllSearch4.png)

- content에서 "page.content"로 수정했습니다.

## 성공

블로그 post 파일을 어떻게 관리하느냐에 따라 다르겠지만, 저는 category별로 폴더를 나눠 post 글을 나눠 분리해서 관리해서 해당 내용이 검색이 안된 것 같습니다...

plainwhite-jekyll theme의 기본 설정은 "post"로 되어있어, 커스텀화하지 않고 사용하시고, "_posts" 폴더에 글을 작성하신다면, 제대로 작동될거라 생각됩니다!!

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 너무 환영합니다~~ 감사합니다 :D