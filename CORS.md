# CORS

추가 HTTP 헤더를 사용해, 한 출처에서 실행중이 웹 어플리케이션이 다른 출처의 자원에 접근할 수 있는 권한을 부여하도록 브라우저에 알려주는 체제. 보안상의 이유로, 브라우저는 스크립트에서 시작한 교차 출처 HTTP 요청을 제한합니다.



### 어떤 요청이 CORS를 사용할까?

* XMLHttpRequest같은 FetchAPI호출
* 웹폰트
* WebGL 텍스쳐
* 캔버스에 그린 이미지/비디오 프레임
* 이미지로부터 추출하는 CSS Shapes



### 사전 요청(preflight)

브라우저에서 실제 요청을 할 수 있는 권한을 요청하기 위해 서버에 '사전 요청'을 보냄.

서버에서 다음과 같은 헤더 집합으로 응답을 보냄

* Access-Control-Allow-Origin
* Access-Control-Allow-Methods
* Access-Control-Allow-Headers

여기에는 인증 토큰과 같은 헤더가 필요하다는 정보도 포함되어 있음.