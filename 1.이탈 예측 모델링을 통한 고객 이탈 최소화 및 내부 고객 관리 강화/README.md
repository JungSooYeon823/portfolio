# 이탈 예측 모델링을 통한 고객 이탈 최소화 및 내부 고객 관리 강화

<br>

**Tool** : Jupyter Notebook | [Link Notebook](https://github.com/JungSooYeon823/portfolio/blob/main/1.%EC%9D%B4%ED%83%88%20%EC%98%88%EC%B8%A1%20%EB%AA%A8%EB%8D%B8%EB%A7%81%EC%9D%84%20%ED%86%B5%ED%95%9C%20%EA%B3%A0%EA%B0%9D%20%EC%9D%B4%ED%83%88%20%EC%B5%9C%EC%86%8C%ED%99%94%20%EB%B0%8F%20%EB%82%B4%EB%B6%80%20%EA%B3%A0%EA%B0%9D%20%EA%B4%80%EB%A6%AC%20%EA%B0%95%ED%99%94/%EC%9D%B4%ED%83%88%20%EC%98%88%EC%B8%A1%20%EB%AA%A8%EB%8D%B8%EB%A7%81%EC%9D%84%20%ED%86%B5%ED%95%9C%20%EA%B3%A0%EA%B0%9D%20%EC%9D%B4%ED%83%88%20%EC%B5%9C%EC%86%8C%ED%99%94%20%EB%B0%8F%20%EB%82%B4%EB%B6%80%20%EA%B3%A0%EA%B0%9D%20%EA%B4%80%EB%A6%AC%20%EA%B0%95%ED%99%94.ipynb)<br>
**Programming Language** : Python <br>
**Libraries** : Pandas, NumPy, sklearn <br>
**Visualization** : Matplotlib, Seaborn<br>
**Source Dataset** : [Kaggle Data](https://www.kaggle.com/datasets/ankitverma2010/ecommerce-customer-churn-analysis-and-prediction/) <br>
<br>
<br>
**Table of Contents**
- [STAGE 0: 프로젝트 개요](https://github.com/JungSooYeon823/portfolio/blob/main/1.%EC%9D%B4%ED%83%88%20%EC%98%88%EC%B8%A1%20%EB%AA%A8%EB%8D%B8%EB%A7%81%EC%9D%84%20%ED%86%B5%ED%95%9C%20%EA%B3%A0%EA%B0%9D%20%EC%9D%B4%ED%83%88%20%EC%B5%9C%EC%86%8C%ED%99%94%20%EB%B0%8F%20%EB%82%B4%EB%B6%80%20%EA%B3%A0%EA%B0%9D%20%EA%B4%80%EB%A6%AC%20%EA%B0%95%ED%99%94/README.md#-stage-0-프로젝트-개요)
	- [기획 의도](https://github.com/JungSooYeon823/portfolio/blob/main/1.%EC%9D%B4%ED%83%88%20%EC%98%88%EC%B8%A1%20%EB%AA%A8%EB%8D%B8%EB%A7%81%EC%9D%84%20%ED%86%B5%ED%95%9C%20%EA%B3%A0%EA%B0%9D%20%EC%9D%B4%ED%83%88%20%EC%B5%9C%EC%86%8C%ED%99%94%20%EB%B0%8F%20%EB%82%B4%EB%B6%80%20%EA%B3%A0%EA%B0%9D%20%EA%B4%80%EB%A6%AC%20%EA%B0%95%ED%99%94/README.md#기획-의도)
	- [문제 정의](https://github.com/JungSooYeon823/portfolio/blob/main/1.%EC%9D%B4%ED%83%88%20%EC%98%88%EC%B8%A1%20%EB%AA%A8%EB%8D%B8%EB%A7%81%EC%9D%84%20%ED%86%B5%ED%95%9C%20%EA%B3%A0%EA%B0%9D%20%EC%9D%B4%ED%83%88%20%EC%B5%9C%EC%86%8C%ED%99%94%20%EB%B0%8F%20%EB%82%B4%EB%B6%80%20%EA%B3%A0%EA%B0%9D%20%EA%B4%80%EB%A6%AC%20%EA%B0%95%ED%99%94/README.md#문제-정의)
	- [분석 목표](https://github.com/JungSooYeon823/portfolio/blob/main/1.%EC%9D%B4%ED%83%88%20%EC%98%88%EC%B8%A1%20%EB%AA%A8%EB%8D%B8%EB%A7%81%EC%9D%84%20%ED%86%B5%ED%95%9C%20%EA%B3%A0%EA%B0%9D%20%EC%9D%B4%ED%83%88%20%EC%B5%9C%EC%86%8C%ED%99%94%20%EB%B0%8F%20%EB%82%B4%EB%B6%80%20%EA%B3%A0%EA%B0%9D%20%EA%B4%80%EB%A6%AC%20%EA%B0%95%ED%99%94/README.md#분석-목표)
- [STAGE 1: 데이터 전처리](https://github.com/JungSooYeon823/portfolio/blob/main/1.%EC%9D%B4%ED%83%88%20%EC%98%88%EC%B8%A1%20%EB%AA%A8%EB%8D%B8%EB%A7%81%EC%9D%84%20%ED%86%B5%ED%95%9C%20%EA%B3%A0%EA%B0%9D%20%EC%9D%B4%ED%83%88%20%EC%B5%9C%EC%86%8C%ED%99%94%20%EB%B0%8F%20%EB%82%B4%EB%B6%80%20%EA%B3%A0%EA%B0%9D%20%EA%B4%80%EB%A6%AC%20%EA%B0%95%ED%99%94/README.md#-stage-1-데이터-전처리)
	- [결측치 & 이상치 처리 & 인코딩](https://github.com/JungSooYeon823/portfolio/blob/main/1.%EC%9D%B4%ED%83%88%20%EC%98%88%EC%B8%A1%20%EB%AA%A8%EB%8D%B8%EB%A7%81%EC%9D%84%20%ED%86%B5%ED%95%9C%20%EA%B3%A0%EA%B0%9D%20%EC%9D%B4%ED%83%88%20%EC%B5%9C%EC%86%8C%ED%99%94%20%EB%B0%8F%20%EB%82%B4%EB%B6%80%20%EA%B3%A0%EA%B0%9D%20%EA%B4%80%EB%A6%AC%20%EA%B0%95%ED%99%94/README.md#결측치-&-이상치-처리-&-인코딩)
- [STAGE 2: EDA](https://github.com/JungSooYeon823/portfolio/blob/main/1.%EC%9D%B4%ED%83%88%20%EC%98%88%EC%B8%A1%20%EB%AA%A8%EB%8D%B8%EB%A7%81%EC%9D%84%20%ED%86%B5%ED%95%9C%20%EA%B3%A0%EA%B0%9D%20%EC%9D%B4%ED%83%88%20%EC%B5%9C%EC%86%8C%ED%99%94%20%EB%B0%8F%20%EB%82%B4%EB%B6%80%20%EA%B3%A0%EA%B0%9D%20%EA%B4%80%EB%A6%AC%20%EA%B0%95%ED%99%94/README.md#-stage-2-EDA)

- [STAGE 3:모델링](https://github.com/JungSooYeon823/portfolio/blob/main/1.%EC%9D%B4%ED%83%88%20%EC%98%88%EC%B8%A1%20%EB%AA%A8%EB%8D%B8%EB%A7%81%EC%9D%84%20%ED%86%B5%ED%95%9C%20%EA%B3%A0%EA%B0%9D%20%EC%9D%B4%ED%83%88%20%EC%B5%9C%EC%86%8C%ED%99%94%20%EB%B0%8F%20%EB%82%B4%EB%B6%80%20%EA%B3%A0%EA%B0%9D%20%EA%B4%80%EB%A6%AC%20%EA%B0%95%ED%99%94/README.md#-stage-3-모델링)
  
- [STAGE 4:결과](https://github.com/JungSooYeon823/portfolio/blob/main/1.%EC%9D%B4%ED%83%88%20%EC%98%88%EC%B8%A1%20%EB%AA%A8%EB%8D%B8%EB%A7%81%EC%9D%84%20%ED%86%B5%ED%95%9C%20%EA%B3%A0%EA%B0%9D%20%EC%9D%B4%ED%83%88%20%EC%B5%9C%EC%86%8C%ED%99%94%20%EB%B0%8F%20%EB%82%B4%EB%B6%80%20%EA%B3%A0%EA%B0%9D%20%EA%B4%80%EB%A6%AC%20%EA%B0%95%ED%99%94/README.md#-stage-4-모델-해석)
- [STAGE 5: 액션 플랜](https://github.com/JungSooYeon823/portfolio/blob/main/1.%EC%9D%B4%ED%83%88%20%EC%98%88%EC%B8%A1%20%EB%AA%A8%EB%8D%B8%EB%A7%81%EC%9D%84%20%ED%86%B5%ED%95%9C%20%EA%B3%A0%EA%B0%9D%20%EC%9D%B4%ED%83%88%20%EC%B5%9C%EC%86%8C%ED%99%94%20%EB%B0%8F%20%EB%82%B4%EB%B6%80%20%EA%B3%A0%EA%B0%9D%20%EA%B4%80%EB%A6%AC%20%EA%B0%95%ED%99%94/README.md#-stage-5-액션-플랜)

<br>
<br>

---

## 📂 **STAGE 0: 프로젝트 개요**

### 기획 의도
엔데믹 영향과 고물가로 인해,이커머스 소비시장이 분산되고, 최저가 경쟁의 이유등으로 기업들은 경쟁적인 상황에 직면하고 있다.

⇒ 이로 인해, 고객 이탈율 상승 및 내부 고객 관리의 필요성이 대두되고 있다.<br>
<br>

### 문제 정의
- 1.고객 특성별 세분화된 마케팅 전략 수립 및 이탈 예측 모델링이 필요하다.
- 2.도시등급,결제 방식 등의 데이터를 활용하여, 비즈니스 전략 수립을 통해 장기적인 가치 창출이 필요하다. 
<br>
<br>

### 분석 목표 
- 1.고객 이탈 예측 모델 개발 
- 2.이탈에 영향을 주는 특성 중요
- 3.내부 고객 관리 강화 및 이탈 위험 고객 관리 액션 플랜 도출 
<br>

---
## 📂 **STAGE 1: 데이터 전처리**
### 결측치 & 이상치 처리 & 인코딩 

 **구분** | **데이터 전처리**  | 
--------------------|--------------|
결측치 |  결측치는 4~5%로 미비한 수치형 데이터로,단순 삭제 
이상치 |  이상치는 IQR 방식 혹은 Isolation Forest 선택 (2가지 경우의 수) 
인코딩 | 범주형 변수에 순서가 없고,카테고리 수가 많지 않으므로  'One-Hot-Encoding' 선택 
스케일링| 'MinMaxScaler' 선택 혹은 스케일링 X (2가지 경우의 수) 
오버 샘플링| 'SMOTE' 오버샘플링 혹은 오버샘플링 X(2가지 경우의 수) 


=> 해당 전처리 방식과 분류기 모델링을 통해 총 '35가지' 경우의 수의 전처리 방식 시도


<br>


<br>
<br>

## 📂 **STAGE 2: EDA**
### [이탈 여부]
![image](https://github.com/JungSooYeon823/portfolio/assets/121957252/35ef0bca-8c86-46f7-b81e-a5f0ae0ed605)
- 이탈 고객 16.8%, 잔존 고객 832.%로 타겟 데이터의 불균형이 심하다.

### [사용기간에 따른 이탈]
![image](https://github.com/JungSooYeon823/portfolio/assets/121957252/8c9a0817-b607-47a8-beb3-196371c200fa)
- 사용기간이 짧을수록 이탈율이 높다=> 사용 기간이 10일 이내인 고객의 이탈율이 24.4%로 가장 높다.
- 사용기간이 30일이 넘어가는 고객부터는 이탈율이 없는 충성적인 고객으로 변환되는 것을 알 수 있다.

### [컴플레인 여부에 따른 이탈]
![image](https://github.com/JungSooYeon823/portfolio/assets/121957252/3af9ca4a-d268-4f30-967f-bd3b351af9e8)
- 컴플레인이 있는 고객의 이탈율은 약 21% 더 높다.

### [결혼상태에 따른 이탈]
![image](https://github.com/JungSooYeon823/portfolio/assets/121957252/e5b29d04-9c77-4b7d-9213-fe242f53d05e)
- 싱글 고객의 이탈율은 26%로 가장 높다.
  
### [도시등급에 따른 이탈] 
![image](https://github.com/JungSooYeon823/portfolio/assets/121957252/45154eaa-362e-49ea-a1c1-e13abbbaab79)
![image](https://github.com/JungSooYeon823/portfolio/assets/121957252/54fe722e-f235-400f-93d7-cf63fa21bbbe)
![image](https://github.com/JungSooYeon823/portfolio/assets/121957252/93e6c378-ec20-4409-9b03-32d032ff2d25)

- 도시등급 3은 이탈율이 가장 높은 지역으로, 이탈율은 약 21.4%
- 도시등급 1,2는 Mobile 카테고리를 가장 선호하며, 도시등급 3은 Laptop을 가장 선호한다.
- 도시등급 1은 직불카드 결제 방식을 가장 선호한다.
- 도시 등급 2는 은행 간 계좌이체 결제 방식을 가장 선호한다.
- 도시 등급 3은 전자 지갑 시스템 결제 방식을 가장 선호한다.

---
## 📂 **STAGE 3: 모델링**

### 모델 비교 
![image](https://github.com/JungSooYeon823/portfolio/assets/121957252/03e2d748-123b-4479-b2a7-1def184437ff)

- 다양한 전처리,모델링에 따른 '36'가지 경우의 수 비교 결과, Data5의 F1 Score가 0.9649로 가장 우수하다. 
- 고객 이탈 예측을 위해 precision과 Recall의 조화 평균인 F1 Score 중점으로 비교하였으며,
XGBClassifier 모델의 성능이 가장 우수하다. 

### 모델 적용 
![image](https://github.com/JungSooYeon823/portfolio/assets/121957252/113a8fb4-de99-4580-a411-4fa004f1ae86)

- GridSearch와 RandomSearch로 파라미터 튜닝을 통해, 추가적인 성능 개선을 시도하였으나,
  튜닝 후 성능이 오히려 저하되어, 기본 베이스라인 선정 

---

## 📂 ** STAGE 4: 결과 **
![image](https://github.com/JungSooYeon823/portfolio/assets/121957252/26e693bd-dd17-4568-912e-dfc7f06642b8)
- High risk 이탈 위험 고객은 이탈 예상률이 60~90%로서, 이탈 등급 rank 1 부여  


## 📂 **STAGE 5: 액션 플랜**

- **1.서비스 이용 기간에 따른 멤버십 혜택 부여**
	- 내부 고객 :  장기 이용 고객 대상 정기적인 감사 이벤트를 통해 충성도 강화 
  	- 이탈 위험 고객 :  이용 기간이 짧은 신규 고객에게 멤버쉽 혜택 소개 및 특별 리워드 증정 
- **2.컴플레인 해결 및 고객 응대 강화** 
	- 내부 고객:컴플레인 고객 응대 및 문제 해결을 위한 컴플레인 해결 프로세스를 개선하고,컴플레인 피드백을 반영하여 제품 및 서비스의 개선 방향 도출 
 	- 이탈 위험 고객: 이탈 위험 고객 전용 서비스 팀을 구성하여,불만사항에 대해 우선적으로 대응, 주요 이슈에 대해 지속적인 모니터링 
- **3.도시 등급 별 선호하는 결제 방식에 따른 프로모션 진행** 
	- 내부 고객 :  도시 등급1은 “Debit card”(직불 카드), 도시 등급 2는 “UPI”(은행 간 계좌이체) , 도시 등급 3은 ‘E wallet’(전자 지갑 시스템)에 맞춰,맞춤형 혜택 제공 
 	- 이탈 위험 고객 : 도시 등급 3의 높은 이탈율에 주목하여, 해당 지역에 특화된 혜택 및 프로모션 진행을 통해, 이탈 고객 유지 및 고객 경험 개선 


