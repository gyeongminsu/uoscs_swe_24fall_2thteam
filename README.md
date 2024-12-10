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
- 내게 좋은 사람들을 찾아서
  - 출석 점수: 성실히 활동했는지에 대한 지표
  - 프로필 조회: 사용자의 참여 모임 및 활동 기록 조회
  - 사용자 특징: 사용자의 활동기록을 토대로 한 특징 제공
- 내게 맞는 모임을 찾아서
  - 다양한 정보: 기본 모임 정보, 모임 구성원 정보, 활동 기록
  - 시대 AI의 모임 분석: 모임 특징 분석, 모임 추천 대상 분석
  - 모임 필터링 검색
  - 시대 AI의 모임 추천: 참여한 모임과 사용자 정보 반영 
- All-In-One: 모임 모집부터 기록, 관리까지 한번에
  - 맞는 모임을 찾았다면 좋아요, 스크랩, 참여 신청까지!
  - 모임 모집: 모집글 작성, 원하는 사람 선별
  - 모임 관리: 활동 기록 작성, 출석 관리, 모임원 관리
  
## **Project Constraints**
-	플랫폼 : 웹 및 모바일 어플리케이션으로 구현되며, iOS와 Android 모두 지원해야 한다.
-	언어 : 한국어 지원이 필수적이며, UI/UX 디자인은 한국어 사용자에 맞춰져야 한다.
-	보안 : 사용자 개인정보 보호가 최우선이며, 실명 인증 시스템의 안전성을 확보해야 한다.
-	데이터베이스 : 사용자 기록 및 모임 데이터를 저장하기 위한 안정적이고 확장 가능한 데이터베이스가 필요하다.

## **High Level Architecture**
### Non-Functional Requirement
- Performance: 
2000명의 사용자가 동시에 사용할 경우, 
시스템은 2초 내로 사용자가 요구한 서비스에 대한 응답을 해야한다.

- System reliability: 
  - 시스템 가용성 95% 이상 유지, 장애 발생 시 복구 시간 1시간 이내, 데이터 일관성 유지

- Scalability: 
  - 사용자 수 12만 명 (재학생 수 * 10년)까지 지원하여 
  - 향후 10년간 DB 스케일링이 필요하지 않도록 분산 DB 설계

### 예상 사용률
- 서울시립대 재학생 수 : 12k 이므로 DAU : 10%로 가정 시, 1200명/day
- 활동중 모임 수 : DAU/10 으로 가정 시 120개
- 모임 생성 포스트 : 활동중 모임 수 / 30 = 4개 / day
- 모임 활동 기록 포스트 : 평균 주 2회 모임 가정 시, 120*2 / 7 = 34
- 활동 기록 조회 : 1200 * 인당 평균 2개 모임 가정 * 
                        (모임 당 하루 활동 기록 2개 / 7일) * 평균 5회 조회 = 약 35,000개 / day

-> 하루 총 154건의 쓰기 작업 & 3,500개의 읽기 작업
=> 10년 기준 5.6만 건의 쓰기 작업

  ![image](https://github.com/user-attachments/assets/4c5d995c-745f-457a-a3f3-e532e423efb4)


## **Project Deliverables
  ### 요구사항 분석 명세서 final version :
  ### Architecture 및 Design Documents
    - Software architecture : (차후 링크 업데이트 예정)
    - Software Design : (차후 링크 업데이트 예정)
    - UI Design : (차후 링크 업데이트 예정)
  ### Coding Standard : 
  ### Code
    - branch description
      - main: 테스트까지 모두 통과과되어 안정성까지 인증된 기능들만 모인 곳이다
      - develop: PR에서 이상이 발견되지 않은 경우 merge를 진행하는 브랜치이다. 이 브랜치를 기준으로 개발이 이뤄진다.
      - feature-[번호]/[기능]: issue 단위로 개발을 진행할 때의 브랜치이다. 완성 시 develop 브랜치로 PR을 올린다.
    - documentation
      - Facade Pattern 적용: user, meeting, history 등이 서로의 테이블과 밀접하게 관련 있고, 관련된 중간 테이블이 많이 존재하게 되어 여러 도메인 서비스가 강하게 결합되는 문제점이 발생하여 전체를 통합하는 Facade service와 각 도메인 또는 도메인-도메인별 service를 분리하였다.
      - swagger 사용: API 명세를 제공함으로써 프론트와의 소통을 용이하게 하였다.
      - themeStyle 적용: font size, color, border radius 등의 값을 단계별로 나누어 정의, 일관된 UI를 제공하였다.
    
 ### Test Case & Test Results
  <img width="892" alt="image" src="https://github.com/user-attachments/assets/499635c6-569e-4905-ab07-6c8cd76ce904">

## Repository Sturcture

  ### Frontend
- (https://github.com/SW-2024-fall/team-matching-client)
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
  - (https://github.com/SW-2024-fall/team-matching-server)
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

  [ UI/UX ]
  https://www.figma.com/design/ItTb7Q5UQPND6G0BUM9ymQ/Untitled?node-id=0-1&node-type=canvas&t=PeeQiXZ5MV4MCSlA-0
  
