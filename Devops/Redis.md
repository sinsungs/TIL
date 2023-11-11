# Redis 

## Redis 란 ? 
Remote dictionary server 
외부 ( key : value ) server 

32bit CPU에서 int 최대값은 ? 
2147483647
쿠팡에서 모든 상품이 품절로 보여지는 이슈가 있었는데 
이유는 int의 최대값인 2147483647 개의 Key를 초과해서 발생한
에러라고 합니다. int -> long으로 이슈 대응했다고 합니다. 

## Cache 란 ? 
나중의 요청에 대한 결과를 미리 저장했다가 빠르게 사용하는 것 
Main Memory가 아닌 Cpu Cache 영역에 해당한다 

Database보다 더 빠른 Memory에 더 자주 접근하고 덜 자주 바뀌는 데이터를 저장하자 
In-memory Database (Cache) 

## Redis 자료구조 
Collection 
String(key-value) , List , Set , Sorted Set , Hash 

HashMap은 사용하지 않는 이유 
서버가 여러대인 경우 Consistency의 문제 발생 
Multi-Threaded 환경에서 Race Condition 

Race Condition이란 여러 개의 Thread가 경합하는 것
Context Switching에 따라 원하지 않는 결과가 발생 

## Redis 어디서 쓰나요 ? 
여러 서버에서 같은 데이터를 공유할때
Single Server라면 ? Atomic 자료구조 & Cache

## Redis 주의사항
Single Thread 서버 이므로 시간 복잡도를 고려해야 한다 
In-memory 특성상 메모리 파편화 , 가상 메모리등의 이해가 필요하다 

Single Thread이므로 빨리빨리 처리해야 한다 
그만큼 처리가 빨라야 한다 -> ex : false -> O(N) 

Memory의 파편화를 생각해야 하기 때문에 메모리를 여유있게 사용해야함
