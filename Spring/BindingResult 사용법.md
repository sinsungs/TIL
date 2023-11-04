# BindingResult 사용법 

## BindingResult 란 ? 
유효성 검사 결과를 처리할 수 있습니다.

BindingResult 객체는 유효성 검사를 통과하지 못한 필드와 에러 메시지를 저장합니다.
각 필드에 대한 유효성 검사 오류 정보를 이 객체에 저장합니다.

hasErrors() 메서드를 사용하여 유효성 검사 결과가 있는지 확인할 수 있습니다. hasErrors()가 true인 경우,
유효성 검사에서 오류가 발생했음을 나타냅니다.

FieldError 객체를 사용하여 각 필드의 에러 메시지를 추출할 수 있습니다.
이를 통해 어떤 필드에서 어떤 유효성 검사 오류가 발생했는지 알 수 있습니다.

BindingResult 객체를 사용하여 클라이언트에게 유효성 검사 오류 메시지를 반환할 수 있습니다.
이를 통해 클라이언트에게 유효성 검사 오류에 대한 적절한 응답을 전달할 수 있습니다.

```
	// 회원 가입
	@PostMapping("/user/join")
	public ResponseEntity<String> joinUser(@Valid @RequestBody UserDTO dto, BindingResult br) {
		if(br.hasErrors()) {
//			return ResponseEntity.ok("회원 정보가 부족합니다.");
			
			// DTO에서 유효성 검사를 통과하지 못한 에러들 매핑 
	        for (FieldError error : br.getFieldErrors()) {
	        	
	        		// 에러의 message를 반환 
	                return ResponseEntity.ok().body(error.getDefaultMessage());
	                
	        }
		}
		
		String result = userService.Join(dto);
		
		return ResponseEntity.ok(result);
	}
```