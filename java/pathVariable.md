## @PathVariable
요청이 들어오는 타입은 아래와 같다.
1. URL 변수(@PathVariable)
2. Query String (@RequestParam / ?name=hansol&age=30)
3. Body
4. Form

### @PathVariable란?
- REST API에서 URI에 변수가 들어가는 걸 볼 수 있다.
 - https://godsolnote.tistory.com/26
 - url 마지막 부분 '/26' 이 @PathVariable로 처리해줄 수 있는 부분
 
### 사용
- Mapping 종류에 상관없다.
- 메소드 정의에서 정의한 {"변수명"} 을 그대로 @PathVariable("변수명") 으로 사용
```java
@Controller
public class TestController {

	@PostMapping("/test/{name}")
	public String testName(@PathVariable("name") String name) {
		return "name : " + name;
	}
	
	@PostMapping("/test/{name}/{age}")
	public String testName(@PathVariable("name") String name, @PathVariable("age") {
		return "name : " + name + ", age: " + age;
	}
}
```