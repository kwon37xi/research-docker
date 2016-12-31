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
docker run --name jjsa -p 8080:8080 -p 50000:50000 -v /var/jjsa/:/var/jenkins_home -v /path/to/projecs:/projects jenkins-java-static-analysisjava-static-analysis
```

Open http://localhost:8080

## Project 실행
* Gradle Build 실행시 `Root Build script`를 `/projects/project-name` 형태로 구성하면 Workspace로 파일 복사를 하지 않아도 빌드할 수 있다.
