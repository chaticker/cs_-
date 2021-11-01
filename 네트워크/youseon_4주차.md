# CORS가 무엇이며 어떻게 해결을 할 수 있는지 설명해 보세요.

다른 도메인에서 리소스 요청 시 cross-origin HTTP 에 의해 요청을 하는데, 대부분의 브라우저는 보안 상의 이유로 이 요청을 제한한다. 이를 동일 오리진 정책(Same Origin Policy)이라고 한다. 요청을 보내기 위해서는 요청 보내는 대상과 프로토콜이 같아야 하고, 포트도 같아야 한다. JSONP(JSON-padding)을 통해 해결하거나 특정 HTTP 헤더를 추가하여 이 이슈를 해결할 수 있다. 이와 같이 타 도메인 간 자원을 공유할 수 있게 해주는 것을 Cross Origin Resource Sharing, 줄여서 CORS라고 한다.