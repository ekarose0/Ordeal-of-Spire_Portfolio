# [Unity2D] Ordeal-of-Spire-Portfolio-

## 소개   
(사진)   
- Unity 2D

## 개발 환경   
- Unity 2022.3.22f1 LTS
- Spine 4.2
- C#
- Window 10/11

## 메인 사용 기술
|기술|설명|
|:------:|:--------------------------|
|디자인 패턴|**싱글톤** 패턴을 사용하여 데이터 구조 관리<br>**Manager** 스크립트를 통한 하위 스크립트 관리<br>**Define**을 통한 정의 관리|
|Scriptable Object|Scriptable Object를 통한 빠른 DB관리(캐릭터, 몬스터, 맵) 및 설정|
|Save|Json을 통한 정보 저장/불러오기|
|Pool|소환되는 오브젝트는 Pool을 통한 접근 및 저장|

## 유니티 엔진 구현
### 1. Inspector 커스텀
|스크립트|결과|
|:-----:|:------|
|<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/e4a59ec1-e183-4b51-8020-4d1d985d4b76" />|<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/88a1d772-1044-48f6-8d41-83a70c14a802" />|
|<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/573dd6fc-9847-43b1-8283-eb3a170900ef" />|<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/fe452863-3b01-4259-b3db-8ff18ffd6db0" />
|

<pre><code> ==UnityEngine의 CustomEditor기능을 사용한 작업==
개발자 외의 타 개발군에서 해당 프로젝트에 쉬운 접근성과 가시성을 표시하는걸 목적으로 제작되었습니다.
버튼을 통한 기능추가 및 이미지와 프리팹등 다양한 설정값을 설정하여 이를 바탕으로 실제 게임에 적용됩니다.</code></pre>


## 시스템 구현
### 1. Scriptable Object, DB관리

|DB관리 목록|이미지|내역|
|:-----:|:------|:-----|
|몬스터|<img width="734" height="111" alt="image" src="https://github.com/user-attachments/assets/4e9f19f0-f2b5-440a-9bca-849495a19305" />|<img width="648" height="385" alt="image" src="https://github.com/user-attachments/assets/65c2855f-a666-4e8d-95b2-05c8139a1eec" />|
|스킬|<img width="524" height="119" alt="image" src="https://github.com/user-attachments/assets/87d8a5e7-7469-4de8-8569-5e8eca1fc439" />|<img width="607" height="561" alt="image" src="https://github.com/user-attachments/assets/539103d5-a36d-4877-8416-ea31614c8d4c" />|
|스테이지|<img width="850" height="128" alt="image" src="https://github.com/user-attachments/assets/027d396b-f90b-428f-8539-de32078d337c" />|<img width="646" height="431" alt="image" src="https://github.com/user-attachments/assets/1e7b3f0f-be4a-4910-8e39-1c65c220b876" />|
|아이템|<img width="628" height="135" alt="image" src="https://github.com/user-attachments/assets/3050ceca-9567-4c26-b01f-666ae7dddb31" />|<img width="645" height="259" alt="image" src="https://github.com/user-attachments/assets/7eb942d2-a22f-42dc-905a-f980c7059b8d" />|

<pre><code> ==Scriptable Object를 사용한 DB관리==
DB를 Scriptable Object를 사용하여 인게임 내에서 쉽게 관리하고 리소스를 쉽게 관리 하기위해 작성되었습니다.</code></pre>

### 2. HP시스템
|환경|이미지|
|:-----:|:------|
|피가 달경우||

### 3. 스테미너 시스템

### 4. 몬스터 탐지, 공격모드 전환

### 5. 대사 시스템

### 6. Spine 관리 및 조절

### 7. 충돌 감지<범용>

### 8. 매니저 처리 및 참조 초기화

### 9. 오브젝트 풀 관리

### 10. 오디오 매니저
