---
layout: post
title:  "Edge AutoOpenAllow"
date:   2023-03-28 09:10:36 +0900
categories: Internet Edge
published: true
---
```powershell
Edge에서 팝업 없이 자동 다운로드 하는 방법입니다.
- 자동으로 다운로드 할 URL을 등록합니다.
- 자동으로 다운로드 할 FileType을 등록합니다.
```

## 윈도우 레지스트리 편집기 실행

## 1. 자동으로 다운로드 할 URL을 등록합니다.
* 아래는 "https://test.com"에서 자동으로 실행하게 설정한 예시입니다.

```powershell
// Command Prompt > regedit 실행 후 아래 경로로 이동

경로 : HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs
```

오른쪽 클릭 > NEW > String Value > 이름 '1' > 오른쪽 클릭 > Modify > Value data에 "https://test.com"

![AutoOpenAllowedForURLs](/assets/img/Internet/Edge/AutoOpenAllow/AutoOpenAllowedForURLs.jpeg)

or 커맨드 명령어로 등록
```powershell
// Command Prompt(cmd) 관리자 권한으로 실행
// 윈도우키 + R > cmd > ctrl + shift + Enter

reg add HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs /v 1 /d https://test.com
```

여러 Url이 있을 경우, 1번에 이어 2번 3번으로 등록하면 됩니다.

* 설정에 따라 다르므로, 'test'도메인만 입력해서 안될 시, https://test/test.com 와 같이 모두 입력해봅시다.

## 2. 자동으로 다운로드 할 FileType을 등록합니다.
* 아래는 "application"을 자동으로 실행하게 설정한 예시입니다.

```powershell
// Command Prompt > regedit 실행 후 아래 경로로 이동

경로 :
HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge\AutoOpenFileTypes
```
오른쪽 클릭 > NEW > String Value > 이름 '1' > 오른쪽 클릭 > Modify > Value data에 "application"

![AutoOpenAllowedForURLs](/assets/img/Internet/Edge/AutoOpenAllow/AutoOpenFileTypes.jpeg)

or 커맨드 명령어로 등록
```powershell
// Command Prompt(cmd) 관리자 권한으로 실행
// 윈도우키 + R > cmd > ctrl + shift + Enter

reg add HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge\AutoOpenFileTypes /v 1 /d application
```

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 너무 환영합니다~ 감사합니다 :D