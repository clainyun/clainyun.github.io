---
title: "수요 예측 기법"

categories:
  - LG Aimers
  - AI Essential Course
tags:
  - [LG CNS, LG Aimers, 모델학습]

permalink: /private/91f2bd2e39b4k/

toc: true
toc_sticky: true

date: 2025-07-25
last_modified_at: 2025-07-25
---
<!-- 검색엔진 차단 -->
<meta name="robots" content="noindex, nofollow">

### 공급망 관리(SCM, Supply Chain Management)
고객이 원하는 제품을 합리적인 가격으로 정확한 상점에서 정확한 수량과 시간에 맞추는 노력
 
### '물류 4.0' 
생성형 AI가 수요를 예측해서 재고를 자동으로 관리, 로봇이 상품을 꺼내고 포장, 드론이나 자율주행차가 배송

Amazon (아마존)
: 물류창고에 Kiva 로봇 도입 → 물건을 자동으로 이동, 분류
예측 알고리즘으로 수요를 미리 분석해, 창고에 미리 재고 배치
드론 배송 시스템 Prime Air 실험 중

Walmart (월마트)
: 매장과 온라인 주문을 통합한 스마트 물류 시스템 구축
AI와 IoT를 활용해 재고 실시간 파악, 자동 발주
배송에는 로봇 팔, 자율주행차, 드론 배송 테스트 진행

 
### 공급망은 어떤 요소로 이루어져 있는가?
효율성과 대응성
-> 공급망 전략에서는 이 둘을 절충 시키는 것이 중요함
 
### 수요 예측 기법 이론 및 실습
공급망 관리에서 가장 중요한 것은 정보
그리고 그 정보에서 가장 중요한 것은 수요 예측
 
# 수요 예측 기법에는 전통적인 통계 기반 기법과 인공지능 기법 등 다양한 기법들이 존재

### 회귀 분석
하나 이상의 독립변수와 종속변수 간의 관계를 함수로 정의하고, 해당 함수의 계수를 실제 데이터를 바탕으로 추정하는 통계적 기법

독립 변수는 종속 변수에 영향을 미친다고 가정하는 요인
종속 변수는 예측하고자 하는 값
-> 선형 함수로 표현 ; x가 y에 어떤 영향을 미치는지 함수로 설명하고자 함.

<img width="669" height="220" alt="image" src="https://github.com/user-attachments/assets/a98ed296-9568-4f34-9203-f9a4f969c2fc" />
1차 선형함수의 경우에 예측에 쓰이는 직선은 실제 데이터와 굉장히 가까이 있어야 함.
얼마나 가까이 있는가를 평가하는, 그것이 바로 오차 또는 잔차
그래서 위의 직선식이 실제 데이터를 잘 설명한다는 것은 '오차의 제곱합을 최소화' 하는 것.

<img width="826" height="441" alt="Image" src="https://github.com/user-attachments/assets/453c3f93-16d1-4890-8a9f-c4cca5a12111" />
다양한 시계열 분석 기법이 존재
-> 보통 추세와 계절성을 잘 반영해서 예측할 수 있냐 없냐로 구분

<img width="796" height="447" alt="Image" src="https://github.com/user-attachments/assets/10988773-e294-4b50-8ad2-7c2b0ed43ba8" />
과거 데이터가 현재에 영향을 준다 → AR
데이터에 추세(증가·감소 경향)가 있다 → I
노이즈(오차)가 일정하지 않다 → MA
ARIMA는 이 세 가지를 동시에 고려해서 예측함.

<img width="834" height="352" alt="Image" src="https://github.com/user-attachments/assets/68276d11-8034-4cfc-b592-40e2067c82cd" />
학습을 위해 충분한 데이터 양(1년치 이상)이 있어야 한다!!! 🌟중요🌟

