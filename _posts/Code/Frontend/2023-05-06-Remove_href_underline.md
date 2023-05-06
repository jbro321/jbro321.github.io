---
layout: post
title:  "HTML 하이퍼링크 밑줄 없애기 #href #underline"
date:   2023-05-06 18:30:33 +0900
categories: Frontend HTML CSS
published: true
---
```
HTML 하이퍼링크 밑줄 없애기
- href=""
- style="text-decoration-line:none"
```

# HTML에서 href 밑줄 없애기

하이퍼링크를 설정하면, 디폴트로 밑줄이 그어져 나옵니다.
- 따라서, "text-decoration-line: none"을 설정해주면 밑줄없이 나옵니다.

1번과 2번 중에 해당되는 설정에 맞게 설정해주면 됩니다.

## 1. html에 style태그 추가

```html
<a style="text-decoration-line: none;"></a>
```
## 2. css파일로 추가

```css
a {
    text-decoration-line: none;
}
```

아래는 text-decoration-line 옵션들입니다.

- none : 선 없음
- underline : 밑줄
- overline : 윗줄
- line-through : 취소선

p.s. "text-decoration: none" 으로도 밑줄을 없앨 수 있습니다.

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 환영합니다~~ 감사합니다 :D