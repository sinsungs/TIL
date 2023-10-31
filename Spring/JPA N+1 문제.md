# JPA N + 1 문제 
요청이 1개의 쿼리로 처리 되길 기대했는데 N개의 추가 쿼리가 발생 하는 현상 

## 해결 방법 Fetch join
연관된 엔티티나 컬렉션을 한 번에 같이 조회하는 기능 
( 연관된 엔티티까지 영속성 컨텍스트에 전부 올린다. )

## 즉시 로딩을 하면 해결되는것이 아닌가 ? 
즉시로딩도 N + 1 문제를 가지고있다 
지연로딩은 필요할때 N + 1 문제를 발생시키고
즉시로딩은 즉시 바로 N + 1문제를 발생하는 차이가 있다 
 
즉시로딩을 최대한 사용하지 않고, 지연로딩 + fetch join 전략을 추천한다.

## findById() , findAll() 시에 N + 1 문제 해결 과정 

```
    // 소셜 모임 전체 조회
    public List<MeetDTO> listMeet() {
    	
        List<Meet> meets = meetRepository.findAll();
        
        List<MeetDTO> dtoList = new ArrayList<>();
        
	     for (Meet meet : meets) {
	      dtoList.add(meetMapper.entityToDTO(meet));
	     }
	  
	     return dtoList;
    }
    
```
meet는 user를 참조하고 있습니다
위 코드에서 findAll() 하는데 user의 외래키 값을 where 절에 넣어서 일일이 외래키 N개 만큼 
조회 쿼리가 늘어났고, 이것을 개선하기 위해서 

```
    @EntityGraph(attributePaths = {"user"}) // Fetch Join 설정
    List<Meet> findAll();
```
@EntityGraph 애너테이션으로 Fetch Join을 설정해서 1번의 쿼리로 개선하였습니다.