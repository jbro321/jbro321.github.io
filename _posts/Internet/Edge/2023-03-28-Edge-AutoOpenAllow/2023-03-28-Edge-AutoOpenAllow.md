---
layout: post
title:  "Edge AutoOpenAllow"
date:   2023-03-28 09:10:36 +0900
categories: Internet Edge
---
## Edge에서 팝업 없이 자동 다운로드 하는 방법

### 윈도우 레지스트리 편집기 실행

1. 자동으로 다운로드 할 URL을 등록합니다.

![AutoOpenAllowedForURLs](/_posts/Internet/Edge/2023-03-28-Edge-AutoOpenAllow/AutoOpenAllowedForURLs.jpeg)

위 이미지는 "https://test.com"에서 자동으로 실행하게 설정하였습니다.

```
// Command Prompt > regedit 실행

reg add HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge\AutoOpenAllowedForURLs /v 1 /d https://test.com
```

여러 Url이 있을 경우, 1번에 이어 2번 3번으로 등록하면 됩니다.

2. 자동으로 다운로드 할 FileType을 등록합니다.

![AutoOpenFileTypes](/_posts/Internet/Edge/2023-03-28-Edge-AutoOpenAllow/AutoOpenFileTypes.jpeg)

### or 커맨드 명령어로 등록
```
// Command Prompt > regedit 실행

reg add HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Edge\AutoOpenFileTypes /v 1 /d application
```
위는 "application" 파일을 자동으로 다운로드 설정한 방법입니다.