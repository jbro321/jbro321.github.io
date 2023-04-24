---
layout: post
title:  "Edge 가짜 도메인 가입해 Edge://policy 정책 허용"
date:   2023-04-19 18:25:36 +0900
categories: Web Edge
published: true
---
```
Edge 정책 확인하기 위해 가짜 도메인 가입
- Edge policy에서 오류, 무시됨
- 가짜 도메인 가입 레지스트리
```

# 사건의 발단
윈도우11로 넘어오면서 InternetExplorer가 사라지고 Edge의 시대로 넘어갔습니다. 물론 아직 Edge가 완벽하지 않아 Edge에서 IE모드를 지원하고 있습니다. 허나, 이는 언제까지 지원될지 모르니 Edge에서 설정을 해보았습니다.

## Edge에서 자동으로 파일 열기
Edge에서 자동으로 파일을 열게 하기 위해 AutoOpenAllowedForURLs, AutoOpenFileTypes 레지스트리 설정을 했습니다.

### 참고 : Edge 정책 AutoOpenAllowedForURLs, AutoOpenFileTypes 설정
> [Edge에서 팝업 없이 자동으로 파일 열기 : AutoOpenAllow](https://jbro321.github.io/web/edge/2023/03/28/Edge-AutoOpenAllow.html)
> [![Edge_fake_mdm1.png](/assets/img/Web/Edge/2023-04-19-Edge_fake_mdm/Edge_fake_mdm1.png)](https://jbro321.github.io/web/edge/2023/03/28/Edge-AutoOpenAllow.html) **☝︎ 그림 클릭 :)**

### 하지만, 잘되었던 자동으로 열리던게 갑자기 다른 pc에서는 안되는 겁니다...!!

## Edge 정책 확인
[Edge://policy](Edge://policy) 를 확인해보니,
아래 그림과 같이 AutoOpenFileTypes에 "오류, 무시됨"이 뜨고

자세히 표시를 눌러보니, "오류 이 정책은 차단되어 있습니다. 해당 값을 무시합니다."
무시당했습니다... ㅠㅠ

![Edge_fake_mdm2](/assets/img/Web/Edge/2023-04-19-Edge_fake_mdm/Edge_fake_mdm2.png)

## Edge 정책 문서 확인
[AutoOpenFileTypes 엣지 정책 문서](https://learn.microsoft.com/ko-kr/DeployEdge/microsoft-edge-policies#autoopenfiletypes) 를 확인해보니 아래에, autoopenfiletypes 허용은 도메인 가입이 되어 있는 컴퓨터에서만 가능하다고 나와있습니다...

![Edge_fake_mdm3](/assets/img/Web/Edge/2023-04-19-Edge_fake_mdm/Edge_fake_mdm3.png)

# 방법 찾았습니다 : 가짜 도메인 가입
구글링을 하던 중에 가짜 도메인을 가입시켜 Edge정책을 임의로 허용하게 만드는 블로그를 찾아서 적용해보았습니다. (~~해당 [블로그]((https://hitco.at/blog/apply-edge-policies-for-non-domain-joined-devices/))의 글쓴이가 엄청 고생하신거 같아요~~)

## 레지스트리 설정
```powershell
reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Enrollments\FFFFFFFF-FFFF-FFFF-FFFF-FFFFFFFFFFFF" /v EnrollmentState /t REG_DWORD /d 0x00000001

reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Enrollments\FFFFFFFF-FFFF-FFFF-FFFF-FFFFFFFFFFFF" /v EnrollmentType /t REG_DWORD /d 0x00000000

reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Enrollments\FFFFFFFF-FFFF-FFFF-FFFF-FFFFFFFFFFFF" /v IsFederated /t REG_DWORD /d 0x00000000

reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Provisioning\OMADM\Accounts\FFFFFFFF-FFFF-FFFF-FFFF-FFFFFFFFFFFF"
```

# 성공 : 정책 허용 확인

![Edge_fake_mdm4](/assets/img/Web/Edge/2023-04-19-Edge_fake_mdm/Edge_fake_mdm4.png)

# 추가사항
- 도메인 연결 방법으로, 회사 혹은 학교 ms teams에 로그인하면, 정책이 확인되는걸 확인할 수 있습니다. 뇌피셜로는, 학교나 회사 ms teams는 기본적으로 도메인으로 가입을 시켜줘야해서 로그인하게되면 도메인이 자동적으로 설정되는 것 같습니다.

추후 다른 방법을 찾게 되면, 추가 포스팅하겠습니다...

참고한 블로그 : [apply-edge-policies-for-non-domain-joined-devices](https://hitco.at/blog/apply-edge-policies-for-non-domain-joined-devices/)

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 너무 환영합니다~ 감사합니다 :D