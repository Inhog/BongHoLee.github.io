---
layout: post
title: Web Application Deploy (TOMCAT)
author: Bong5
category:
  - Java
  - Keywords
  - web-development
summary: Servlet (2)
thumbnail: posts/http.png
---

## Web Application Deploy (TOMCAT)

---

그동안 IDE에서만 웹 컨테이너(톰캣)을 구동함으로써 웹 어플리케이션을 실행하고 테스트하느라 실제 운영시 배포 방법에 대해서는 고민해 본적이 없다.

이번 기회에 간단하게 웹 어플리케이션을 톰캣에 배포하는 방법을 살펴본다.

---

### 웹 어플리케이션 배포
이클립스 에서 웹 어플리케이션 개발시 주로 Tomcat 서버를 설정했었다.

실제로 웹 프로젝트 생성시에 Tomcat 디렉토리 경로를 설정하는 순서가 있는데 이는 실제 톰캣 서버에 배포하는것이 아니라 이클립스에서 다양한 테스트 환경을 제공하고자 __톰캣 설치 디렉토리에 있는 설정 파일을 복사__ 하여 별도의 실행환경을 구성하는것이다.

만일 운영 서버에 웹 어플리케이션을 배포한다면 서버 내 톰캣 디렉토리에 해당 웹 어플리케이션을 배치시켜야 할 것이다.

즉 웹 어플리케이션 실행을 위해서는 톰캣 서버에 deployment를 해야 한다. 여기서 deployment란 간단하게 클라이언트에서 서비스를 요청했을 때 톰캣 서버가 어플리케이션을 실행 할 수 있도록 설치하는 것을 의미한다.

#### 운영 서버에 배치
실제 운영하는 서버에 배치할 때에는 배치할 파일들 (.class, resources, webContents, web.xml 등)을 하나의 웹 아카이브 파일(war)로 만들어서 배치 폴더에 복사한다.

1. application.war 파일을 준비한다.
2. tomcat_directory/webapps에 복사한다.
3. tomcat_directory/bin/startup.sh(cmd)를 실행한다.
4. webapps 디렉토리에 application 디렉토리가 생성된 것을 확인한다. 이는 applicat.war 파일을 풀어서 생성한 디렉토리 이다. 즉 톰캣 서버 실행시 webapps에 있는 .war 파일들은 자동으로 풀린다.
5. 위와 같은 배치 덕분에 서로 다른 웹 어플리케이션이 같은 톰캣 서버 위에서 같은 포트를 갖고 구동이 가능한 것 같다.(context-path로 구분 가능)

위에서 webapps가 웹 어플리케이션을 배치하는 폴더이다.












###참고 및 출처
  - 자바 웹개발 워크북