<img width="857" height="469" alt="Image" src="https://github.com/user-attachments/assets/ba0091a6-3ffb-4ea0-ac2b-afe9dd8478eb" />
하이브리드 모델은 전통적 기법의 예측과 인공지능 모델을 혼합해서 사용하는 모델
추세와 계절성을 반영할 수 있음. ex) 프로모션 등의 이벤트
교수님 추천🎖️ 수요예측 경진대회를 나가면 하이브리드 모델을 사용 권장
 
### 수요예측 실습 진행
 

### 모델 학습
1. 오적합은 데이터의 구조를 잘못 이해해서 모델을 엉뚱하게 적용
2. 과소적합은 모델이 너무 단순해서 데이터의 패턴을 못 따라감
3. 과대적합은 모델이 너무 복잡해서 훈련 데이터에 지나치게 맞춰버리는 것 -> 모델의 일반화 가능성 떨어짐

 
### 딥러닝이 항상 좋은 것은 아니다
하이퍼파라미터(hyperparameter)는 모델을 학습하기 전에 사람이 직접 지정해주는 값
이 하이퍼파라미터 튜닝 없이는 오히려 단순한 회귀 분석보다 성능이 낮을 수도 있음.

# * 실습 참고
<img width="808" height="384" alt="Image" src="https://github.com/user-attachments/assets/463f06d3-a477-4ce8-9b65-d9228ccfdc16" />

<img width="827" height="480" alt="Image" src="https://github.com/user-attachments/assets/ba0c54c7-af3d-4fe1-af16-af90f24658ac" />
 
# 결정계수(R-squared)는 모델이 데이터를 얼마나 잘 설명하는지, 즉 '설명력'을 나타내는 지표
그래서 1에 가까울수록 예측 good.
보통 70%가 넘으면 아주 훌륭함
 
### 인과 추론
머신러닝 모델이 학습한 상관관계가 실제로 인과관계와는 다를 수 있다!!!
상관성과 인과성의 차이는
쉽게 말해서 연관관계가 있으면 상관성이고, 원인이 결과에 어떻게 기여 하는지는 인과성
 
전통적으로 머신러닝은 데이터에 있는 상관성을 다룸.
왜냐면 일반적인 머신러닝 모델을 통해 얻는 예측값은 단지 패턴을 학습한 것에 불과하고,
그 결과가 어떠한 인과구조에 의해 만들어졌는지는 전혀 설명하지 못한다.
그래서 모델의 예측이 과연 '왜' 그런 결과를 냈는지를 질문하는 자세가 중요함.

 
### 인과 추론에서의 대표적인 프레임워크
- Potential Outcome (PO) Framework
- Structural Causal Model (SCM)

Potential Outcome Framework는 "만약에 ~~했더라면?"을 다루는 이론

# 신약 A의 효과
어떤 환자가 A 약을 먹고 병이 나았다.
그런데 그 환자가 약을 안 먹었다면 어땠을까? -> PO
그러나 그것은 관찰할 수 없는 데이터임
why? 이미 약을 먹었으니까. -> Missing Data Problem

### 그러면 어떻게 인과추론을 해야할 것인가?
약을 먹은 사람과 안 먹은 사람을 비슷한 조건(나이, 성별, 병력, ...)으로 잘 맞춰서 비교(Matching)

### SCM (Structural Causal Model)
변수들 사이의 인과 관계를 방향 있는 그래프(DAG)로 표현하는 것.
<img width="303" height="160" alt="Image" src="https://github.com/user-attachments/assets/7541eaac-5d55-437d-ba0b-5a172c4082ff" />
내생변수(우리가 관측할 수 있는 요인) 간의 인과관계
A, B에 의해 영향을 받고있는 D는 단방향 edge로 표현가능
한편, U' 라고 하는 외생변수(관측 X)에 영향을 받고있는 D와 E는 양방향 edge로 표현함

예를 들면,
    X: 공부 시간
    Y: 시험 점수
## X → Y
## Y = f(X,U)
f: 공부량이 시험 점수에 어떻게 영향을 주는지에 대한 함수
U: 관찰되지 않은 노이즈(예: 컨디션, 운 등)

