## 서블릿 예외 처리 - 시작
* WAS <- 필터 <- 서블릿 <- 인터셉터 <- 컨트롤러
* Exception(500), response.sendError(404, 500..)

## 서블릿 예외 처리 - 오류 화면 제공
* WebServerFactoryCustomizer통해 에러발생시 이동 페이지 설정
* new ErrorPage(HttpStatus.NOT_FOUND, "/error-page/404");

## 서블릿 예외 처리 - 오류 페이지 작동 원리
* WAS(예외 확인) <- ... <- 컨트롤러(예외 발생)
* WAS(오류 페이지 요청 /errorpage/404) -> ... -> 컨트롤러
