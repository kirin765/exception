## 서블릿 예외 처리 - 시작
* WAS <- 필터 <- 서블릿 <- 인터셉터 <- 컨트롤러
* Exception(500), response.sendError(404, 500..)

## 서블릿 예외 처리 - 오류 화면 제공
* WebServerFactoryCustomizer통해 에러발생시 이동 페이지 설정
* new ErrorPage(HttpStatus.NOT_FOUND, "/error-page/404");

## 서블릿 예외 처리 - 오류 페이지 작동 원리
* WAS(예외 확인) <- ... <- 컨트롤러(예외 발생)
* WAS(오류 페이지 요청 /errorpage/404) -> ... -> 컨트롤러

## 서블릿 예외 처리 - 필터
* WAS -> 필터 -> ... -> 컨트롤러 인 경우 dispatcherTypes = REQUEST
* WAS(오류로 인한 호출 /errorpage/500) -> 필터 -> ... -> 컨트롤러 인 경우 dispatcherTypes = ERROR
* dispatcherTypes를 설정하여 필터링 하고자하는 dispatcherTypes 설정 가능

## 스프링 부트 - 오류 페이지1
* 아무것도 설정을 하지않아도 BasicErrorController에서 오류페이지로 이동
* 404.html, 400.html, 500.html, 4xx.html, 5xx.html 등으로 자동 이동

## 스프링 부트 - 오류 페이지2
* 다양한 오류 정보를 넘겨주어 뷰에서 표시 가능

## API 예외처리 - 시작
* @RequestMapping의 produces = MediaType.APPLICATION_JSON_VALUE로 설정하여
* application/json 요청에 대해서만 에러처리

## 스프링 부트 기본 오류 처리
* BasicErrorController에서 Header의 Accept에 따라 오류의 반환결과 달리 할 수 있음
* text/html -> html 전송, application/json -> json 형식으로 전송