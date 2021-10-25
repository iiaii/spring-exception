# spring-exception


### 웹 애플리케이션 호출 구조

```
WAS -> 필터 -> 서블릿 -> 인터셉터 -> 컨트롤러 
```

- 컨트롤러 내부에서 예외가 발생하면 `WAS` 까지 전달된다
- 컨트롤러에서 `response.sendError()` 를 호출하면, 오류가 발생했다는 상태를 저장하고 서블릿 컨테이너가 응답전에 `sendError()`가 호출되었는지 확인 후 설정한 오류코드에 맞추어 기본 오류페이지를 보여준다
- `server.error.whitelabel.enabled=false` 는 스프링이 제공하는 에러페이지를 사용을 해제하는 설정이다

