---
layout: post
title:  "openslide의 원리 (deepzoom)"
date:   2023-04-12 21:12:33 +0900
categories: Code Python Openslide
published: true
---
```
Principle of openslide
- deepzoom
- 이미지 피라미드
```

# openslide

openslide는 deepzoom의 원리로 이미지 로드를 지원합니다.

## deepzoom

### deepzoom이란?

이미지를 타일 크기로 만들어 피라미드 형식으로 이미지를 확대 및 축소하는 원리입니다.
고해상도 이미지를 로드할 때, 원본 그대로 로드하려면 용량도 커지고, 속도도 느려집니다.

원본 이미지를 1/2, 1/4, 1/8 로 축소해 타일로 만들고 이미지를 확대할 때, 해당 부분의 이미지 타일만 로드해서 이미지를 보는 원리입니다.
이미지가 타일로 되어, 해당 타일만 불러오면 되어 이미지 크기가 작아 빠른 속도로 이미지를 불러 올 수 있는 원리입니다.

- Google Maps도 deepzoom의 원리로 되어 있습니다.

![python_openslide1.png](/assets/img/Code/Python/Openslide/2023-04-12-%08Principle_of_openslide/python_openslide1.png)

이미지 출처 : [large-image-display-with-seadragon-ajax](https://objectcomputing.com/resources/publications/sett/october-2011-large-image-display-with-seadragon-ajax)

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 환영합니다~~ 감사합니다 :D