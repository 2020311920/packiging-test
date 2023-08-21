# <img src="https://play-lh.googleusercontent.com/Ob9Ys8yKMeyKzZvl3cB9JNSTui1lJwjSKD60IVYnlvU2DsahysGENJE-txiRIW9_72Vd" style="height: 32px;"> Kakao Alarm Bot</div>

<div align="center">
<p>
  <img src="https://github.com/hyeonjeong-ko/skku-git-assignment-1/assets/80453145/6298b61c-bdc0-41ff-b961-c483361170ec" style = "height: 300px;">
  <img src="screenshots/feed_push.png" style = "height: 300px;">
  <img src="screenshots/text_pull_request.png" style = "height: 100px;">
  <img src="screenshots/text_push.png" style = "height: 100px;">
</p>

<p>
  더 이상 팀원에게 따로 일일이 직접 연락을 하지 마세요!<br> Github Action을 활용하여 만든 Kakao Alarm Bot과 함께라면 실시간으로 작업내용을 팀원에게 알려줄 수 있습니다!
</p>
</div>

# 사전 설정

1. [Kakao Developers](https://developers.kakao.com/)에 들어가 내 애플리케이션에 들어간다.<br>
> <img src="https://github.com/hyeonjeong-ko/skku-git-assignment-1/assets/80453145/9af6470a-cb3b-4870-afe5-46d633ebda96" style = "width: 700px;">
<br>

2. 애플리케이션이 없다면 새로 만듭니다.<br>
> <img src="https://github.com/hyeonjeong-ko/skku-git-assignment-1/assets/80453145/11a52288-e856-4d6b-a69e-f25cb3902022" style = "width: 700px;">
<br>

3. 좌측 "팀 관리"에서 본인 팀원의 카카오톡 ID를 입력하여 팀원을 초대하세요.<br>
> <img src = "https://github.com/hyeonjeong-ko/skku-git-assignment-1/assets/80453145/040787cf-10ab-44e1-9f95-c8a00f80d835" style = "width: 700px;">
<br>

4. 좌측의 "플랫폼" >> "WEB"에서 "https://github.com" 를 추가해주세요.<br>
> 그래야 카톡이미지와 버튼이 본인 리포지터리로 링크가 됩니다.<br>
> ![platform_web_url](https://github.com/hyeonjeong-ko/skku-git-assignment-1/assets/80453145/6ee11402-cef1-45a3-a2db-033d70101cb9)
<br>

5. 4와 마찬가지로 좌측의 "카카오 로그인"에서 "활성화를 시킨 이후, 아래에 "Redirect URL"에 "https://localhost:3000"을 추가해주세요<br>
> Access Token을 받기 위한 절차입니다
> ![kakao_developer_login_statusON](https://github.com/hyeonjeong-ko/skku-git-assignment-1/assets/80453145/bcf327d4-5379-4327-8a31-5aa6e78c87c0)
> ![kakao_developer_login_RedirectURL](https://github.com/hyeonjeong-ko/skku-git-assignment-1/assets/80453145/fb3f9d25-0670-4bfc-8fe3-1c21fd762e4c)


카카오 디벨로퍼
앱 만들기
팀원 넣기
rest api 코드를 사용자 입력 변수에 집어넣기


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
