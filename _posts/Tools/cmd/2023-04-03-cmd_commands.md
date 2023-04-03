---
layout: post
title:  "Cmd commands로 hosts파일 수정 커맨드(echo)"
date:   2023-04-03 10:15:36 +0900
categories: etc Blog_Dev
---
```
Cmd 명령 프롬프트 명령어
- echo(프린트)
- hosts파일 수정 명령어
```

# echo

echo는 커맨드 명령 프롬프트에서 프린트 역할을 합니다.
- echo를 통해서 메모장(notepad)에 글을 써보겠습니다.
- 저는 hosts 파일을 수정할 일이 자주 있어 hosts파일을 메모장으로 열어서 입력하고 싶은 내용을 추가해보겠습니다.


## 1. 관리자 권한 cmd 실행
- 실행(윈도우+R)에서 cmd 입력 후, Ctrl+Shift+Enter : 관리자 권한으로 실행

```powershell
echo.192.168.0.90 demo>> %SystemRoot%\system32\drivers\etc\hosts
```

## 2. 확인하기
```
notepad %SystemRoot%\system32\drivers\etc\hosts
```

## 참고)
윈도우의 기본 시스템경로 설정 '%SystemRoot%' 값은
'C:\WINDOWS' 입니다.

혹여나 해당 파일이 열리지 않을 경우, 기본 시스템 경로( 환경변수 PATH 설정)가 변경되었을 수도 있습니다.

- 기본 hosts파일 경로
    - 'C:\WINDOWS\system32\drivers\etc\hosts'


---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 환영합니다~~ 감사합니다 :D