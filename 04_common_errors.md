# MakeCode Arcade 학생들이 자주 틀리는 점

## 1. SpriteKind가 맞지 않음

문제:

Player overlaps Enemy 이벤트를 만들었는데 실행되지 않는다.

원인:

적 스프라이트의 kind가 Enemy가 아닐 수 있다.

해결:

적을 만들 때 반드시 kind를 Enemy로 설정한다.

---

## 2. 변수를 만들기 전에 사용함

문제:

move sprite with buttons 블록에서 대상 스프라이트가 이상하다.

원인:

player 변수를 만들기 전에 이동 블록을 사용했을 수 있다.

해결:

on start 안에서 먼저 player 스프라이트를 만든 뒤 move sprite with buttons를 넣는다.

---

## 3. on game update 안에서 스프라이트를 계속 만듦

문제:

적이 너무 많이 생겨서 게임이 느려진다.

원인:

on game update는 매우 자주 실행된다.

해결:

일정 시간마다 적을 만들고 싶으면 on game update every를 사용한다.

---

## 4. 총알이 움직이지 않음

문제:

A 버튼을 눌렀는데 총알이 제자리에 있다.

원인:

projectile의 vx와 vy가 모두 0일 수 있다.

해결:

오른쪽 발사는 vx 100, vy 0  
왼쪽 발사는 vx -100, vy 0  
위쪽 발사는 vx 0, vy -100  
아래쪽 발사는 vx 0, vy 100

---

## 5. 점수가 계속 올라감

문제:

아이템 하나를 먹었는데 점수가 계속 오른다.

원인:

아이템을 destroy 하지 않아서 player와 계속 overlap 상태일 수 있다.

해결:

점수를 올린 뒤 아이템 스프라이트를 destroy 한다.

---

## 6. 벽을 통과함

문제:

타일맵을 만들었는데 플레이어가 벽을 통과한다.

원인:

타일맵에서 해당 타일을 wall로 설정하지 않았을 수 있다.

해결:

타일맵 편집기에서 벽으로 사용할 타일에 wall 속성을 켠다.

---

## 7. 카메라가 안 따라옴

문제:

플레이어가 움직이는데 화면이 따라오지 않는다.

원인:

camera follow sprite 블록이 없거나 대상이 잘못되었을 수 있다.

해결:

Scene의 camera follow sprite 블록을 넣고 대상을 player로 설정한다.
