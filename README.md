# TextRPG

C++ 을 활용해서 Text형식으로만든 RPG게임입니다.

**클래스 구성**

![RPG 클래스](https://user-images.githubusercontent.com/82795868/206779508-655f857a-0573-4aa4-b2d6-8cffe04a743f.png)

**소스.cpp**

![이미지1](https://user-images.githubusercontent.com/82795868/206779364-612c4d5e-dce7-4c6e-a3de-9a915e4c6413.png)

Player1이라는 객체를 1개 생성하여 게임시작


**GameManager.cpp  GameManager.h**

![이미지2](https://user-images.githubusercontent.com/82795868/206779366-a2981341-d670-42c2-8142-23e21894443c.png)

Player는 1명이기때문에 단일객체로 Monster는 여러종류이기때문에  Vector로 MosterList 관리
**Vector를 사용한 이유는 List에 비해 각 원소에 접근하기 쉽고 
추가 및 삭제가 빈번하게 일어나지 않기때문에 Vector를 무리 없이 사용할 수 있다고 판단하여 Vector사용**
게임의 흐름에 맞춰서 DrawManager를 통해 화면을 그리는 함수를 호출
Shop 객체를 하나 생성하여 상점관리

**Character.cpp Character.h**

![이미지3](https://user-images.githubusercontent.com/82795868/206779368-cfa55bbf-2757-4c17-ab67-8453477ad7cc.png)

Character클래스는 Player와 Monster의 부모클래스이기때문에 멤버변수를 protected로 선언해주엇고
캐릭터(유저와 몬스터 둘 다 포함)의 이름 / 데미지 / HP / 경험치 등 캐릭터가 필요한 데이터를 가지고 있다.
**Character클래스는 1명의 데이터만 정의함.**




실제 플레이 영상
https://youtu.be/wZTTPIDpW8A

다운로드
http://naver.me/GD5Nq9z8
