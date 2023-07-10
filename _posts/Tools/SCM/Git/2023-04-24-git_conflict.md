---
layout: post
title:  "git conflict(충돌) 났을 때 강제로 pull 하기"
date:   2023-04-24 11:22:33 +0900
categories: Tools SCM Git
published: true
---
```
git conflict(충돌) - 강제 pull
- git fetch
- git reset 
```

# git conflict

수정한 파일들이 깃허브와 로컬 깃 등 충돌 났을 때 해결방법입니다.

```bash
$ git fetch --all
$ git reset --hard origin/main
$ git pull origin main
```

## 한 줄씩 풀어보면

수정한 파일이 충돌나면, fetch로 파일들을 remote 저장소에서 이전 fetch들을 받습니다.
```bash
$ git fetch --all
```

그 다음, local에서 다시 reset hard를 사용하여 제 상태를 충돌나기 전, 수정하기 전으로 되돌립니다.
```bash
$ git reset --hard origin/main
```

그 후, main 브랜치로 pull 합니다.
```bash
$ git pull origin main
```

감사합니다.

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 환영합니다~~ 감사합니다 :D