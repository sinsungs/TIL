# JUnit
- Java 진영의 대표적인 Test Framework
- 단위 테스트(Unit Test)를 위한 도구를 제공
- 어노테이션을 기반으로 테스트를 지원
- 단정문(Assert)으로 테스트 케이스의 기대값에 대해 수행 결과를 확인할 수 있다 
- Spring Boot 2.2버전부터 JUnit 5 버전을 사용
- JUnit 5는 크게 Jupiter, Platform, Vintage 모듀롤 구성됨


## 단위 테스트란 ? 
- 코드의 특정 모듈이 의도된 대로 동작하는지 테스트 하는 절자
- 모든 함수와 메소드에 대한 각각의 테스트 케이스(Test Case)를 작성하는 것 

## @SpringBootTest
- 통합 테스트 용도로 사용됨
- @SpringBootApplication을 찾아가 하위의 모든 Bean을 스캔하여 로드함
- 그 후 Test용 Application Context를 만들어 Bean을 추가하고, MockBen을 찾아 교체

## @MockBean
- 테스트할 클래스에서 주입 받고 있는 객체에 대해 가짜 객체를 생성해주는 어노테이션
- 해당 객체는 실제 행위를 하지 않음