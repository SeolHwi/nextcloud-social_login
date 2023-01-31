# Social login ( Google, Meta, Kakao, Naver )

### 소셜 로그인 API

구글 로그인 API: https://console.cloud.google.com

메타 로그인 API: https://developers.facebook.com/apps/

카카오 로그인 API: https://developers.kakao.com/console/app

네이버 로그인 API: https://developers.naver.com/products/login/api/api.md

### social login 앱 사용 방법

각 소셜의 개인 계정에서 개발자 모드를 통해 로그인 API 사용

API 설정 완료 후 앱 ID와 Secret을 얻어 nextcloud social login 앱에 적용

  1. 관리자 계정으로 로그인 후 setting -> social login 탭에서 위에서 얻은 앱 ID와 Secret 입력
  2. cli환경에서 nextcloud의 DB로 접속하여 직접 앱 ID와 Secret 입력

* * *
  
### 앱 활성화

    sudo -u apahce php occ app:install sociallogin
    sudo -u apache php occ app:enable sociallogin
    
### Redirect URL

    [nextcloud_url]/index.php/apps/sociallogin/custom_oauth2/[internal_name]
    [nextcloud_url]/index.php/apps/sociallogin/custom_oidc/[internal_name]
    [nextcloud_url]/index.php/apps/sociallogin/oauth/[internal_name]

* * *

### 특이사항

* 네이버 로그인은 미구현

* 구글과 메타 로그인은 social login 앱에서 지원을 해줘서 앱 ID와 Secret만 입력하면 동작
  (docs/sso/ 폴더 참고)

* 카카오는 social login 앱의 Custom OpenID Connect를 사용하여 구현

* 네이버 로그인 API는 OIDC를 지원하지 않아 카카오와 같은 방법 사용 불가능

* css/styles.css line 28~47

  * 카카오와 네이버의 로그인 버튼 임시 이미지로 구글 로그인 이미지와 같은 이미지 사용
  
  * 카카오와 네이버 로그인 버튼의 색상 임의 지정

  * ![nextcloud-social_login-button](https://user-images.githubusercontent.com/94033731/215657737-54785652-f3fa-4578-91eb-f64bcb8a4d39.png)


##### 참고

https://github.com/zorn-v/nextcloud-social-login
