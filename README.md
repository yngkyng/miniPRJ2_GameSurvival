# miniPRJ2_GameSurvival

## 사용 데이터
[엔씨소프트, 게임유저 잔존가치를 고려한 고객 이탈예측 (2019년 빅콘 제공데이터)](https://danbi-ncsoft.github.io/OpenData/)

## 진행 과정
### 1. 프로젝트 주제 선정 및 데이터 수집
### 2. 데이터 분석 설계, 전처리
#### 2-1. 분석 계획
  * 전체 기간 합산 / 일자별 데이터 2종류로 모델 학습 및 검증
  * 생존에 영향을 주는 추가 요인 탐색
#### 2-2. 데이터 전처리
  * 생존 기간(일) 컬럼을 63일 이하이면, 0(이탈) / 64일이면, 1(생존)으로 라벨링

### 3. 모델 학습
#### 3-1. 전체 기간 합산 데이터 학습
  ![image](https://github.com/yngkyng/miniPRJ2_GameSurvival/assets/121409505/985341f5-4413-48c4-83c7-fc23d4773ae5)

#### 3-2. 일자별 데이터 학습
  ![image](https://github.com/yngkyng/miniPRJ2_GameSurvival/assets/121409505/c65abba9-083a-4846-a98e-beedecbd4454)

#### 3-3. test 결과
  ![image](https://github.com/yngkyng/miniPRJ2_GameSurvival/assets/121409505/a5405629-fa91-4183-b73f-528acce46565)
  * 과적합되었음

### 4. 추가 요인 탐색
#### 4-1. 캐릭터 직업 그룹별 생존율
  ![image](https://github.com/yngkyng/miniPRJ2_GameSurvival/assets/121409505/afe80387-4adf-4e37-ae89-3266af1b11ff)
  * 생존율 높은 순서 : 1,7,2,0,6,5,3,4 (기사, 전사, 요정, 군주, 환술사, 용기사, 마법사, 다크엘프)

#### 4-2. 보유 캐릭터 갯수별 생존율
  ![image](https://github.com/yngkyng/miniPRJ2_GameSurvival/assets/121409505/3273bf39-8b74-49b9-a94c-cc0723840abf)
  * 생존율 높은 순서 : 5 이상, 4,1,3,2(개)

#### 4-3. 결제금액 그룹별 생존율
  ![image](https://github.com/yngkyng/miniPRJ2_GameSurvival/assets/121409505/c89814cf-ea76-4926-9e3e-0744295fdbdd)
  * 생존율 높은 순서 : 평균 이상 결제 그룹 > 평균 이하 결제 그룹

#### 4-4. 활동 혈맹원에 따른 생존율
  ![image](https://github.com/yngkyng/miniPRJ2_GameSurvival/assets/121409505/99e2824a-10ba-4223-803a-a2191cc36380)
  * 혈맹원들의 활동량과 개인의 생존율은 단순 비례 관계가 아님
