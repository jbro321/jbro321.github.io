---
layout: post
title:  "git 명령어 모음"
date:   2023-04-08 11:11:33 +0900
categories: Tools Git
published: true
---
```
git commands
- github 레포지토리 가져오기
- github repository에 저장하기 
```

github에 생성된 "practice" 이름의 레포지토리(repository)로 진행해보겠습니다.

# git clone

- github의 practice 레포지토리 소스 코드 복제 및 다운로드하는 명령어입니다.
```bash
$ git clone https://github.com/jbro321/practice.git
```

# git add

- practice.py 파일을 stage 상태로 만듭니다.
```bash
$ git add practice.py
```
> - **Stage란?** 수정 및 생성한 파일을 깃허브에 올리기 전 단계라고 보시면 됩니다. 이 파일들을 올릴거다하는 확인단계입니다.


- practice repository의 변경사항이 있는 파일을 모두 stage 상태로 만드는 명령어입니다. (add 뒤에 띄어쓰기해야됩니다. 주의해주세요.)
```bash
$ git add .
```

- stage한 파일들 전부를 unstage하는 명령어입니다.
```bash
$ git reset HEAD --
```

- stage한 "practice.py" 파일을 unstage하는 명령어입니다.
```bash
$ git reset HEAD practice.py
```

# git commit -m "commit message"

- "1st commit"이라는 메세지로 commit합니다. Stage한 파일을 github에 올리기 직전 단계입니다. (push 되기 전 단계)
```bash
git commit -m "1st commit"
```

# git push

- github에 연결된 main이라는 branch로 commit된 변경사항들을 업로드합니다.
```bash
$ git push origin main
```

## branch에 push
- "test" branch에 push
```bash
$ git push --set-upstream origin test
```

## git branch 복사

- main에서 "test" branch로 브랜치 복사합니다.
```bash
$ git push origin main:test
```

# git pull

- github의 변경 내용을 현재 내 directory로 가져오고(fetch) 병합(merge)합니다.
```bash
$ git pull
```

# git remote

- git remote를 통해서 기존 폴더를 github에 연결합니다.

1. git 초기화합니다.
```bash
$ git init
```

2. git 파일을 stage합니다
```bash
$ git add .
```

3. stage한 파일을 "1st commit" 이라는 메세지로 commit합니다.
```bash
$ git commit -m "1st commit"
```

4. github_url에 등록합니다.
```bash
$ git remote add origin [github_url.git]
```

5. github의 main 브랜치에 업로드합니다.
```bash
$ git push -u origin main
```

# git branch

- github에 branch 현황을 보여줍니다.
```bash
$ git branch
```

- github에 "new_branch"이라는 이름으로 branch를 만듭니다.
```bash
$ git branch "new_branch"
```

- "new_branch"로 이동합니다.
```bash
$ git checkout new_branch
```

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 환영합니다~~ 감사합니다 :D