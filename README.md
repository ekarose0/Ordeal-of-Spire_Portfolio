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
|관련 이미지| 작성 스크립트|
|:-----:|:------:|
|<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/88a1d772-1044-48f6-8d41-83a70c14a802" />|<img width="798" height="500" alt="image" src="https://github.com/user-attachments/assets/52cf784e-4222-45e0-802e-7d4bd75f84e4" />|
|<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/f3ee5e69-6baf-4fc1-82fb-1b9b18d82088" />|<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/573dd6fc-9847-43b1-8283-eb3a170900ef" />|

<pre><code> ==UnityEngine의 CustomEditor기능을 사용한 작업==
개발자 외의 타 개발군에서 해당 프로젝트에 쉬운 접근성과 가시성을 표시하는걸 목적으로 제작하여 개발기간을 줄이는 목적으로 제작하였습니다.
버튼을 통한 기능추가 및 이미지와 프리팹등 다양한 설정값을 설정하여 이를 바탕으로 실제 게임에 적용됩니다.</code></pre>


## 시스템 구현
### 1. Scriptable Object, DB관리

|DB관리 목록|이미지|내역|
|:-----:|:------:|:-----:|
|몬스터|<img width="734" height="111" alt="image" src="https://github.com/user-attachments/assets/4e9f19f0-f2b5-440a-9bca-849495a19305" />|<img width="648" height="385" alt="image" src="https://github.com/user-attachments/assets/65c2855f-a666-4e8d-95b2-05c8139a1eec" />|
|스킬|<img width="524" height="119" alt="image" src="https://github.com/user-attachments/assets/87d8a5e7-7469-4de8-8569-5e8eca1fc439" />|<img width="607" height="561" alt="image" src="https://github.com/user-attachments/assets/539103d5-a36d-4877-8416-ea31614c8d4c" />|
|스테이지|<img width="850" height="128" alt="image" src="https://github.com/user-attachments/assets/027d396b-f90b-428f-8539-de32078d337c" />|<img width="646" height="431" alt="image" src="https://github.com/user-attachments/assets/1e7b3f0f-be4a-4910-8e39-1c65c220b876" />|
|아이템|<img width="628" height="135" alt="image" src="https://github.com/user-attachments/assets/3050ceca-9567-4c26-b01f-666ae7dddb31" />|<img width="645" height="259" alt="image" src="https://github.com/user-attachments/assets/7eb942d2-a22f-42dc-905a-f980c7059b8d" />|

<pre><code> ==Scriptable Object를 사용한 DB관리==
DB를 Scriptable Object를 사용하여 인게임 내에서 쉽게 관리하고 리소스를 쉽게 관리 하기위해 작성되었습니다.</code></pre>

### 2. 스텟 시스템
|내역|결과물|연출 관련 스크립트|
|:-----:|:------:|:-------:|
|체력|<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/023a1787-62c1-4498-869b-b5bd3b9cd2cb" />|<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/0e85ad07-041e-42e7-9908-c881f0f8f1db" />|
|스테미너|<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/308252c8-ad56-405d-9645-077987980115" />|<img width="753" height="242" alt="image" src="https://github.com/user-attachments/assets/9921fbda-d606-470a-9677-cb041218cea9" />|

<pre><code> 원형이 되는 함수를 건들이지 않고 부분 값을 가져와 넣는 방식입니다
  해당 방식으로 통해 코드의 호출을 최소화 하고 애니메이션을 통하여 연출을 추가하였습니다. </code></pre>


### 4. 탐지, 공격모드 전환
|관련 이미지|탐지 스크립트|모드 전환 스크립트|
|:-----:|:-----:|:-----:|
|<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/e7716ea9-9d0f-4ac4-8a51-d0bbafca7a77" />|<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/24ed6733-2fe3-4337-a7d2-86f56b1af907" />|<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/f513b760-5fb7-4eed-8e5e-9f3d7cfdb6f4" />|

<pre><code> 푸른색 범위에 플레이어에 잡힌다면 해당 몬스터는 탐색모드(플레이어를 계속 따라감)에서 공격모드로 전환합니다.
이때 공격을 하고 다시 ExitAttackMode를 통해 탐색모드로 전환합니다.
이 방식은 프리팹을 통해 각 몬스터마다 탐지, 공격 범위를 쉽게 설정할 수 있다는 장점이 있습니다. </code></pre>

### 5. 대사 시스템

|관련 영상 및 사진|대사 스크립트|
|:-----:|:-----:|
|<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/5ad03d33-5d64-47c5-ba2d-bff77da0b16e" /> | <img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/5ee9e1f7-708f-4446-bf16-553119e80e88" /> 
|<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/0d5eaa78-780b-4f97-8361-eae4ec4fc92b" />| <img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/6ddac05d-c69e-4cea-9061-ad38f4908478" /> |

