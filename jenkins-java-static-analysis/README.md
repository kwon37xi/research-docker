# Jenkins for Java Static Analysis Local Gradle Projects

##  환경
* Oracle JDK 설치 : /opt/jdk/jdk1.8.0_111
* Jenkins plugin 설치
* projects 디렉토리 연결

## Build
```
```

## Run
```
docker run --name jjsa -d -p 8080:8080 -p 50000:50000 -v /var/jjsa/:/var/jenkins_home -v /path/to/projecs:/projects jenkins-java-static-analysisjava-static-analysis
```

Open http://localhost:8080

## Project 실행
* Gradle Build 실행시 *General -> 고급(Advanced) -> 사용자 빌드 경로 사용* 에서 Workspace 경로를 프로젝트 경로로 바꿔주면서 Job을 생성할 것.
