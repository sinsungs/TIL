# RDS too many connections 에러
RDS를 연결한 connection이 30개 초과해서 발생한 에러 입니다.
( RDS 프리티어 기준 30개 )

# RDS connection 에러 해결 방법 
연결 타임아웃을 설정하면 클라이언트가 데이터베이스에 연결을 시도하고 일정 시간 동안 응답을 받지 못하면
연결이 자동으로 해제됩니다. 
이렇게 함으로써 데이터베이스 서버의 연결 리소스가 과도하게 사용되는 것을 방지할 수 있으며, 
장애 조치 및 리소스 관리에 도움이 됩니다.


RDS 파라미터 그룹 설정에서 
wait_timeout 기본값이 28800인데 8시간이라고 합니다.
180으로 줄이면 connect시간이 3분으로 줄어들어 문제를 해결할 수 있습니다. 
또는 max connection을 늘려주면 됩니다.