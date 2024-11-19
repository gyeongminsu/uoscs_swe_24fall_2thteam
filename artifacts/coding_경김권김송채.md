# Coding Convention
## Commit Convention
- Add : 클래스, 설정파일 등의 새로운 파일 추가
- Feat : 새로운 기능 추가
- Docs : 문서 수정
- Test : 테스트 코드 작성
- Chore : 기타 변경 사항(빌드 스크립트 수정 등)
- Fix : 올바르지 않은 코드를 고친 경우
- Update : 수정, 추가, 보완(주로 코드가 아닌 버전 업데이트)
- Refactor : 코드의 리팩토링
- Remove : 코드의 삭제
ex) Feat: jwt 토큰 발행 기능

## Naming Convention
- 직관적으로 의미를 파악할 수 있도록 이름을 짓습니다 (약어 금지)
- 변수 및 함수명은 camelCase를 사용합니다.
- 배열의 경우 접미사로 list를 붙입니다.
- private 변수는 _ 를 접두사로 선언합니다.
- props로 전달되는 핸들러 함수는 on으로 시작합니다.
- 동사와 명사가 함께 쓰이는 경우 동사 + 명사 형식으로 작성합니다.
- 컴포넌트는 항상 PascalCase로 선언합니다.
- inline style은 가능한 지양합니다.


# Gihub Branch Rules
- 크게 4가지 브랜치를 사용한다. main, develop, feature, hotfix
- feature 브랜치는 이슈 단위로 생성되며, feature-1/user과 같이 이슈 번호와 간략한 기능 설명을 포함한 브랜치명을 생성한다.
- hotfix는 병합된 기능에 에러 발생 시, 에러를 수정하는 코드가 포함된다.
- develop은 feature와 hotfix를 병합한 브랜치이다. 개발 진행 시 develop을 기준으로 pull 받는다
- main은 develop에서 안정된 것이 확인된 기능들만 merge한 브랜치이다. 추후 배포할 때 사용된다.

# Code Review Process
## Issue Rule
- 기본 설정은, 각 팀의 리더가 issue를 작성, 팀원들에게 할 일을 배분한다.
- 자신이 할 일에 할당된 issue가 없는 경우 리더에게 전달 후 새로 작성한다.

## PR Rule
- 각 인원은 issue 단위로 할 일을 할당받고, 해당 issue를 구현한 후 develop branch에 PR을 올린다.
- PR은 설정된 PR template대로 내용을 작성한다. 관련 이슈 번호, 구현한 내용, 스크린샷 등이 포함된다.
- 각 팀(프론트 / 백엔드)의 리더가 최종적으로 코드를 리뷰한 뒤 merge를 진행한다.
