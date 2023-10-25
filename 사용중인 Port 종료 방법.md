# 8080 포트 강제종료 
cmd에서 netstat -ano 입력 후 8080 로컬주소를 사용 중인 것의 pid 알아내서 강제종료
관리자 모드로 cmd 실행 후, taskkill /f /pid [pid] 입력
작업관리자에서 pid 강제종료

```
netstat -ano
taskkill /f /pid [pid]
```
최근에 JSP 진행하면서 오라클을 사용했는데 8080을 사용하고 있어서 그런 것 같다.