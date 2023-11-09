# Doker 도커 (Maven)

## Doker란 ? 
application을 패키징 할 수 있는 tool 
Docker 컨테이너는 다른 환경에서도 안정적으로 실행이 가능해진다 

## Docker hub , image , container 개념
docker hub -> [ pull ] -> image -> [ run ] -> container

## Docker install
```
sudo apt update
sudo apt install maven
sudo apt install docker.io

```

## Docker file 양식 
```
FROM openjdk:17-jdk-alpine
ADD /docker/*.jar app.jar
ENTRYPOINT ["java", "-jar", "app.jar"]
```

## Docker 실행 commend 
```

// 도커 빌드 
sudo docker build -t good-influence_v2/spring_influence_v2 .

// 도커 이미지 확인
sudo docker images

```
이 과정을 마치면 스프링부트가 Docker 컨테이너 안에서 실행될 수 있다 

이제 우분투에 온 요청을 Docker로 보내줘야 합니다

```
sudo docker run -p 8080:8080 good-influence_v2/spring_influence_v2
```
위 명령어를 실행하면 8080 요청을 docker 컨테이너 안에서 실행 가능 
