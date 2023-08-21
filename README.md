# <img src="https://play-lh.googleusercontent.com/Ob9Ys8yKMeyKzZvl3cB9JNSTui1lJwjSKD60IVYnlvU2DsahysGENJE-txiRIW9_72Vd" style="height: 32px;"> Kakao Alarm Bot</div>

<div align="center">
<p>
  <img src="https://github.com/hyeonjeong-ko/skku-git-assignment-1/assets/80453145/6298b61c-bdc0-41ff-b961-c483361170ec" style = "height: 300px;">
  <img src="https://github.com/hyeonjeong-ko/skku-git-assignment-1/assets/80453145/d24bf58c-7042-45d4-a281-55907835afb2" style = "height: 300px;">
  <img src="https://github.com/hyeonjeong-ko/skku-git-assignment-1/assets/80453145/ffbb93c4-be88-415c-889c-43bdb07b517c" style = "height: 100px;">
  <img src="https://github.com/hyeonjeong-ko/skku-git-assignment-1/assets/80453145/af5dda32-10f6-42cf-b303-1c9ac42b7229" style = "height: 100px;">
</p>

<p>
  더 이상 팀원에게 따로 일일이 직접 연락을 하지 마세요!<br> Github Action을 활용하여 만든 Kakao Alarm Bot과 함께라면 실시간으로 작업내용을 팀원에게 알려줄 수 있습니다!
</p>
</div>

# <img src="https://img1.daumcdn.net/thumb/R800x0/?scode=mtistory2&fname=https%3A%2F%2Ftistory1.daumcdn.net%2Ftistory%2F4346785%2Fattach%2F6018d9cab34440c6bccec9dee83bbc57" style="height: 32px;"> 사전 설정 - Kakao Developer</div>

1. [Kakao Developers](https://developers.kakao.com/)에 들어가 내 애플리케이션에 들어간다.<br>
> <img src="https://github.com/hyeonjeong-ko/skku-git-assignment-1/assets/80453145/9af6470a-cb3b-4870-afe5-46d633ebda96" style = "width: 700px;">
<br>

2. 애플리케이션이 없다면 새로 만듭니다.<br>
> <img src="https://github.com/hyeonjeong-ko/skku-git-assignment-1/assets/80453145/11a52288-e856-4d6b-a69e-f25cb3902022" style = "width: 700px;">
<br>

3. 좌측 "팀 관리"에서 본인 팀원의 카카오톡 ID를 입력하여 팀원을 초대하세요.<br>
> <img src = "https://github.com/hyeonjeong-ko/skku-git-assignment-1/assets/80453145/ba4d7ace-0ff5-4acd-a625-e5ab73ac1316" style = "width: 700px;">
<br>

4. 좌측의 "플랫폼" >> "WEB"에서 "https://github.com" 를 추가해주세요.<br>
> !중요 전제조건! 반드시 **기본링크**만 가능합니다. ex)https://github.com/user_name/.... -> 불가!!!<br>
> 나중에 메시지나 버튼을 클릭해서 링크를 이동할 때, **"본인 리포지터리"** 로 이동하려면 깃헙으로 설정해야합니다.<br>
> 또한 단순한 테스트라면 Google이나 타 링크도 가능합니다.<br>
> ![platform_web_url](https://github.com/hyeonjeong-ko/skku-git-assignment-1/assets/80453145/6ee11402-cef1-45a3-a2db-033d70101cb9)
<br>

5. 4와 마찬가지로 좌측의 "카카오 로그인"에서 "활성화를 시킨 이후, 아래에 "Redirect URL"에 "https://localhost:3000"을 추가해주세요<br>
> Access Token을 받기 위한 절차입니다
> ![kakao_developer_login_statusON](https://github.com/hyeonjeong-ko/skku-git-assignment-1/assets/80453145/bcf327d4-5379-4327-8a31-5aa6e78c87c0)
> ![kakao_developer_login_RedirectURL](https://github.com/hyeonjeong-ko/skku-git-assignment-1/assets/80453145/fb3f9d25-0670-4bfc-8fe3-1c21fd762e4c)

6. 마지막 단계입니다. 현재 존재하는 "카카오 로그인"에서 하위 항목 중 "동의항목"에 들어가서 개인정보들 중 수집할 것을 설정합니다.<br>
> 동의 목적은 아무렇게나 써도 됩니다. ex) 개발목적

| 항목이름                  	| 상태         	|
|---------------------------	|--------------	|
| 닉네임                    	| 필수 동의    	|
| 카카오 서비스 내 친구목록 	| 이용 중 동의 	|
| 카카오톡 메시지 전송      	| 이용 중 동의 	|

![kakao_developer_login_Agreement](https://github.com/hyeonjeong-ko/skku-git-assignment-1/assets/80453145/aa218215-c643-4616-8318-132fd1d09c02)

# <img src="https://seeklogo.com/images/G/github-actions-logo-031704BDC6-seeklogo.com.png" style="height: 32px;"> 토큰 받기</div>

1. REST API
> <img src = "https://github.com/hyeonjeong-ko/skku-git-assignment-1/assets/80453145/366daa93-29e7-4948-b901-311a820ad0e9" style = "width: 700px;">

2. dfdf
> `https://kauth.kakao.com/oauth/authorize?client_id={REST API 키}&redirect_uri=https://localhost:3000&response_type=code&scope=talk_message`

```yml
name: Example for show

on:
  push:
    branches:
      - main

jobs:
  run-hjk-test-v1:
    runs-on: ubuntu-latest
    
    steps:
    - name: Checkout code
      uses: actions/checkout@v2
      
    - name: Run hjk-test-v1 action
      uses: hyeonjeong-ko/packiging-test@5.7
      with:
        test-variable: "your test name"
        send-to-function: "send_to_me" or "send_to_friends"
        rest-api-key: "your rest api key" 
        redirect-uri: "your redirect url(이미지 또는 버튼을 클릭할 때 넘어갈 url)"
        code-key: "your Access Token"
        msg-template: "text" or "feed"
```




# 라이선스
이 프로젝트는 MIT 라이선스 하에 배포됩니다. 자세한 내용은 LICENSE 파일을 참고하세요.
