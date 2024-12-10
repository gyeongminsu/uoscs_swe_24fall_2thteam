## **Project Title**
  시대생모여라-시대생 모임 플랫폼
  
## **Project Scope**
- 서울시립대학교 학생을 대상으로 한 모임 매칭 플랫폼을 개발합니다.
- Software Development Life-Cycle(SDLC)을 기반으로 객체지향 소프트웨어공학 방법론을 적용하는 것이 목표입니다. 
- 프로젝트를 진행하며 협업 스킬을 향상하고, 상세한 pain point 분석과 함께 사용자 중심의 설계를 진행하며, 요구사항 분석, 설계 문서(UML, UI Design 등), 코딩 표준, 테스트 케이스 등의 다양한 문서화를 진행하고자 합니다.

  
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


## **Project Deliverables

### Non-Functional Requirement
- Performance: 
2000명의 사용자가 동시에 사용할 경우, 
시스템은 2초 내로 사용자가 요구한 서비스에 대한 응답을 해야한다.
- System reliability: 
  - 시스템 가용성 95% 이상 유지, 장애 발생 시 복구 시간 1시간 이내, 데이터 일관성 유지
- Scalability: 
  - 사용자 수 12만 명 (재학생 수 * 10년)까지 지원하여 
  - 향후 10년간 DB 스케일링이 필요하지 않도록 분산 DB 설계
- Security
  - 사용자 데이터 암호화, 통신에 SSL/TLS 프로토콜 사용
  - 사용자 개인 정보는 필요한 정보만 일부 공개한다
  - 도메인 이메일 인증을 통해 재학생 인증을 진행한다.
- Maintainability
  - 코드 변경 시 테스트 커버리지 80% 이상 유지, 문서화 90% 이상 완료
- Usability
  - 사용자 인터페이스에 대한 만족도 조사에서 만족도 80%이상 달성
- Compliance
  - 관련 데이터 보호 규정 준수


### 예상 사용률
- 서울시립대 재학생 수 : 12k 이므로 DAU : 10%로 가정 시, 1200명/day
- 활동중 모임 수 : DAU/10 으로 가정 시 120개
- 모임 생성 포스트 : 활동중 모임 수 / 30 = 4개 / day
- 모임 활동 기록 포스트 : 평균 주 2회 모임 가정 시, 120*2 / 7 = 34
- 활동 기록 조회 : 1200 * 인당 평균 2개 모임 가정 * 
                        (모임 당 하루 활동 기록 2개 / 7일) * 평균 5회 조회 = 약 35,000개 / day

-> 하루 총 154건의 쓰기 작업 & 3,500개의 읽기 작업
=> 10년 기준 5.6만 건의 쓰기 작업

### Final Architecture
  ![image](https://github.com/user-attachments/assets/4c5d995c-745f-457a-a3f3-e532e423efb4)

### Class diagram
![image](https://github.com/user-attachments/assets/9a6e6973-45a8-460f-97e3-c279cc040b0e)

### Use Case
<img width="464" alt="image" src="https://github.com/user-attachments/assets/a9577249-4811-4799-9448-94a3bf2a901f">


  ### Coding Standard : 
- Commit Convention
  - Add : 클래스, 설정파일 등의 새로운 파일 추가
  - Feat : 새로운 기능 추가
  - Docs : 문서 수정
  - Test : 테스트 코드 작성
  - Chore : 기타 변경 사항(빌드 스크립트 수정 등)
  - Fix : 올바르지 않은 코드를 고친 경우
  - Update : 수정, 추가, 보완(주로 코드가 아닌 버전 업데이트)
  - Refactor : 코드의 리팩토링
  - Remove : 코드의 삭제 ex) Feat: jwt 토큰 발행 기능
- Naming Convention
  - 직관적으로 의미를 파악할 수 있도록 이름을 짓습니다 (약어 금지)
  - 변수 및 함수명은 camelCase를 사용합니다.
  - 배열의 경우 접미사로 list를 붙입니다.
  - private 변수는 _ 를 접두사로 선언합니다.
  - props로 전달되는 핸들러 함수는 on으로 시작합니다.
  - 동사와 명사가 함께 쓰이는 경우 동사 + 명사 형식으로 작성합니다.
  - 컴포넌트는 항상 PascalCase로 선언합니다.
  - inline style은 가능한 지양합니다.
- Gihub Branch Rules
  - 크게 4가지 브랜치를 사용합니다. main, develop, feature, hotfix
  - feature 브랜치는 이슈 단위로 생성되며, feature-1/user과 같이 이슈 번호와 간략한 기능 설명을 포함한 브랜치명을 생성합니다.
  - hotfix는 병합된 기능에 에러 발생 시, 에러를 수정하는 코드가 포함됩니다.
  - develop은 feature와 hotfix를 병합한 브랜치입니다. 개발 진행 시 develop을 기준으로 pull 받습니다
  - main은 develop에서 안정된 것이 확인된 기능들만 merge한 브랜치입니다. 추후 배포할 때 사용됩니다.
- Code Review Process
- Issue Rule
  - 기본 설정은, 각 팀의 리더가 issue를 작성, 팀원들에게 할 일을 배분한다.
  - 자신이 할 일에 할당된 issue가 없는 경우 리더에게 전달 후 새로 작성한다.
- PR Rule
  - 각 인원은 issue 단위로 할 일을 할당받고, 해당 issue를 구현한 후 develop branch에 PR을 올린다.
  - PR은 설정된 PR template대로 내용을 작성한다. 관련 이슈 번호, 구현한 내용, 스크린샷 등이 포함된다.
  - 각 팀(프론트 / 백엔드)의 리더가 최종적으로 코드를 리뷰한 뒤 merge를 진행한다.
    
### ERD
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


### Source code
- Frontend: https://github.com/SW-2024-fall/team-matching-client
- Bakcend: https://github.com/SW-2024-fall/team-matching-server

### Test Case & Test Results
  <img width="892" alt="image" src="https://github.com/user-attachments/assets/499635c6-569e-4905-ab07-6c8cd76ce904">


 ## **Project Constraints**
-	플랫폼 : 웹 및 모바일 어플리케이션으로 구현되며, iOS와 Android 모두 지원해야 한다.
-	언어 : 한국어 지원이 필수적이며, UI/UX 디자인은 한국어 사용자에 맞춰져야 한다.
-	보안 : 사용자 개인정보 보호가 최우선이며, 실명 인증 시스템의 안전성을 확보해야 한다.
-	데이터베이스 : 사용자 기록 및 모임 데이터를 저장하기 위한 안정적이고 확장 가능한 데이터베이스가 필요하다.



## Project Team Members
  - 2020920001 경민수 : Machine Learning
  - 2020520008 김세연 : Design, Frontend
  - 2021920006 권민재 : Frontend
  - 2021920020 김혜주 : PM, Design, Frontend, Backend
  - 2022920038 송채희 : Backend
  - 2022920060 최재원 : Frontend

  
