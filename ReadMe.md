##### 주기적으로 업데이트 됩니다. (20220630 - 전반적 내용 추가)
##### step1 - 플레이어 움직임, 꼬리 요소랑 플레이어가 닿으면 꼬리 추가, 꼬리가 플레이어 뒤를 따라다니는 로직 추가 목표(20220701)

# A Catching tail (꼬리 잡기)

## 기획 사항들

### 승리 조건

#### 1. 제한 시간 내에 모든 다른 적들의 꼬리를 잡아 아웃시킨다.
#### 2. 제한 시간이 끝나는 시점에 가장 긴 꼬리를 가지고 있다.


### 목표

#### 1. 스타트 멤버(AI 상대) 수 변경
#### 2. 상황에 맞는 상대 행동 매커니즘 구현
#### 3. 매칭을 통한 PVP 플레이 구현



### Scene 구성

#### 1. 타이틀 Scene
#### 2. 게임 모드 설정 Scene (PVE or PVP / PVE일 경우 상대 수 설정)
#### 3. 인 게임 Scene


### 고민들 - 쯔꾸르식 2D? or 탑뷰 3D?

#### - 3D로 하는 것이 더 현장감 있어 보일라나..

<hr>

20220701 - 세부 step1 목표 설정

### 플레이어 움직임
### 꼬리에 닿으면 꼬리 추가
### 꼬리가 플레이어 뒤를 따라다니게끔(여러 꼬리 중첩)


#### 플레이어 움직임

> 발상 : 꼬리 오브젝트가 플레이어 오브젝트(or AI 오브젝트)에 닿게 되면 닿게 된 오브젝트 뒤에 위치하게끔 하며, 이동 방향을 따라서 뒤를 졸졸 따라다니께끔 설정하면 좋을 것.
> 처음 생각한 솔루션 : 꼬리 오브젝트에 Collider2D(IsTrigger)를 설정하여 이벤트가 생기게 한다. (플레이어 방향 뒤 좌표로 이동하게끔)
> 문제 사항 
<oi> 플레이어의 이동 방향에 영향을 받으면서 플레이어의 뒤에 있게 하려다 보니 움직이지 않을때는 속도가 0이어서 플레이어와 자리가 겹치게 된다.

