## RequiredArgsConstructor

@RequiredArgsConstructor 어노테이션을 사용한 생성자 주입
- 생성자주입의 단점은 생성자를 만들기 번거롭다는 점이다.
- 롬복을 사용하여 간단한 방법으로 생성자 주입을 할 수 있다.

~~~java
public class test {
    
    private final UserService  userService;
    private final JoinService  joinService;
    
    @Autowired
    public ExampleCase(UserService  userService, JoinService  JoinService) {
   	this.userService = userService;
   	this.JoinService = JoinService;
    }
}
~~~

### @RequiredArgsConstructor
final이 붙거나 @NotNull 이 붙은 필드의 생성자를 자동 생성해주는 롬복 어노테이션
- @RequiredArgsConstructor 를 활용한 생성자 주입

~~~java
@Service
@RequiredArgsConstructor
public class testImpl implements test {

private final UserRepository userRepository;
private final CommonFileUtils commonFileUtils;

}
~~~