# nohup 실행 종료 방법

# nohup 실행
```
nohup java -jar build/lib/demo-0.0.1-SNAPSHOT.jar &
```
EC2 백그라운드에서 배포 유지할 수 있다 
& 를 뒤에 붙여주면 jar 실행 후에도 명령어를
계속해서 입력할 수 있다 

# nohup 종료 
```
ps -ef
// jar 파일 pid 찾아서 kill
kill PID
```