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

**Player.cpp Player.h**

![이미지4](https://user-images.githubusercontent.com/82795868/206779371-e79b0d4b-ed5e-4467-84b3-56a843c24c91.png)

Character 클래스를 상속받은 자식클래스이다.
Player와 연관있는 함수를 처리하고 담당
**(중요)착용할 무기의 데이터를 포인터로 받아옴.**
포인터를 사용하지 않으면 객체를 하나 생성하면서 전체를 가져오기때문에 생성자를 한번 더 실행하면서 문제가
생길수도 있음. 그러니 포인터를 이용해 동적으로 가져와야함

![이미지5](https://user-images.githubusercontent.com/82795868/206779372-da20b707-5d60-487f-9587-b78a61fee0fb.png)

착용한 무기의 종류는 Weapon클래스에 enum으로 정의된 WEAPONKIND 사용 

**Monster.cpp Moster.h**

Player와 마찬가지로 Character 클래스를 상속받은 자식클래스이다.
Monster와 관련있는 함수와 데이터를 처리하고 담당

![이미지10](https://user-images.githubusercontent.com/82795868/206780500-415a8d51-2aab-42ce-8c3a-36cd23a2c88e.png)

![이미지6](https://user-images.githubusercontent.com/82795868/206779374-8167ea91-eb3c-4b9a-a88c-2395e0ee87cf.png)

Monster의 개별적인 정보는 파일입출력을 통해 text파일에서 데이터를 가져옴 

**Weapon.cpp Weapon.h**

![이미지6](https://user-images.githubusercontent.com/82795868/206779374-8167ea91-eb3c-4b9a-a88c-2395e0ee87cf.png)

![이미지7](https://user-images.githubusercontent.com/82795868/206779375-9bd16e07-fdc5-4cdc-a7c4-12bd3830a7d2.png)

Weapon클래스는 객체1개의 무기의 이름 , 종류 , 데미지 ,가격을 저장
각 무기별로 Weapon을 상속받는 구조로 짜기위해 protected를 사용했으며

![이미지7](https://user-images.githubusercontent.com/82795868/206779375-9bd16e07-fdc5-4cdc-a7c4-12bd3830a7d2.png)

![이미지8](https://user-images.githubusercontent.com/82795868/206779377-afa14322-cc5d-4de1-adf5-5e88161c808c.png)



**각 무기별 클래스별로 Weapon을 상속받은 후 Attack 무기의 효과는 전부 다르게 구현하기위해
virtual을 이용하여 순수가상함수로 생성**

![이미지9](https://user-images.githubusercontent.com/82795868/206779379-56a8124c-af23-441a-935e-b15b7fdebce3.png)



실제 플레이 영상
https://youtu.be/wZTTPIDpW8A

다운로드
http://naver.me/GD5Nq9z8
