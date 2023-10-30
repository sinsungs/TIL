# Exception 예외처리 정리

## @ControllerAdvice
모든 Controller에서 발생할 수 있는 예외 처리

예외 발생 시 json의 형태로 결과를 반환하기 위해서는 @RestControllerAdice를 사용하면 됨 

## @ExceptionHandler
특정 Controller의 예외 처리 
발생하는 예외 마다 처리할 메소드를 정의 

@ExceptionHandler(00Exception.class)
어떤 Exception.Class를 처리할지 설정할 수 있음 

@ControllerAdvice보다 @ExceptionHandler가 우선순위를 가진다 

## Custom Exception 



