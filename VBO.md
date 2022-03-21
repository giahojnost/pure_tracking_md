
## VBO 기능 설명
### Training Task 기능
- Admin에서 설정 된 Training Subjects를 노출.
- Training Subject Item
    - Complete / Undo
    - 설정된 element별로 조작 가능.
### Prospect 관리
> NOTE: 현재 있는 필드 확장함. 확장 된 부분은 DB참조, 구현시 [Benchmarking Site](https://pulsepenny.rodanandfields.com/app/daily) 참조하면서 진행.
- Prospect 병합 지원 
    - 현재 선택한 Prospect 기준으로 현재 Prospect에 없는 정보를 두번째 Prospect의 정보로 입력함
    - 두 Prospect의 정보 모두 비어 있으면 그냥 비워둠
    - 두번쨰 Prospect의 모든 기록은 첫번째 Prospect에 계승이 아니라 완전히 삭제됨.
- 프로필 이미지 지원
- 주소 기능 지원
- Categorize 기능 지원
- Status Marking 지원
- Sample 보내기 지원
### Task 관리
> NOTE: Flow 간략 설명, 구현 시 [Benchmarking Site](https://pulsepenny.rodanandfields.com/app/daily) 참조하면서 진행.
> Tag는 **아직** 지원하지 않음.
- **신규생성**
    1. Prospect 선택
    2. Schedule Date 설정(선택 OR 입력)
    3. Note 추가(Prospect Note 혹은 Task Note 중 선택)
    4. Type은 **Reachout**으로 설정 됨.
    5. Activity 테이블에 상황기록 추가.
- **Task 완료 후 생성**
    1. Prospect Status 설정
        - 임의 상태 설정 시 자동으로 Task Type가 **Followup**인 Task를 60일 후로 신규 생성 됨. (예: 3.15에 진행하면 60일 후인 5.14로 설정 된 Task가 생성 됨.)
            - Reschedule 가능함.
            - Tag/Note 추가 가능함.
        - Not Interested 시 아래 작업 진행 중지 즉 Task 생성 안함.
    4. Activity 테이블에 완료 된 Task의 activity 기록 추가.
- **Task Actions**
    - Complete / Undo
    - Rescheudle
    - Remove
    - Share
        - Share관련 설정은 task_sharing_config에 따라 진행 **예정**. 기타 내용 추가 예정
        - 현재 VBO에서 사용하고 있는 Library와 연동 예정. 방식은 아직 미정. 곧 추가 예정.
    - Contact (현재는 Email만 지원)
