## 컴파일러 언어
컴파일러(compiler)는 고급언어로 작성된 소스코드를 저급언어로 번역하는 프로그램<br>
고급언어는 사람이 이해하기 쉽게 작성된 프로그래밍 언어로 C, C++, Java 등이 이에 속한다.<br>
저급언어는 컴퓨터 내부에서 바로 처리 가능한 프로그래밍 언어로 기계어와 어셈블리어가 이에 속한다.<br><br>


컴파일러 언어는 컴파일러를 통해 컴파일 타임에 전체 소스코드를 한번에 기계어로 변환 후 실행파일을 만든다.<br>
컴파일러 언어는 컴파일 단계와 실행단계가 분리되어있으며 컴파일은 한번만 수행한다.<br>
실행은 실행파일을 실행시킴으로써 할 수 있고 실행시에는 컴파일 과정을 거치지 않고 실행만 하면 되므로 코드 실행속도가 빠르다. 단, 프로젝트의 규모가 클 경우 컴파일 시간이 오래걸릴 수 있다.

- C, C++, C#, Java 등


## 인터프리터 언어
인터프리터(interpreter)는 프로그래밍 언어와 소스코드를 바로 실행하는 컴퓨터 프로그램이다.<br>
인터프리터 언어는 소스코드를 한번에 기계어로 변환하는 컴파일러와 달리 컴파일하지않고 소스 코드를 한줄씩 읽어 실행한다.<br>
컴파일 하는 과정이 없기 때문에 컴파일 하는 시간은 소요되지 않으나 인터프리터 언어는 실행파일을 별도로 생성하지 않기 때문에 실행시마다 인터프리터 과정이 반복되어 실행속도가 느리다.
- Javascript, Python, Ruby 등