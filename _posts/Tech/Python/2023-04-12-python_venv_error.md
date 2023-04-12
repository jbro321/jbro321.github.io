---
layout: post
title:  "Python 가상환경 실행 오류 (Windows Powershell)"
date:   2023-04-12 17:14:33 +0900
categories: Tools Powershell
published: true
---
```
Python venv error
- Powershell 실행 오류
- Powershell 실행 정책
```

# PowerShell 가상환경 실행 오류 (venv)

- 가상환경 생성은 아래 블로그 글을 참고해주세요 **☟**
> [![Python_venv_mk_del_url.png](/assets/img/Tech/Python//Python_venv_error/Python_venv_mk_del_url.png)](https://jbro321.github.io/tech/python/2023/04/05/Python_venv_mk_del.html) **☝︎ 그림 클릭 :)**

## 가상환경 실행
- 가상환경을 '.venv'로 생성한 경우입니다.

```powershell
.venv\Scripts\Activate
```

## 오류 발생

![python_venv_error1.png](/assets/img/Tech/Python//Python_venv_error/python_venv_error1.png)

## 오류 발생 원인

- **"PowerShell이 가상화 실행 명령 스크립트의 실행을 제한하기 때문입니다"**

## PowerShell의 실행 정책

PowerShell의 실행 정책은 PowerShell이 구성 파일을 로드하고 스크립트를 실행하는 조건을 제어하는 안전 기능입니다. 이 기능은 악성 스크립트의 실행을 방지하는 데 도움이 됩니다.

( 출처 : [microsoft.powershell-policy](https://learn.microsoft.com/ko-kr/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7.2) )

## 해결책 : " PowerShell의 실행 정책을 변경 "

### 1. Windows PowerShell 관리자 권한으로 실행

![python_venv_error2.png](/assets/img/Tech/Python//Python_venv_error/python_venv_error2.png)

### 2. 현재의 실행정책 확인

```powershell
Get-ExecutionPolicy
```

**"RemoteSigned"**가 아닌 경우, RemoteSigned로 정책을 바꿔야 합니다.

![python_venv_error3.png](/assets/img/Tech/Python//Python_venv_error/python_venv_error3.png)

### 3. 실행 정책 변경

```powershell
Set-ExecutionPolicy RemoteSigned
```

- A : 모두 예(A) 선택

![python_venv_error4.png](/assets/img/Tech/Python/Python_venv_error/python_venv_error4.png)

정책을 바꾼 후, 가상환경을 다시 실행해보면 정상적으로 실행됩니다.

---

이상입니다.

궁금하신 점은 댓글 남겨주세요!

소통도 환영합니다~~ 감사합니다 :D