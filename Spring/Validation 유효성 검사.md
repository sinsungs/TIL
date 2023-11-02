# 유효성 검사 / 데이터 검증 (Validation)

## 유효성 검사란 ? 
서비스의 비즈니스 로직이 올바르게 동작하기 위해 사용되는 데이터에 대한 사전 검증하는 작업이 필요함

Validation은 들어오는 데이터에 대해 의도한 형식의 값이 제대로 들어오는지 체크하는 과정을 뜻함 

이전 버전의 Spring Boot에서는 starter-web에 validation이 포함되어 있었으나, Spring Boot 2.3버전 부터 starter-validation을 추가해야함

@Valid : 해당 객체의 유효성 검사 
검증 오류 시 MethodArgumentNotValidException 예외 발생 

@Validated : 컨트롤러가 아닌 다른 계층에서 유효성 검사를 하고 싶을 때는 @Validated를 사용하면 된다. Validated는 AOP 기반으로 메소드의 요청을 가로채서 유효성 검사를 진행해준다.
검증 오류 시 ContraintViolationException 예외 발생 