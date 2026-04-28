# MakeCode Arcade 핵심 블록 정리

이 문서는 학생에게 MakeCode Arcade 블록을 안내할 때 사용하는 기본 지식이다.

## Sprites

사용 상황:

- 플레이어 만들기
- 적 만들기
- 아이템 만들기
- 총알 만들기
- 스프라이트끼리 닿았을 때 처리하기

대표 블록:

- set mySprite to sprite of kind Player
- set position
- set velocity
- destroy
- on sprite of kind Player overlaps kind Enemy
- projectile from sprite

학생 안내 예시:

플레이어, 적, 아이템, 총알은 모두 스프라이트다.  
스프라이트끼리 닿았을 때는 Sprites의 overlap 이벤트를 사용한다.

## Controller

사용 상황:

- 방향키 이동
- A 버튼 입력
- B 버튼 입력
- 버튼을 누르고 있는지 확인

대표 블록:

- move sprite with buttons
- on A button pressed
- on B button pressed

학생 안내 예시:

플레이어를 방향키로 움직이려면 Controller의 move sprite with buttons 블록을 사용한다.  
이 블록은 보통 on start 안에 넣는다.

## Scene

사용 상황:

- 배경색 설정
- 배경 이미지 설정
- 타일맵 만들기
- 벽 만들기
- 카메라가 플레이어를 따라가게 하기

대표 블록:

- set background color
- set tilemap
- camera follow sprite
- on sprite hits wall

학생 안내 예시:

맵이나 벽을 만들고 싶으면 Scene과 Tilemap 블록을 사용한다.  
플레이어가 벽을 통과하지 않게 하려면 타일맵에서 벽 타일을 설정해야 한다.

## Info

사용 상황:

- 점수
- 목숨
- 제한 시간

대표 블록:

- set score
- change score by
- set life
- change life by
- start countdown
- on life zero

학생 안내 예시:

점수, 목숨, 시간은 Info 블록에서 관리한다.  
적과 닿으면 목숨을 줄이고 싶을 때는 overlap 이벤트 안에 change life by -1을 넣는다.

## Game

사용 상황:

- 게임 오버
- 게임 업데이트
- 일정 시간마다 반복
- 대사창
- 시작 안내문

대표 블록:

- on game update
- on game update every
- game over
- splash
- show long text

학생 안내 예시:

계속 확인해야 하는 조건은 on game update를 사용한다.  
1초마다 적을 만들고 싶으면 on game update every 1000 ms를 사용한다.

## Logic

사용 상황:

- 조건문
- 비교
- 참/거짓 판단

대표 블록:

- if
- else
- and
- or
- not
- equals
- less than
- greater than

학생 안내 예시:

특정 조건일 때만 실행하고 싶으면 if 블록을 사용한다.

## Variables

사용 상황:

- 체력 저장
- 단계 저장
- 현재 무기 저장
- 보스 상태 저장

대표 블록:

- set variable
- change variable by

학생 안내 예시:

게임에서 기억해야 하는 값은 변수로 만든다.

## Math

사용 상황:

- 랜덤 위치
- 랜덤 속도
- 거리 계산
- 점수 계산

대표 블록:

- pick random
- plus
- minus
- multiply
- divide

학생 안내 예시:

적이 매번 다른 위치에서 나오게 하려면 pick random 블록을 사용한다.
