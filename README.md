## **Project Title**
  시대생모여라-시대생 모임 플랫폼
  
## **Project Scope**
- 서울시립대학교 학생을 대상으로 한 모임 매칭 플랫폼을 개발합니다.
- Software Development Life-Cycle(SDLC)을 기반으로 객체지향 소프트웨어공학 방법론을 적용하는 것이 목표입니다. 
- 프로젝트를 진행하며 협업 스킬을 향상하고, 상세한 pain point 분석과 함께 사용자 중심의 설계를 진행하며, 요구사항 분석, 설계 문서(UML, UI Design 등), 코딩 표준, 테스트 케이스 등의 다양한 문서화를 진행하고자 합니다.

## Project Team Members
  - 2020920001 경민수 : Machine Learning
  - 2020520008 김세연 : Design, Frontend
  - 2021920006 권민재 : Frontend
  - 2021920020 김혜주 : PM, Design, Frontend, Backend
  - 2022920038 송채희 : Backend
  - 2022920060 최재원 : Frontend

## **Technology Stacks**
  - 협업 툴 : Notion, Github, Slack \
  - Machine Learning : Google Gemini API
  - Design : Figma
  - Frontend : React Native
  - Backend : JAVA Spring boot

## **Project Duration**
  2024년 2학기 (2024.09-11)

## **Highlighted Features**
  (발표자료 완성 후 그에 따라 작성 예정)
  
## **Project Constraints**
  (논의 후 작성 예정)
  
## **High Level Architecture**
  (사진 첨부 예정)

## **Installation guideline**
  (추후 작성 예정)

## **Project Deliverables
  ### 요구사항 분석 명세서 final version :
  ### Architecture 및 Design Documents
    - Software architecture : (차후 링크 업데이트 예정)
    - Software Design : (차후 링크 업데이트 예정)
    - UI Design : (차후 링크 업데이트 예정)
  ### Coding Standard : 
  ### Code
    - branch description
    - documentation
    
  ### Test Case & Test Results

## Repository Sturcture

  ### Frontend
  - assets: 정적인 파일들을 저장한다.
  - context: authContext (token, user info) 등 전역적으로 전달할 값들을 전달한다.
  - hooks: 공통 hooks를 정의한다.
  - layout: 전체에 적용될 페이지별 레이아웃을 정의한다
    - appbar, header, layout
  - navigation: 페이지 라우팅을 정의한다.
  - styles: 공통 스타일 (ThemeStyle)을 정의한다.
  - utils: 공용 fetch 함수 및 도메인별 api 호출 함수
  - pages: 구현해야하는 페이지별 폴더로 존재한다.
    - auth, main, meeting, meetingBoard, meeting, meetingHistory, profile, recommend

  ### Backend
- common
- dto, entity, enums, exception, message folder: 공통으로 사용되는 클래스들 모음
core
- config: AwsS3, Gemini, Security, Swagger config 클래스 모음
- jwt: JwtProvider, JwtFilter 등 jwt 관련 클래스들 모음
- gemini: gemini 사용 클래스 모음
domain
- auth, user, file, comment, history, meeting, scrap, like: 각 도메인별로 폴더를 갖는다.
- 각 도메인별 controller, model, repository, service 폴더를 갖는다.
- service는 Facade Pattern을 사용하여 Facade Service와 sophisticated service (특히 다른 도메인과 연결되는 service)를 갖는다.
- model은 dto, entity, enums, exception, mapper(dto<->entity) 폴더를 갖는다.
    

## ERD
|table|description|
|-----|-------------------------------|
|users|이메일, 전공, 학번, 비밀번호, 이름, 특징, 선호 카테고리 등의 사용자 정보를 젖아하는 테이블입니다.|
|meetings|모임 게시 정보 (제목, 글, 사진)과 모임 자체에 대한 정보 (카테고리, 특징, 장소, 시간 등)  등을 저장하는 테이블입니다.|
|files|users, meetings, histories의 FK를 가지며, 유저 프로필, 모임 썸네일, 활동 내역 사진 등의 정보를 저장하는 데 사용됩니다.|
|histories|모임의 활동 기록을 저장하는 테이블입니다. 제목, 내용, 모임 진행 정보를 저장합니다.|
|comments|모임 모집글에 작성되는 댓글을 저장하는 테이블입니다. depth는 최대 2까지 지원되어, 대댓글을 단 경우 parent_comment_id를 갖게 됩니다.|
|attendance_history|활동 기록에서 작성되는 모임원들의 출석 내역을 저장하는 테이블입니다. 무단 지각 및 결석의 경우에는 해당 모임원의 출석 점수가 감점되고, 정상 출석 시 점수가 복구됩니다.|
|meeting_member|모임의 모임원들을 저장하는 테이블로, meetings와 users에 대한 FK와 해당 모임에서의 role을 attribute로 가집니다.|
|users_meeting_likes|모임에 대한 좋아요를 저장하는 테이블입니다.|
|user_meeting_scraps|모임에 대한 스크랩을 저장하는 테이블입니다.|
![image](https://github.com/user-attachments/assets/87e63aab-2da1-4dac-baa0-e126ff857107)

  
## **Project Description**
  [ Pain Point ]

- 새로운 사람들을 만나고 싶은데 기존 앱들은 **신뢰성**은 떨어짐
- 나와 비슷한 사람들과 어울리고 싶은데, 범위가 너무 넓음
- 모임의 기록과 모집 및 활동을 한번에 할 수 있는 곳이 없음
- 무슨 모임이 내게 적합할지 모르겠음

[ Target ]

- 신뢰성 있는 사람들과 어울리고 싶은 사람
- 모임 관련된 모든 것을 하나의 앱으로 해결하고 싶은 사람
- 나와 잘 맞는 사람과 모임을 찾고 싶은 사람

[ Differences ]

  - 내게 좋은 사람들을 찾아서
      - 실명제
  - 모임에 대한 추가 정보를 제공한다
      - 지각 및 무단 결석 등에 대한 기록을 남겨 신뢰성을 높인다
      - 구성원이 진행한 모임 내역 및 특징
      - 구성원의 특징
      - 특징들을 토대로 새로 개설하는 모임의 특징을 예측해서 제공한다 ⇒ ‘친목’ ‘학술적’ (부가 기능)
      - 직접 적을 수 있다.
- 에타나 myUOS와 무엇이 다를까? ⇒ ‘모임’에 초점을 맞춘다.

[ 주요 기능 ]

- 모임에 대한 추가 정보를 제공
    - 이 모임의 신뢰도 → 모임장 & 팀원의 신뢰도 총합
    - 특징 → #직접 설정 #이제까지 진행한 모임 특징 #개개인의 특징들 종합
    - 구성원이 진행한 모임 내역 및 특징
    - 구성원의 특징
    - 특징들을 토대로 새로 개설하는 모임의 특징을 예측해서 제공한다 ⇒ ‘친목’ ‘학술적’ (부가 기능)
    - 직접 적을 수 있다.
- 모임에 대한 기록
    - 누가 지각을 했다, 불참을 했다
    - 무슨 활동을 했는지 → 모임의 특징이 추출
        - 공개 / 비공개
    - 모임의 특징을 토대로 개인의 특징
    - 해당 기록은 개개인의 프로필을 통해 접근 가능하다.
- 모임 매칭
    1. 모집 글을 올린다.
    2. 모집 글 게시판에서 원하는 모임을 찾을 수 있다
    3. 모임 매칭 기능을 사용해 적합한 모임을 추천받을 수 있다
    - 즉석 모임 매칭
    - 주기적인 모임 매칭
  
