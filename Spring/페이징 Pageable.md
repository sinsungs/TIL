# 페이징 Pageable 사용법

```
@GetMapping("/list")
public ResponseEntity<Page<PostReviewDTO>> listPost(@RequestParam(defaultValue = "0") int page, @RequestParam(defaultValue = "10") int size) {
    Page<PostReviewDTO> response = postReviweService.getList(page, size);
    return ResponseEntity.ok(response);
}
```
page와 size 값을 매개로 받아서 원하는 형태로 페이징 할 수 있음 
나는 10개씩 고정적으로 보여주고 싶어서 defaultValue = 10으로 설정 !

프론트에서는 page의 값을 설정해서 넘겨줘야 한다 

```
public Page<PostReviewDTO> getList(int page, int size) {
    Pageable pageable = PageRequest.of(page, size);
    Page<PostReview> postReviews = postReviewRepository.findAll(pageable);
    
    return postReviews.map(postReviewMaper::entityToDTO);
}
```

Pageable 객체를 설정해서 findAll에 넣어주기만 하면 됨 
왜 ? JPA가 지원해주니까 
