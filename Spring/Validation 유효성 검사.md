# 유효성 검사 / 데이터 검증 (Validation)

## 유효성 검사란 ? 
서비스의 비즈니스 로직이 올바르게 동작하기 위해 사용되는 데이터에 대한 사전 검증하는 작업이 필요함

Validation은 들어오는 데이터에 대해 의도한 형식의 값이 제대로 들어오는지 체크하는 과정을 뜻함 

이전 버전의 Spring Boot에서는 starter-web에 validation이 포함되어 있었으나, Spring Boot 2.3버전 부터 starter-validation을 추가해야함

@Valid : 해당 객체의 유효성 검사 
검증 오류 시 MethodArgumentNotValidException 예외 발생 

@Validated : 컨트롤러가 아닌 다른 계층에서 유효성 검사를 하고 싶을 때는 @Validated를 사용하면 된다. Validated는 AOP 기반으로 메소드의 요청을 가로채서 유효성 검사를 진행해준다.
검증 오류 시 ContraintViolationException 예외 발생 

@Validated 는 스프링 전용 검증 애노테이션이고, @Valid 는 자바 표준 검증 애노테이션이다. 

## 유효성검사 어노테이션 모음 

@Null  // null만 혀용합니다.
@NotNull  // null을 허용하지 않습니다. "", " "는 허용합니다.
@NotEmpty  // null, ""을 허용하지 않습니다. " "는 허용합니다.
@NotBlank  // null, "", " " 모두 허용하지 않습니다.

@Email  // 이메일 형식을 검사합니다. 다만 ""의 경우를 통과 시킵니다
@Pattern(regexp = )  // 정규식을 검사할 때 사용됩니다.
@Size(min=, max=)  // 길이를 제한할 때 사용됩니다.

@Max(value = )  // value 이하의 값을 받을 때 사용됩니다.
@Min(value = )  // value 이상의 값을 받을 때 사용됩니다.

@Positive  // 값을 양수로 제한합니다.
@PositiveOrZero  // 값을 양수와 0만 가능하도록 제한합니다.

@Negative  // 값을 음수로 제한합니다.
@NegativeOrZero  // 값을 음수와 0만 가능하도록 제한합니다.

@Future  // 현재보다 미래
@Past  // 현재보다 과거

@AssertFalse  // false 여부, null은 체크하지 않습니다.
@AssertTrue  // true 여부, null은 체크하지 않습니다.