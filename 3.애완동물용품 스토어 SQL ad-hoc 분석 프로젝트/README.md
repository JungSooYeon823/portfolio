# 애완동물용품 스토어 SQL ad-hoc 분석 프로젝트
<br>

**Tool** : Jupyter Notebook | [Link Notebook](https://github.com/JungSooYeon823/portfolio/blob/main/3.%EC%95%A0%EC%99%84%EB%8F%99%EB%AC%BC%EC%9A%A9%ED%92%88%20%EC%8A%A4%ED%86%A0%EC%96%B4%20SQL%20ad-hoc%20%EB%B6%84%EC%84%9D%20%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8/%EC%A0%95%EC%88%98%EC%97%B0_%EC%95%A0%EC%99%84%EB%8F%99%EB%AC%BC%EC%9A%A9%ED%92%88%20%EC%8A%A4%ED%86%A0%EC%96%B4%20SQL%20ad-hoc%20%EB%B6%84%EC%84%9D%20%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8.ipynb)<br>
**Programming Language** : SQL <br>
**Libraries** : Pandas <br>
**Visualization** : Matplotlib, Seaborn <br>
**Source Dataset** :  <br>
<br>
<br>

**Table of Contents**
- [STAGE 0:프로젝트 개요](https://github.com/JungSooYeon823/portfolio/blob/main/3.%EC%95%A0%EC%99%84%EB%8F%99%EB%AC%BC%EC%9A%A9%ED%92%88%20%EC%8A%A4%ED%86%A0%EC%96%B4%20SQL%20ad-hoc%20%EB%B6%84%EC%84%9D%20%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8/README.md#-stage-0-프로젝트-개요)
	- [기획 의도](https://github.com/JungSooYeon823/portfolio/blob/main/3.%EC%95%A0%EC%99%84%EB%8F%99%EB%AC%BC%EC%9A%A9%ED%92%88%20%EC%8A%A4%ED%86%A0%EC%96%B4%20SQL%20ad-hoc%20%EB%B6%84%EC%84%9D%20%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8/README.md#기획-의도)
	- [문제 정의](https://github.com/JungSooYeon823/portfolio/blob/main/3.%EC%95%A0%EC%99%84%EB%8F%99%EB%AC%BC%EC%9A%A9%ED%92%88%20%EC%8A%A4%ED%86%A0%EC%96%B4%20SQL%20ad-hoc%20%EB%B6%84%EC%84%9D%20%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8/README.md#문제-정의)
	- [분석 목표](https://github.com/JungSooYeon823/portfolio/blob/main/3.%EC%95%A0%EC%99%84%EB%8F%99%EB%AC%BC%EC%9A%A9%ED%92%88%20%EC%8A%A4%ED%86%A0%EC%96%B4%20SQL%20ad-hoc%20%EB%B6%84%EC%84%9D%20%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8/README.md#분석-목표)
- [STAGE 1: 결과](https://github.com/JungSooYeon823/portfolio/blob/main/3.%EC%95%A0%EC%99%84%EB%8F%99%EB%AC%BC%EC%9A%A9%ED%92%88%20%EC%8A%A4%ED%86%A0%EC%96%B4%20SQL%20ad-hoc%20%EB%B6%84%EC%84%9D%20%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8/README.md#-stage-1-결과)
	- [프로덕트 팀 요청 사항](https://github.com/JungSooYeon823/portfolio/blob/main/3.%EC%95%A0%EC%99%84%EB%8F%99%EB%AC%BC%EC%9A%A9%ED%92%88%20%EC%8A%A4%ED%86%A0%EC%96%B4%20SQL%20ad-hoc%20%EB%B6%84%EC%84%9D%20%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8/README.md#프로덕트-팀-요청사항)
 	- [마케팅 팀 요청 사항](https://github.com/JungSooYeon823/portfolio/blob/main/3.%EC%95%A0%EC%99%84%EB%8F%99%EB%AC%BC%EC%9A%A9%ED%92%88%20%EC%8A%A4%ED%86%A0%EC%96%B4%20SQL%20ad-hoc%20%EB%B6%84%EC%84%9D%20%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8/README.md#마케팅-팀-요청사항)
	 -  [비즈니스 팀 요청 사항](https://github.com/JungSooYeon823/portfolio/blob/main/3.%EC%95%A0%EC%99%84%EB%8F%99%EB%AC%BC%EC%9A%A9%ED%92%88%20%EC%8A%A4%ED%86%A0%EC%96%B4%20SQL%20ad-hoc%20%EB%B6%84%EC%84%9D%20%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8/README.md#비즈니스-팀-요청사항)
	
- [STAGE 2: 액션 플랜](https://github.com/JungSooYeon823/portfolio/blob/main/3.%EC%95%A0%EC%99%84%EB%8F%99%EB%AC%BC%EC%9A%A9%ED%92%88%20%EC%8A%A4%ED%86%A0%EC%96%B4%20SQL%20ad-hoc%20%EB%B6%84%EC%84%9D%20%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8/README.md#-stage-2-액션-플랜)
<br>
<br>

---

## 📂 **STAGE 0: 프로젝트 개요**

### 기획 의도
애완동물 용품 스토어 판매 데이터를 바탕으로,실제 현업에서 활용할 수 있는 ad-hoc 분석 시뮬레이션 진행<br>
<br>

### 문제 정의
- 프로덕트 팀 요청 사항:
    - 알러지가 있는 애완동물 보호자의 플레이버 선호도 확인
    - 애완동물 사이즈 별 건식/습식 사료 주문 현황
    - 애완동물 생애 단계 별 주문 현황
- 마케팅 팀 요청 사항
    - 가입 경로 별 주문 현황
    - 가입 경로 별 세션/접속 시간 확인
- 비즈니스 팀 요청 사항
    - 재구매율 분석
    - 사료 카테고리 별 성장률
    - 코호트 분석
    - 습식 사료 구매 증가 요인 확인
<br>

### 분석 목표
- 팀 별 요청사항 대응과 함께 요청사항 별 문제정의 단계부터 액션플랜 도출단계까지 시뮬레이션 진행 

<br>
<br>

---

## 📂 **STAGE 1: 결과**


### 프로덕트 팀 요청사항
#### 1.알러지가 있는 애완동물 보호자의 플레이버 선호도 확인

![top](https://github.com/JungSooYeon823/portfolio/assets/121957252/9b36c848-3969-408f-8bec-1cc440f82cb9) [상위 Flavour]
![botoom](https://github.com/JungSooYeon823/portfolio/assets/121957252/db5e23cc-c809-4f48-9d70-2d8eecd84a93)[하위 Flavour]


- 알러지 리스트별 가장 선호하는 Flavor (맛)  : Fish/Lamb 와 같이, 주로 단일 원료 Flavor을 선호한다.
- 알러지 리스트별 가장 선호하지 않는  Flavor (맛)  : Fish Lamb/Beef Lamb와 같이, 혼합 원료 Flavor을 비선호한다.

####  2.애완동물 사이즈별 건식/습식 사료 주문 현황

![스크린샷 2024-01-12 오후 6 19 11](https://github.com/JungSooYeon823/portfolio/assets/121957252/90cf2cd6-ad37-4ad9-bd62-abc94b284c35)


- 애완동물 사이즈별 사료의 총 주문 건 비교 시, 'Small' 사이즈의 강아지 주문량이 가장 많다.
- 건식/습식 사료의 총 주문건 비교 시, 건식사료의 주문량이 압도적으로 많다.

#### ※특이사항 
- 건식 사료는 'Medium'사이즈 애완동물 보호자의 주문이 가장 많았으며, 
- 습식 사료는 'Small'사이즈의 애완동물 보호자의 주문이 가장 많았습니다.

  ⇒ 사이즈별 주문량이 다르므로, 애완동물 생애 단계에 따른 사료 주문량 분석 데이터 추가 확인해야 합니다.

####  3.애완동물 생애단계 별 주문현황

![ddd](https://github.com/JungSooYeon823/portfolio/assets/121957252/c810512f-dc36-49b3-9b5d-f9f3362b9baf)

- 애완동물 생애단계 별 건식/습식 사료 주문 비교 시, '건식 사료' 주문 현황이 압도적으로 더 많다.

  ⇒ 습식사료는 성견과 노견 의 주문량 이 많으며, 건식사료는 반성숙기견,성견의 주문량이 가장 많다.
  
  ⇒ 애완동물 생애단계와 사이즈별 주문현황도 추가 확인이 필요하다.

####  4.(추가 확인 사항)애완동물 생애단계 +사이즈별 주문 현황

![dfd](https://github.com/JungSooYeon823/portfolio/assets/121957252/e9da90d7-650c-4b12-b99e-5263b5444220)

- 습식 사료는 강아지의 전 생애단계가 모두 'Small'사이즈 애완동물의 주문량이 가장 많다. 
- 건식 사료는 애완동물 전 생애단계에서 'Medium,Large'사이즈의 주문량이 가장 많다.

  ⇒ 사료별 칼로리 데이터를 통해 ,애완동물의 몸집이 클수록, 높은 칼로리의 사료인 '건조사료'가 필요하다는 사실을 확인 할 수 있다. 

___

### 마케팅 팀 요청사항
#### 1.고객의 가입 경로 별 주문 현황 데이터 요청

![signup](https://github.com/JungSooYeon823/portfolio/assets/121957252/7e6658c5-6fc2-48a7-9a52-c4691004d4df)

- 'Search Generic ' (오가닉 검색) 유입으로 가입한 고객의 주문 건수가 상위 2위 랭크

  ⇒  현재 자사의 브랜딩 전략이 효과적인 성과를 달성한것으로 추측되며,자사 브랜드 키워드의 검색 쿼리 트렌드 확인을 통해  브랜딩 효과 확인이 필요함
 
- 현재 Paid 채널인  'Digital Display' 채널은 'Social Marketing'채널보다 총 주문 건이 월등히 높다.

  ⇒ 해당 데이터를 바탕으로 추가적인  채널별 세션 및 사용시간 분석 필요하다.

#### 2.(추가 확인 사항) 고객 가입 채널별 세션 및 사용시간 분석

![promo](https://github.com/JungSooYeon823/portfolio/assets/121957252/8d5508c4-78a9-4b2b-a5bf-ab34ecbc2934)

- 'Digital Display' 채널보다 Social Marketing 채널의 총 세션 시간이 높지만,고객 당 세션 시간이 약 8배 가량 차이가 있다.
  
  ⇒ 'Social Marketing ' 랜딩 페이지 점검 및 연결 버튼 URL 점검 요청

- 'Digital Display' 채널은 'Refer a Friend'와 같은 브랜드 인지고객과 유사한 세션시간을 나타내지만,주문 건수는 월등히 높다.
  
  ⇒ 비효율 채널의 예산 분배 혹은 'Digital Display' 채널 확장 제안

### 비즈니스 팀 요청 사항 
#### 1.재구매율 분석

  ![20240112_153340](https://github.com/JungSooYeon823/portfolio/assets/121957252/49a55a06-4e34-4db9-85bc-7923d54bb774)

  - 재구매 고객 비율은 평균 85%로,구매 주기는 평균 26일로 확인된다.
  - 습식 사료의 재구매 주기는 24일로 가장 짧다.

#### 2.사료 카테고리 별 성장률 

  ![20240112_153506](https://github.com/JungSooYeon823/portfolio/assets/121957252/25e5dc64-9ad1-40c4-8a37-9f2ed0e33790)

  - 건식 사료와 습식 사료 모두 2019년 상반기 대비 성장하였으며,특히 습식사료는 2019년 대비 건식 사료의 약2배 성장=> 습식 사료 구매 증가 요인 추가 확인 필요함

#### 3.(추가 확인 사항) 습식 사료 구매 증가 요인

  ![습식사료 성장률](https://github.com/JungSooYeon823/portfolio/assets/121957252/5b7c0059-12b6-4594-b1f5-09ac04bb68d9)

  [습식사료 성장률]

  ![습식사료 생애단계별 성장률](https://github.com/JungSooYeon823/portfolio/assets/121957252/5b066380-593a-4030-9c22-ed201654bc18)

  [습식사료 생애단계별 성장률]

  ![최종 파일](https://github.com/JungSooYeon823/portfolio/assets/121957252/03d959c6-b386-4c18-beac-6dd66a47bd31)

  [습식사료의 애완동물 사이즈,성장단계별 성장률]


  - 습식사료는 주로 'Toy,Small' 사이즈의 주문건이 가장 많이 상승했으며,이유기 시기와 성견 시기의 주문건이 대폭 상승
  - 사이즈/성장단계별 종합적인 성장률 확인 시,주로 성견 > 반성숙 견 >노견 순으로 주문량이 대폭 상승

  ⇒ 해당 성장률을 바탕으로, 사료 선택에 있어 애완동물 사이즈 및 성장 단계가 중요한 요소인 것으로 판단

  #### 4.코홀트 분석
  ``` sql
  코호트의 유형은 : 최초 주문일 기준 코호트
  코호트 집계 방식 : 코호트 기준일에 부합하면 집계
  코호트의 크기 : 1달 단위
  코호트의 측정 항목 : 유지율
  코호트의 전체 기간 : 12달
  코호트 집계 방식 : 코호트 기준일에 부합하면 집계
  ```

  ![20240112_155000](https://github.com/JungSooYeon823/portfolio/assets/121957252/83a530d3-8a56-4ee5-bf8d-0b298353d5e5)


- 모든 코호트기간에서 1달이 경과했을 때 , 유지율은 평균 40%로, 평균 이커머스 유지율 20% 대비 높은 수치
- 첫 구매 후 2달이 경과했을 때,유지율이 가장 많이 하락

  ⇒가입 시, 프로모션 혹은 구독 시스템으로 인한 혜택을 받은 후, 이탈로 추측

  ⇒이탈 시기를 바탕으로, 추가적인 CRM 마케팅 및 프로모션 기획이 필요하다.

 ## 📂 **STAGE 2: 액션 플랜**
  
 ### 1.프로덕트 팀 액션 플랜

 - 애완동물 사이즈 및 성장 단계 필터 기능을 생성 제안  => 고객의 결제 시간 단축 및 편의성 증대 목적

 ### 2.마케팅 팀 액션 플랜

 - 'Social Marketing ' 랜딩 페이지 점검 및 연결 버튼 URL 점검 요청
 - 비효율 Paid 채널의 예산 분배 혹은 'Digital Display' 채널 확장 제안
 - 자사 브랜드 키워드의 검색 쿼리 트렌드 확인을 통한  브랜딩 효과 추가 확인

 ### 3.비즈니스 팀 액랜

 - 고객 피드백 수집 및 분석을 통해,재구매율 감소 원인 파악
 - 개인화된 마케팅 전략을 통해, 고객 맞춤 추천 및 할인 프로모션 시행
 - 충성 고객 유치와 재구매 촉진을 위한 리워드 시스템 도입
