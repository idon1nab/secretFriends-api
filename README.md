# Secret Friend (Biminchingu)

> **Note to Admission Committee:**
>
> This repository is a fork of the [Original Project Repository](https://github.com/Dallili/secretFriends-api). It has been created to provide English documentation and translated summaries. The source code and commit history remain identical to the original work, demonstrating the contribution period and development process.

![Intro Image](https://github.com/Dallili/BeMeeelFriend_front/assets/80890092/b5a1d63e-af26-4cb5-b5a6-8716fbdfeebb)

## Deployment Links
🔗 **Service URL:** https://secret-friends.link<br>
🔗 **API Test (Swagger-UI):** [Link to Swagger-UI](http://ec2-3-17-227-166.us-east-2.compute.amazonaws.com/swagger-ui/index.html)

> **Test Credentials:**
> - **ID:** `heytwinkler@gmail.com`
> - **PW:** `test123!`

## Project Overview
**"Secret Friend": An Exchange Diary Web Service to Relieve Alienation**<br>

💚 **Capstone Graduation Project**, Dept. of Computer Science & Engineering, Ewha Womans University<br>
💚 **Development Period:** Feb 2024 ~ June 2024

💬 **Motivation:** This project was initiated to address the growing social issue of depression and alienation, particularly among people in their 10s and 20s. Our market research indicated a lack of platforms that encourage sincere, deep personal storytelling. We designed "Secret Friend" as an exchange diary web service to serve as a communication channel for sharing genuine inner thoughts.

💬 **Key Features:** Unlike existing diary services, this platform provides a **Random Matching System** that allows users to share diaries with anonymous partners. It also features **AI-based Sentiment Analysis**, providing users with objective reports and feedback on the emotions expressed in their entries.

## Team Members

<table>
    <tr height="160px">
        <td align="center" width="200px">
            <a href="https://github.com/idon1nab"><img height="150px" width="150px" src="https://avatars.githubusercontent.com/u/99960721?v=4"/></a>
            <br />
        </td>
        <td align="center" width="200px">
            <a href="https://github.com/rwaeng"><img height="150px" width="150px" src="https://avatars.githubusercontent.com/u/80890092?v=4"/></a>
            <br />
        </td>
         <td align="center" width="200px">
            <a href="https://github.com/crHwang0822"><img height="150px" width="150px" src="https://avatars.githubusercontent.com/u/87927105?v=4"/></a>
            <br />
        </td>
    </tr>
    <tr height="60px">
        <td align="center">
        <a>Minji Kwak</a><br>
            <a href="https://github.com/idon1nab">:octocat: GitHub</a>
            <br />
        </td>
        <td align="center">
        <a>Aryoung Jo</a><br>
            <a href="https://github.com/rwaeng">:octocat: GitHub</a>
            <br />
        </td>
        <td align="center">
        <a>Chaerin Hwang</a><br>
            <a href="https://github.com/crHwang0822">:octocat: GitHub</a>
            <br />
         </td>
    </tr>
</table>

## 🔗 ERD (Entity Relationship Diagram)
![image](https://github.com/Dallili/secretFriends-api/assets/87927105/ee10869b-fd85-4249-9d93-c5511520b8b4)

## ⚙️ Tech Stack
**Environment**

<img src="https://img.shields.io/badge/intellij-000000?style=for-the-badge&logo=intellij idea&logoColor=white"> <img src="https://img.shields.io/badge/git-F05032?style=for-the-badge&logo=git&logoColor=white"> <img src="https://img.shields.io/badge/github-181717?style=for-the-badge&logo=github&logoColor=white">

**Language**

<img src="https://img.shields.io/badge/java-007396?style=for-the-badge&logo=java&logoColor=white">

**Development**

<img src="https://img.shields.io/badge/springboot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white"> <img src="https://img.shields.io/badge/mariaDB-003545?style=for-the-badge&logo=mariaDB&logoColor=white"> <img src="https://img.shields.io/badge/gradle-02303A?style=for-the-badge&logo=gradle&logoColor=white">

**Deploy**

<img src="https://img.shields.io/badge/route 53-8C4FFF?style=for-the-badge&logo=amazon route 53&logoColor=white"> <img src="https://img.shields.io/badge/amazonec2-FF9900?style=for-the-badge&logo=amazonec2&logoColor=white"> <img src="https://img.shields.io/badge/amazonrds-527FFF?style=for-the-badge&logo=amazonrds&logoColor=white"> 

**CI/CD**

<img src="https://img.shields.io/badge/github actions-2088FF?style=for-the-badge&logo=github actions&logoColor=white"> <img src="https://img.shields.io/badge/docker-2496ED?style=for-the-badge&logo=docker&logoColor=white">

## 🏠 System Architecture
![image](https://github.com/Dallili/secretFriends-api/assets/99960721/8572f509-416b-4b2d-b939-ffdbaf678495)

## 🔧 External Libraries & Modules
📍 **Project Vane's bad-word-filtering Library**
- Used to implement profanity filtering within diary entries.
- [Repository Link](https://github.com/VaneProject/bad-word-filtering.git)
  
📍 **OpenAI ChatGPT API**
- Used to implement the sentiment analysis feature for user diaries.
- Utilized **few-shot prompting** to analyze the user's diary entry and system prompts.

## 🚀 How to start
#### 💻 Running the API Server Locally
1. Clone the Spring Boot Project<br><br>
   ```
   git clone https://github.com/Dallili/secretFriends-api.git
   ```
2. Configure application.yml<br><br>
   ```
   spring:
    # Database Configuration
     datasource:  
       driver-class-name: org.mariadb.jdbc.Driver
       url: jdbc:mariadb://localhost:3306/secretfriends
       username: # username 
       password: # password 
    
     jpa:
       hibernate:
         ddl-auto: update
         format_sql: true
         show-sql: true
    
     logging:
       level:
         org:
           springframework: info
           dallili: debug
    
    # JWT Token Configuration
     jwt:
       secret: # JWT Secret Key (ex. secretfriendsaksf1231skdjlfa)
    
    # OpenAI API Configuration
     openai:
       organization: 
         id: # OPENAI ORGANIZATION ID
       project: 
         id: # OPENAI PROJECT ID
       api: 
         key: # Your OpenAI API Key
         url: [https://api.openai.com/v1/chat/completions](https://api.openai.com/v1/chat/completions)
       model: # Model to use (ex. gpt-3.5-turbo)
    
    # Email Verification Configuration (Gmail SMTP)
     mail:
       host: smtp.gmail.com
       port: 587
       username: # Google Email Address
       password: # Google App Password
       properties:
         mail:
           smtp:
             starttls:
               enable: true
             auth: true
           debug: true
       templates:
         path: templates/email/
         img:
           logo: /static/logo.png
           title: /static/title.png
           text: /static/text.png

   ```
3. Run the Project

#### 🌏 Running the API Server on AWS
1. Create a Remote Repository via Git Fork
2. Configure Environment Variables via GitHub Actions Secrets<br><br>
    <table> <thead> <tr> <th>Secret Name</th> <th>Value</th> </tr> </thead> <tbody> <tr> <td>AWS_EC2_HOST</td> <td>{EC2 Public IP Address}</td> </tr> <tr> <td>AWS_EC2_KEY</td> <td>{EC2 Key Pair Content (.pem)}</td> </tr> <tr> <td>AWS_RDS_HOST</td> <td>{RDS Endpoint}</td> </tr> <tr> <td>AWS_RDS_PASSWORD</td> <td>{RDS Password}</td> </tr> <tr> <td>AWS_RDS_USERNAME</td> <td>{RDS Username}</td> </tr> <tr> <td>DOCKER_PASSWORD</td> <td>{Docker Hub Password}</td> </tr> <tr> <td>DOCKER_REPOSITORY</td> <td>{Docker Repository Name}</td> </tr> <tr> <td>DOCKER_USERNAME</td> <td>{Docker Hub Username}</td> </tr> <tr> <td>JWT_SECRET_KEY</td> <td>{JWT Secret Key}</td> </tr> <tr> <td>MAIL_LOGO_PATH</td> <td>/static/logo.png</td> </tr> <tr> <td>MAIL_PASSWORD</td> <td>{Google App Password}</td> </tr> <tr> <td>MAIL_TEMPLATE_PATH</td> <td>templates/email/</td> </tr> <tr> <td>MAIL_TEXT_PATH</td> <td>/static/text.png</td> </tr> <tr> <td>MAIL_TITLE_PATH</td> <td>/static/logo.png</td> </tr> <tr> <td>MAIL_USERNAME</td> <td>{Google Email Address}</td> </tr> <tr> <td>OPENAI_API_KEY</td> <td>{OpenAI API Key}</td> </tr> <tr> <td>OPENAI_API_URL</td> <td>https://api.openai.com/v1/chat/completions</td> </tr> <tr> <td>OPENAI_MODEL</td> <td>gpt-3.5-turbo</td> </tr> <tr> <td>OPENAI_ORGANIZATION_ID</td> <td>{OpenAI Organization ID}</td> </tr> <tr> <td>OPENAI_PROJECT_ID</td> <td>{OpenAI Project ID}</td> </tr> </tbody> </table>
3. Trigger the GitHub Actions Workflow




---

   




![소개이미지](https://github.com/Dallili/BeMeeelFriend_front/assets/80890092/b5a1d63e-af26-4cb5-b5a6-8716fbdfeebb)

## 배포 주소
🔗 https://secret-friends.link<br>
🔗 [Swagger-UI 를 통한 API 테스트](http://ec2-3-17-227-166.us-east-2.compute.amazonaws.com/swagger-ui/index.html)
```
- 테스트 계정 ID: heytwinkler@gmail.com
- 테스트 계정 pw: test123!
```
## 프로젝트 개요
**속마음을 담은 일기 교환을 통해 현대인의 소외감 해소를 돕는 교환일기 웹 서비스 <비밀친구>**<br>

💚 이화여대 컴퓨터공학전공 캡스톤 졸업프로젝트<br>
💚 개발 기간: 2024.02 ~ 2024.06

💬 우울증 환자가 증가하는 상황으로 특히 10대부터 20대까지의 우울감 및 소외감에 집중해서 이러한 사회적 문제를 해결하고자 프로젝트를 시작했다. SNS 시장 조사 결과 개인의 진솔한 이야기를 이끌어내는 소통창구가 될만한 서비스가 부재한 상황이라 판단했고 깊은 이야기를 나눌 수 있는 소통창구로서 교환일기 웹 서비스를 고안했다. 

💬 기존에 존재하는 일기 서비스와는 다르게 익명의 유저와 일기를 공유할 수 있는 랜덤 매칭 기능을 제공하며 사용자들이 작성한 일기에 대한 감정 분석 레포트를 제공한다.

## 팀원 소개

<table>
    <tr height="160px">
        <td align="center" width="200px">
            <a href="https://github.com/idon1nab"><img height="150px" width="150px" src="https://avatars.githubusercontent.com/u/99960721?v=4"/></a>
            <br />
        </td>
        <td align="center" width="200px">
            <a href="https://github.com/rwaeng"><img height="150px" width="150px" src="https://avatars.githubusercontent.com/u/80890092?v=4"/></a>
            <br />
        </td>
         <td align="center" width="200px">
            <a href="https://github.com/crHwang0822"><img height="150px" width="150px" src="https://avatars.githubusercontent.com/u/87927105?v=4"/></a>
            <br />
        </td>
    </tr>
    <tr height="60px">
        <td align="center">
        <a>곽민지</a><br>
            <a href="https://github.com/idon1nab">:octocat: GitHub</a>
            <br />
        </td>
        <td align="center">
        <a>조아령</a><br>
            <a href="https://github.com/rwaeng">:octocat: GitHub</a>
            <br />
        </td>
        <td align="center">
        <a>황채린</a><br>
            <a href="https://github.com/crHwang0822">:octocat: GitHub</a>
            <br />
         </td>
    </tr>
</table>

## 🔗 ERD
![image](https://github.com/Dallili/secretFriends-api/assets/87927105/ee10869b-fd85-4249-9d93-c5511520b8b4)

## ⚙️ 기술 스택
**Environment**

<img src="https://img.shields.io/badge/intellij-000000?style=for-the-badge&logo=intellij idea&logoColor=white"> <img src="https://img.shields.io/badge/git-F05032?style=for-the-badge&logo=git&logoColor=white"> <img src="https://img.shields.io/badge/github-181717?style=for-the-badge&logo=github&logoColor=white">

**Language**

<img src="https://img.shields.io/badge/java-007396?style=for-the-badge&logo=java&logoColor=white">

**Development**

<img src="https://img.shields.io/badge/springboot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white"> <img src="https://img.shields.io/badge/mariaDB-003545?style=for-the-badge&logo=mariaDB&logoColor=white"> <img src="https://img.shields.io/badge/gradle-02303A?style=for-the-badge&logo=gradle&logoColor=white">

**Deploy**

<img src="https://img.shields.io/badge/route 53-8C4FFF?style=for-the-badge&logo=amazon route 53&logoColor=white"> <img src="https://img.shields.io/badge/amazonec2-FF9900?style=for-the-badge&logo=amazonec2&logoColor=white"> <img src="https://img.shields.io/badge/amazonrds-527FFF?style=for-the-badge&logo=amazonrds&logoColor=white"> 

**CI/CD**

<img src="https://img.shields.io/badge/github actions-2088FF?style=for-the-badge&logo=github actions&logoColor=white"> <img src="https://img.shields.io/badge/docker-2496ED?style=for-the-badge&logo=docker&logoColor=white">

## 🏠 서비스 아키텍처
![image](https://github.com/Dallili/secretFriends-api/assets/99960721/8572f509-416b-4b2d-b939-ffdbaf678495)

## 🔧 사용한 외부 모듈
📍 **Project Vane의 bad-word-filtering 라이브러리**
- 일기 속 비속어 필터링 기능 구현을 위해 사용
- https://github.com/VaneProject/bad-word-filtering.git
  
📍**OpenAI의 ChatGPT API**
- 사용자가 작성한 일기에 대한 감정 분석 기능 구현을 위해 사용
- few-shot prompting을 통해 사용자가 작성한 일기와 명령 프롬프트 전

## 🚀 How to start
#### 💻 로컬 환경에서  API 서버 실행 방법
1. Git clone 을 통한 스프링 부트 프로젝트 생성<br><br>
   ```
   git clone https://github.com/Dallili/secretFriends-api.git
   ```
2. application.yml 설정<br><br>
   ```
   spring:
   # 데이터베이스 설정
    datasource:  
      driver-class-name: org.mariadb.jdbc.Driver
      url: jdbc:mariadb://localhost:3306/secretfriends
      username: # username 
      password: # password 

    jpa:
      hibernate:
        ddl-auto: update
        format_sql: true
        show-sql: true
  
    logging:
      level:
        org:
          springframework: info
          dallili: debug

   # JWT 토큰 사용을 위한 키 설정
    jwt:
      secret: # JWT 시크릿 키 (ex. secretfriendsaksf1231skdjlfa)

   # OpenAI API 사용을 위한 설정
    openai:
      organization: 
        id: # OPENAI ORGANIZATION ID
      project: 
        id: # OPENAI PROJECT ID
      api: 
        key: # 발급받은 API 키
        url: https://api.openai.com/v1/chat/completions
      model: # 사용할 모델 (ex. gpt-3.5-turbo)

   # 회원가입 시 인증 메일 발송 기능을 위한 설정
    mail:
      host: smtp.gmail.com
      port: 587
      username: # 구글 이메일
      password: # 발급받은 앱 비밀번호
      properties:
        mail:
          smtp:
            starttls:
              enable: true
            auth: true
          debug: true
      templates:
        path: templates/email/
        img:
          logo: /static/logo.png
          title: /static/title.png
          text: /static/text.png

   ```
3. 프로젝트 실행

#### 🌏 AWS 환경에서 API 서버 실행 방법
1. Git fork 을 통한 원격 저장소 생성
2. Github Actions 의 Secrets 를 통한 환경 변수 설정<br><br>
    <table>
      <thead>
        <tr>
          <th>Secrets 이름</th>
          <th>들어가야 하는 값</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>AWS_EC2_HOST</td>
          <td>{EC2 퍼블릭 IP 주소}</td>
        </tr>
        <tr>
          <td>AWS_EC2_KEY</td>
          <td>{EC2 키페어 (.ppk -> .pem 변환한 파일의 내용)}</td>
        </tr>
        <tr>
          <td>AWS_RDS_HOST</td>
          <td>{RDS 엔드포인트}</td>
        </tr>
        <tr>
          <td>AWS_RDS_PASSWORD</td>
          <td>{RDS 패스워드}</td>
        </tr>
        <tr>
          <td>AWS_RDS_USERNAME</td>
          <td>{RDS 유저네임}</td>
        </tr>
        <tr>
          <td>DOCKER_PASSWORD</td>
          <td>{Docker 패스워드}</td>
        </tr>
        <tr>
          <td>DOCKER_REPOSITORY</td>
          <td>{Docker 리포지토리명}</td>
        </tr>
        <tr>
          <td>DOCKER_USERNAME</td>
          <td>{Docker 유저네임}</td>
        </tr>
        <tr>
          <td>JWT_SECRET_KEY</td>
          <td>{JWT 시크릿 키}</td>
        </tr>
        <tr>
          <td>MAIL_LOGO_PATH</td>
          <td>/static/logo.png</td>
        </tr>
        <tr>
          <td>MAIL_PASSWORD</td>
          <td>{구글에서 발급받은 앱 비밀번호}</td>
        </tr>
        <tr>
          <td>MAIL_TEMPLATE_PATH</td>
          <td>templates/email/</td>
        </tr>
        <tr>
          <td>MAIL_TEXT_PATH</td>
          <td>/static/text.png</td>
        </tr>
        <tr>
          <td>MAIL_TITLE_PATH</td>
          <td>/static/logo.png</td>
        </tr>
        <tr>
          <td>MAIL_USERNAME</td>
          <td>{구글 이메일}</td>
        </tr>
        <tr>
          <td>OPENAI_API_KEY</td>
          <td>{OpenAI 에서 발급받은 API 키}</td>
        </tr>
        <tr>
          <td>OPENAI_API_URL</td>
          <td>https://api.openai.com/v1/chat/completions</td>
        </tr>
        <tr>
          <td>OPENAI_MODEL</td>
          <td>gpt-3.5-turbo</td>
        </tr>
        <tr>
          <td>OPENAI_ORGANIZATION_ID</td>
          <td>{OpenAI Organization ID}</td>
        </tr>
        <tr>
          <td>OPENAI_PROJECT_ID</td>
          <td>{OpenAI Project ID}</td>
        </tr>
      </tbody>
    </table>
3. Github Actions Workflow 실행

