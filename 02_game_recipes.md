# MakeCode Arcade 게임 기능별 블록 레시피

## 방향키로 플레이어 움직이기

필요한 블록:

- Sprites → set player to sprite of kind Player
- Controller → move sprite with buttons
- Sprites → set stay in screen

배치:

1. on start 안에서 player 스프라이트를 만든다.
2. Controller에서 move sprite with buttons 블록을 꺼낸다.
3. 대상 스프라이트를 player로 설정한다.
4. 속도는 처음에는 vx 100, vy 100으로 둔다.
5. player가 화면 밖으로 나가지 않게 stay in screen을 켠다.

자주 틀리는 점:

- player를 만들기 전에 move sprite with buttons를 사용하면 대상이 없다.
- 적 스프라이트에 move sprite를 연결하면 적이 방향키로 움직인다.

---

## A 버튼을 누르면 총알 발사하기

필요한 블록:

- Controller → on A button pressed
- Sprites → projectile from sprite

배치:

1. on start에서 player 스프라이트를 만든다.
2. Controller에서 on A button pressed 블록을 꺼낸다.
3. 그 안에 projectile from sprite 블록을 넣는다.
4. 기준 스프라이트를 player로 설정한다.
5. 오른쪽으로 쏘려면 vx를 100, vy를 0으로 설정한다.
6. 위쪽으로 쏘려면 vx를 0, vy를 -100으로 설정한다.

자주 틀리는 점:

- vx와 vy가 모두 0이면 총알이 움직이지 않는다.
- projectile의 kind가 Projectile인지 확인해야 한다.

---

## 적과 닿으면 목숨 줄이기

필요한 블록:

- Info → set life
- Sprites → on sprite of kind Player overlaps kind Enemy
- Info → change life by
- Sprites → destroy
- Info → on life zero
- Game → game over

배치:

1. on start 안에 set life to 3을 넣는다.
2. Sprites에서 Player overlaps Enemy 이벤트를 만든다.
3. 이벤트 안에 change life by -1을 넣는다.
4. 적을 destroy 하거나 player를 시작 위치로 이동시킨다.
5. on life zero 이벤트 안에 game over를 넣는다.

자주 틀리는 점:

- enemy의 SpriteKind가 Enemy가 아니면 overlap 이벤트가 실행되지 않는다.
- 적을 없애지 않으면 계속 닿아서 목숨이 너무 빨리 줄어든다.

---

## 아이템을 먹으면 점수 올리기

필요한 블록:

- Sprites → on sprite of kind Player overlaps kind Food
- Info → change score by
- Sprites → destroy

배치:

1. 아이템 스프라이트의 kind를 Food로 설정한다.
2. Player overlaps Food 이벤트를 만든다.
3. 이벤트 안에 change score by 1을 넣는다.
4. 먹은 아이템을 destroy 한다.

자주 틀리는 점:

- 아이템을 destroy 하지 않으면 같은 아이템으로 점수가 계속 오른다.
- Food 대신 Player나 Enemy로 설정하면 이벤트가 맞지 않는다.

---

## 일정 시간마다 적 만들기

필요한 블록:

- Game → on game update every
- Sprites → set enemy to sprite of kind Enemy
- Sprites → set position
- Sprites → set velocity
- Math → pick random

배치:

1. Game에서 on game update every 1000 ms 블록을 꺼낸다.
2. 그 안에서 enemy 스프라이트를 만든다.
3. x 위치 또는 y 위치에 pick random을 사용한다.
4. set velocity로 적이 움직이게 한다.

자주 틀리는 점:

- on game update 안에서 적을 만들면 너무 많이 생성된다.
- 일정 간격 생성은 on game update every를 사용하는 것이 좋다.

---

## 타일맵에서 카메라가 플레이어를 따라가기

필요한 블록:

- Scene → set tilemap
- Sprites → set player to sprite of kind Player
- Controller → move sprite with buttons
- Scene → camera follow sprite

배치:

1. on start 안에 set tilemap을 넣는다.
2. player 스프라이트를 만든다.
3. move sprite with buttons로 player를 움직인다.
4. camera follow sprite 블록을 넣고 대상을 player로 설정한다.

자주 틀리는 점:

- 맵이 화면보다 작으면 카메라가 움직이는 것이 잘 보이지 않는다.
- camera follow sprite의 대상이 player인지 확인해야 한다.
