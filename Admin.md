## Admin 기능 설명
### Training Subject 관리
1. Training Subject 관리
    - NOTE: Training Subject 생성 시 선행 Subject 선택 가능(Auto-complete지원) 
    - 해당 Subject가 완료되기 전에는 해당 Subject는 표기하지 않거나 혹은 조작(완료/미완료 상태변경)불가 상태.
2. Training Subject 소속 Item 관리
    - Item은 중복사용이 가능함
    - 소속 선택 시 신규생성 혹은 기존에서 선택
3. Training Subject 소속 Item 소속 Element 관리
    - Element는 중복사용이 가능함
    - 리소스타입 지정 및 리소스 업로드
    - 소속 선택 시 신규생성 혹은 기존에서 선택
### Training Subject 리포트
- 조건(Form)
    - Subject 선택 ( Auto-complete )
    - 타입(Type) 선택 ( Options: Details|Summary )
        - Details => 조건에 부합되는 전체 회원
        - Summary => 조건에 부합되는 회원수
    - 참여일 지정 ( Date Range )
    - 완료일 지정 ( Date Range )
    - 완료 퍼센티지 지정 
        - Operation(비교부호) 선택 가능
            - Greater than ( > )
            - Greater than or Equals to ( >= )
            - Equals to ( = )
            - Less than or Equals to ( <= )
            - Less than ( < )
        - 퍼센티지 입력(or 선택) 가능(0%-100% Unsigned Integer만)
- 결과항목
    - 회원 #
    - 가입일
    - 완료 % ( 해당 값은 회원별로 Training Subject Item 완료/미완료 시 DB에 저장되어야 함. )
    - Completed 날짜
    - 해당 Subject 완료일 - 해당 Subject 완료 시 위에 항목이랑 값이 같을것, 미 완료시 값 없음.
    - 완료 Subject Item 수 ( 예: 10개 중 5개 완료일 경우 5/10으로 표기 )

### Training Type 관리
- 추가 / 변경
- 삭제 불가
### Training Element Type 관리
- 추가 / 변경
- 삭제 불가
### Prospect Status 관리
- 추가 / 변경
- 삭제 가능
    - ID: 1은 Default 값으로 삭제 불가. 
    - 삭제 전 해당 값을 가진 모든 기록을 기본값(ID: 1)로 변경.
    - Relation Tables: rep_prospects
### Prospect Category 관리
- 추가 / 변경
- 삭제 가능
    - ID: 0은 Default 값으로 변경/삭제 불가. 
    - 삭제 전 해당 값을 가진 모든 기록을 기본값(ID: 0)로 변경.
    - Relation Tables: rep_prospects
### Task Type 관리
- 추가 / 변경
- 삭제 불가
### Task Activity Type 관리
- 추가 / 변경
- 삭제 불가

### Task Sharing Configuration 관리
- 진행중
