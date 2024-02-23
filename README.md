# RL CARTPOLE 프로젝트

### 카트 폴이란?
*카트와 폴로 구성된 게임

![image](https://github.com/matrix215/RL_cartpole_project/assets/101815603/292e1ad0-26f1-4607-ba8b-a8cdad4f5358)


### 목표
- 카트 위에 폴이 떨어지지 않고 목표 시간까지 버티고 있어야 함.​
- 카트를 오른쪽이나 왼쪽으로 밀었을 때 폴의 균형을 맞추는 방법을 강화학습을 통해서 배워야함​
### 종료 요건
막대기가 수직으로 부터 12도 이상 기울어짐​
카트가 중심으로 부터 2.4이상 벗어남​
시간 시스템이 500보다 커짐

---

![image](https://github.com/matrix215/RL_cartpole_project/assets/101815603/c4c6caf6-cf0f-4e6a-aae2-196a7df2b0ac)

- 매 스탭마다 에이전트는 행동을 선택하고, 환경은 관찰값과 보상을 반환
- 보상값이 커지는 방향으로 행동

----

# 코드 설명

![image](https://github.com/matrix215/RL_cartpole_project/assets/101815603/1f371293-03ad-4507-9be0-640a4a762a72)
###Gym 라이브러리
-  openAI 사가 출시한 강화학습 전용 라이브러리

![image](https://github.com/matrix215/RL_cartpole_project/assets/101815603/798b4295-b469-40d2-a19f-5b953578becb)

-Gym을 구동하는 주요 3가지 함수

:Make, Step 과 Reset

Make: 사용하고 싶은 라이브러리를 불러오는 것

Reset: state 변수를 0 주변의 작은 범주안의 값으로 초기화함

Step: 정보를 반환하는 값
- 관찰(object): 환경에 대한 관찰을 나타내는 객체이며, 환경에 따라 달라짐
- reward: 이전의 행동을 통해 얻어지는 보상의 양. 그 크기는 환경에 따라 달라지지만 목표는 언제나 보상의 총량을 높이는 것이다.
- Done(boolen): 환경을 reset 해야할지 나타내는 진리값이다. done=True 라면 에피소드가 종료되었음을 나타냅니다.
- Info는 디버깅에 유용한 진단 정보이다.

![image](https://github.com/matrix215/RL_cartpole_project/assets/101815603/9fde9a92-4d13-4215-a206-7d8d0465f60d)

- 실제 state의 경우 연속적인 값을 가지고 있음-> 무한한 종류의 state를 가질 수 있는 문제, Q-Table을 만들기 위해선 연속적인 값을 이산값으로 변환하는 함수 discretizer

![image](https://github.com/matrix215/RL_cartpole_project/assets/101815603/0ba902af-8cb7-432a-8566-fcc3a2617022)
- Q-table: 각 state에서 action이 가지는 값을 모두 가지고 있음

- <Q-table 초기화>
0 행렬로 초기화 후, shape(현재 데이터 출력)


![image](https://github.com/matrix215/RL_cartpole_project/assets/101815603/e7687010-6bca-47ad-a52f-b5445f0306ee)


![image](https://github.com/matrix215/RL_cartpole_project/assets/101815603/6f921b29-9ff7-4984-b12b-9bbc51311cea)
- learning_rate 함수 정의

![image](https://github.com/matrix215/RL_cartpole_project/assets/101815603/c05d504b-e22e-4cc5-8b87-5ededd486ffc)
- exploration_rate 함수 정의




![image](https://github.com/matrix215/RL_cartpole_project/assets/101815603/870f37cb-4376-448e-89b9-c45e75378344)

![image](https://github.com/matrix215/RL_cartpole_project/assets/101815603/e52809f8-7e04-4b44-beb6-98df6ff6b495)

- Q-learing을 시행한 후 각각의 state값을 출력함

- 각각 observation에는 4가지 즉, 카트 위치, 카트 속도, 폴 각도, 폴 각도 속도
- 1이 나타내는 것은 보상
- Done: 끝나지 않았음으로 False
- Info= Default로 Fasle 값




[cartpole자료.pdf](https://github.com/matrix215/RL_cartpole_project/files/14384052/cartpole.pdf)
