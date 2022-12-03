---
title: "[Spring] 1.1 프로젝트 환경설정"
excerpt: ""

categories:
- Spring beginning

tags:
- [Spring, Programming]

toc: true
toc_sticky: true

date: 2022-12-01
last_modified_at: 2022-12-01
---

인프런의 **'김영한의 스프링 입문'** 강의를 들으며 정리한 내용  
[🍃스프링입문-코드로 배우는 스프링부트](https://inf.run/R53Z)

<br>

## 프로젝트 생성
- IDE: IntelliJ 또는 Eclipse -> IntelliJ 사용함

### 스프링 프로젝트 생성

- 프로젝트 선택
    - Project: Gradle Project
    - Spring Boot (SNAPSHOT, M1같은 미정식 버전을 제외하고 최신 버전 사용) 
    - Language: JAVA
    - Packaging: Jar
    - JAVA: 11

- Project Metadata
    - groupId: hello
    - artifactId: hello-spring

- Dependencies: Spring Web, Thymeleaf
![image](https://user-images.githubusercontent.com/96652450/204960159-f4048507-f80b-4be3-8485-eb22abebb79c.png)

### Gradle 설정
```
//build.gradle 

plugins {
	id 'org.springframework.boot' version '2.7.3'
	id 'io.spring.dependency-management' version '1.0.13.RELEASE'
	id 'java'
}

group = 'hello'
version = '0.0.1-SNAPSHOT'
sourceCompatibility = '11'

dependencies {
	implementation 'org.springframework.boot:spring-boot-starter-thymeleaf'
	implementation 'org.springframework.boot:spring-boot-starter-web'
	testImplementation ('org.springframework.boot:spring-boot-starter-test') {
		exclude group: 'org.junit.vintage', module: 'junit-vintage-engine'
	}
}
```

### IntelliJ JDK 설치 확인

- 프로젝트 JDK 설정
    - Windows: File -> Project Structure (ctrl+alt+shift+S)  
![image](https://user-images.githubusercontent.com/96652450/205441210-88b97346-14db-407c-a288-0d5b9915c842.png)

- Gradle JDK 설정
    - Windos: File -> Settings (ctrl+alt+S)
![image](https://user-images.githubusercontent.com/96652450/205460793-12caa135-a3f6-4e94-b713-39bb839524e4.png)