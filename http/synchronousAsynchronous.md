## 동기와 비동기

개발을 하다보면 수도없이 들어보았을 동기와 비동기

### 동기(Synchronous)
- 직렬적으로 작업을 수행(순차)
- 하나의 작업(Thread1)이 수행될 동안 다른 작업(Thread2)는 대기
- Thread1 종료 후 Thread2 수행
- 하나의 작업이 종료될때까지 다음 작업들은 작업중단된다.(Blocking)

### 비동기(Asynchronous)
- 병렬적으로 작업을 수행
- 하나의 작업(Thread1)이 작업을 시작하고 종료되기를 기다리지 않고 다른 작업을 처리할 수 있음
- 하나의 작업이 종료되지 않은 상태여도 대기하지 않음(non-Blocking)

### Blocking
- 요청한 작업을 마칠때까지 계속 대기
- Thread 관점에서 요청한 작업을 종료할때까지 계속 대기하며 return 값을 받을때까지 Thread를 계속 사용/대기

### Non-Blocking
- 요청한 작업을 즉시 마칠 수 없다면 즉시 return
- Thread 관점에서 하나의 Thread가 여러개의 I/O 처리가 가능하다.