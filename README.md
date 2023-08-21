# Kakao Alarm Bot

## Kakao Alarm Bot은 GitHub의 Pull Request와 Merge 관련 정보를 자동으로 카카오톡으로 알림을 보내주는 도구입니다.
###  더 이상 수동으로 카카오톡으로 리뷰를 요청하거나 알림을 보내지 마세요!

# 사용 방법

- 이 저장소를 클론하거나 Fork합니다.
- KakaoTalk API 토큰을 얻습니다.
- 카카오 개발자 사이트에서 프로젝트를 생성하고 API 토큰을 발급받습니다.
- 저장소 Settings > Secrets로 이동하여 아래와 같이 Secrets를 추가합니다:
- KAKAO_API_TOKEN: 카카오톡 API 토큰 값을 추가합니다.
- .github/workflows/kakao_alert.yml 파일을 업데이트하고 커스터마이즈합니다:
- 
원하는 Pull Request 이벤트와 브랜치를 설정합니다.
send_kakao_alert.js 파일을 열어 KakaoTalk 알림 보내는 스크립트를 수정할 수 있습니다:
원하는 알림 형식이나 내용으로 커스터마이즈합니다.
README 파일 업데이트:
필요한 사용법과 예시 사진을 자세히 기술합니다.
스크린샷 예시
KakaoTalk 알림 예시

# 라이선스
이 프로젝트는 MIT 라이선스 하에 배포됩니다. 자세한 내용은 LICENSE 파일을 참고하세요.
