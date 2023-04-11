---
layout: post
title:  "git commit 메세지 규칙"
date:   2023-04-11 10:08:33 +0900
categories: Tools Git
published: true
---
```
git commit message
- git commit message rules
- git commit message type
```

git commit message를 작성하는데, 매번 다르게 작성을 하다보니 통일화된 규칙이 없을까 하면서 찾아보았습니다.

# git commit message rules ( 7가지 규칙 )

1. 제목과 본문을 한 줄 띄어 분리합니다.
2. 제목은 영문 기준 50자 이내로 작성합니다.
3. 제목 첫 글자는 대문자로 작성합니다.
4. 제목 끝에 마침표를 넣지 않습니다.
5. 제목은 명령문으로 사용하며 과거형을 사용하지 않습니다.
6. 본문의 각 행은 72글자 내로 제한합니다.
7. 본문은 how보다 what, why에 맞춰 작성합니다.

## commit message 구조

Header : 필수
Body : 필수
Footer : 선택

```
// Header(필수)
<type>(<scope>): <subject>

// Body(필수)
<body>

// Footer(선택)
<footer>
```

# git commit message type

- feat : new feature 추가, 기존의 feature를 requirement에 맞춰 수정
- fix : feature에 대한 bug 수정
- docs : document(commnet) 수정
- comment : 필요한 comment 추가 및 변경
- style : code formatting, 세미콜론(;) 누락, 코드 변경이 없는 경우
- refactor : code refactoring
- test : test code, refactoring test code 추가(production code 변경 X)
- chore : build 업무 수정, package 매니저 수정(프로덕션 코드 변경 X)
- design : CSS 등 사용자 UI design 변경
- rename : file 혹은 folder name을 수정하거나 옮기는 작업만인 경우
- remove : file을 삭제하는 작업만 수행한 경우
- !BREAKING CHANGE : 커다란 API 변경한 경우
- !HOTFIX : 급하게 치명적인 BUG를 고쳐야 하는 경우

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 환영합니다~~ 감사합니다 :D