<pre><code>JSON을 활용하여 작성된 대사 스크립트입니다
 대사의 주체가 누구인지 판단하여 스크립트에 적힌 대사가 출력됩니다. </code></pre>

### 6. Spine 관리 및 조절

|관련 이미지|관리 스크립트|
|:-----:|:-----:|
|<img width="565" height="669" alt="image" src="https://github.com/user-attachments/assets/30958044-0c67-447b-b283-7741a1f4a319" />| <img width="680" height="309" alt="image" src="https://github.com/user-attachments/assets/6fb5af0e-e857-4a84-8964-1fff0b925516" />
||<img width="739" height="156" alt="image" src="https://github.com/user-attachments/assets/c762d533-8230-4865-8fd3-a86157052096" />|

<pre><code>Spine의 애니메이션을 호출받을 경우 해당 스파인 애니메이션을 재생하며 애니메이션 출력도중 이벤트가 존재할경우 
해당 이벤트에 해당하는 함수를 출력합니다. Ex. 공격 타이밍등등 (MonsterController.cs, CharactorController.cs)</code></pre>

### 7. 충돌 감지<범용>

|감지체 스크립트|접촉판단 스크립트|
|:-----:|:-----:|
|<img width="438" height="321" alt="image" src="https://github.com/user-attachments/assets/35ed8969-8f12-4529-8bf9-ab322bc730a8" />|<img width="918" height="645" alt="image" src="https://github.com/user-attachments/assets/6a915724-909f-4925-b9dc-d4178e35947e" />|

<pre><code>충돌감지를 범용성 목적으로 제작한 스크립트입니다. 
 타 스크립트로부터 호출받아 작동되며 NPC나 스킬, 포탈등 플레이어와의 접촉시 해당 값을 접촉한 객체에게 되돌리며 접촉한 순간 해당 콜리더(스크립트 포함)에 명령을 내립니다.</code></pre>


### 8. 매니저 처리 및 참조 초기화

|상속 이미지|초기화 스크립트|
|:-----:|:-----:|
|<img width="672" height="177" alt="image" src="https://github.com/user-attachments/assets/a4f25ba2-dd9d-4d2d-9da9-129ad448f7a1" />|<img width="656" height="184" alt="image" src="https://github.com/user-attachments/assets/00cca907-6bc1-42a5-96a8-ffc0ba3e7f1e" />|
|<img width="249" height="209" alt="image" src="https://github.com/user-attachments/assets/b8d61dcb-01ce-4e87-8c70-e127302eb0fa" />|<img width="643" height="558" alt="image" src="https://github.com/user-attachments/assets/cf409cce-cfd4-4e73-bf7e-7a41b8381b32" />|

<pre><code>싱글톤을 통해 게임의 정보 데이터를 Battle~RestScene(전투 및 휴식)에서 초기화하며,
 이후 GameManager를 메인으로한 GameManger.Instance.(하위 매니저명)을 통해 각 하위 매니저로 접근하는 것을 목적으로 작성하였습니다.</code></pre>

### 9. 오브젝트 풀 관리

|오브젝트 이미지|관리 스크립트|
|:-----:|:-----:|
|<img height="500" alt="image" src="https://github.com/user-attachments/assets/6da8c08f-dce7-47ea-8616-8dc815ff49c1" />|<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/40bca22f-c412-492b-864b-2e625526743d" />|
|<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/6be637a1-a157-4b00-a116-49ad9ce74471" />|<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/3bc9b971-6d53-4fb9-b6fb-81faea0cea94" />|

<pre><code>Object들을 Pool을 통해 관리하며, 각 객체에 접근하는 것이 가능합니다.
또한, 각 오브젝트를 소환하는 메서드는 GameManager의 Pool로 접근하여 자식으로 소환하고 관리합니다</code></pre>


### 10. 오디오 매니저

|오디오관련 이미지|재생 스크립트|관리 스크립트|
|:-----:|:-----:|:-----:|
|<img width="259" height="109" alt="image" src="https://github.com/user-attachments/assets/4b4ca760-907d-4cc5-ab86-62c26dd20610" />|<img width="546" height="507" alt="image" src="https://github.com/user-attachments/assets/042ba439-71c2-4f57-a2e9-25f356a10252" />|<img width="374" height="512" alt="image" src="https://github.com/user-attachments/assets/0f021f25-ae1d-4358-9bf8-aaf9c2d38eb6" />|

<pre><code>사운드를 관리하는 매니저로, 게임내 배경음, 효과음등을 BackgroundAudio와 EventAudio로 관리하며(같은 종류의 오디오와는 중첩안됨)
중첩이 가능한 분류의 음(타격음등)이 있을 경우 AudioPool을 통해 자식으로 생성하여 관리하도록 작성하였습니다.</code></pre>

