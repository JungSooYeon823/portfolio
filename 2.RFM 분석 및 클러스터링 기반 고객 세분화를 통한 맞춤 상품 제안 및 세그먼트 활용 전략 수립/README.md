## RFM 분석 및 클러스터링 기반 고객 세분화를 통한 맞춤 상품 제안 및 세그먼트 활용 전략 수립
<br>

**Tool** : Jupyter Notebook | [Link Notebook](https://github.com/JungSooYeon823/portfolio/blob/main/2.RFM%20%EB%B6%84%EC%84%9D%20%EB%B0%8F%20%ED%81%B4%EB%9F%AC%EC%8A%A4%ED%84%B0%EB%A7%81%20%EA%B8%B0%EB%B0%98%20%EA%B3%A0%EA%B0%9D%20%EC%84%B8%EB%B6%84%ED%99%94%EB%A5%BC%20%ED%86%B5%ED%95%9C%C2%A0%EB%A7%9E%EC%B6%A4%20%EC%83%81%ED%92%88%20%EC%A0%9C%EC%95%88%20%EB%B0%8F%20%EC%84%B8%EA%B7%B8%EB%A8%BC%ED%8A%B8%20%ED%99%9C%EC%9A%A9%20%EC%A0%84%EB%9E%B5%20%EC%88%98%EB%A6%BD/RFM%20%EB%B6%84%EC%84%9D%20%EB%B0%8F%20%ED%81%B4%EB%9F%AC%EC%8A%A4%ED%84%B0%EB%A7%81%20%EA%B8%B0%EB%B0%98%20%EA%B3%A0%EA%B0%9D%20%EC%84%B8%EB%B6%84%ED%99%94%EB%A5%BC%20%ED%86%B5%ED%95%9C%C2%A0%EB%A7%9E%EC%B6%A4%20%EC%83%81%ED%92%88%20%EC%A0%9C%EC%95%88%20%EB%B0%8F%20%EC%84%B8%EA%B7%B8%EB%A8%BC%ED%8A%B8%20%ED%99%9C%EC%9A%A9%20%EC%A0%84%EB%9E%B5%20%EC%88%98%EB%A6%BD.ipynb.pdf)<br>
**Programming Language** : Python <br>
**Libraries** : Pandas, NumPy, sklearn <br>
**Visualization** : Matplotlib, Seaborn <br>
**Source Dataset** : [Kaggle Data](https://www.kaggle.com/datasets/carrie1/ecommerce-data) <br>
<br>
<br>

**Table of Contents**
- [STAGE 0: 프로젝트 개요](https://github.com/JungSooYeon823/portfolio/blob/main/2.RFM%20%EB%B6%84%EC%84%9D%20%EB%B0%8F%20%ED%81%B4%EB%9F%AC%EC%8A%A4%ED%84%B0%EB%A7%81%20%EA%B8%B0%EB%B0%98%20%EA%B3%A0%EA%B0%9D%20%EC%84%B8%EB%B6%84%ED%99%94%EB%A5%BC%20%ED%86%B5%ED%95%9C%C2%A0%EB%A7%9E%EC%B6%A4%20%EC%83%81%ED%92%88%20%EC%A0%9C%EC%95%88%20%EB%B0%8F%20%EC%84%B8%EA%B7%B8%EB%A8%BC%ED%8A%B8%20%ED%99%9C%EC%9A%A9%20%EC%A0%84%EB%9E%B5%20%EC%88%98%EB%A6%BD/README.md#-stage-0-프로젝트-개요)
	- [기획 의도](https://github.com/JungSooYeon823/portfolio/blob/main/2.RFM%20%EB%B6%84%EC%84%9D%20%EB%B0%8F%20%ED%81%B4%EB%9F%AC%EC%8A%A4%ED%84%B0%EB%A7%81%20%EA%B8%B0%EB%B0%98%20%EA%B3%A0%EA%B0%9D%20%EC%84%B8%EB%B6%84%ED%99%94%EB%A5%BC%20%ED%86%B5%ED%95%9C%C2%A0%EB%A7%9E%EC%B6%A4%20%EC%83%81%ED%92%88%20%EC%A0%9C%EC%95%88%20%EB%B0%8F%20%EC%84%B8%EA%B7%B8%EB%A8%BC%ED%8A%B8%20%ED%99%9C%EC%9A%A9%20%EC%A0%84%EB%9E%B5%20%EC%88%98%EB%A6%BD/README.md#-기획-의도)
	- [문제 정의](https://github.com/JungSooYeon823/portfolio/blob/main/2.RFM%20%EB%B6%84%EC%84%9D%20%EB%B0%8F%20%ED%81%B4%EB%9F%AC%EC%8A%A4%ED%84%B0%EB%A7%81%20%EA%B8%B0%EB%B0%98%20%EA%B3%A0%EA%B0%9D%20%EC%84%B8%EB%B6%84%ED%99%94%EB%A5%BC%20%ED%86%B5%ED%95%9C%C2%A0%EB%A7%9E%EC%B6%A4%20%EC%83%81%ED%92%88%20%EC%A0%9C%EC%95%88%20%EB%B0%8F%20%EC%84%B8%EA%B7%B8%EB%A8%BC%ED%8A%B8%20%ED%99%9C%EC%9A%A9%20%EC%A0%84%EB%9E%B5%20%EC%88%98%EB%A6%BD/README.md#-문제-정의)
	- [분석 목표](https://github.com/JungSooYeon823/portfolio/blob/main/2.RFM%20%EB%B6%84%EC%84%9D%20%EB%B0%8F%20%ED%81%B4%EB%9F%AC%EC%8A%A4%ED%84%B0%EB%A7%81%20%EA%B8%B0%EB%B0%98%20%EA%B3%A0%EA%B0%9D%20%EC%84%B8%EB%B6%84%ED%99%94%EB%A5%BC%20%ED%86%B5%ED%95%9C%C2%A0%EB%A7%9E%EC%B6%A4%20%EC%83%81%ED%92%88%20%EC%A0%9C%EC%95%88%20%EB%B0%8F%20%EC%84%B8%EA%B7%B8%EB%A8%BC%ED%8A%B8%20%ED%99%9C%EC%9A%A9%20%EC%A0%84%EB%9E%B5%20%EC%88%98%EB%A6%BD/README.md#-분석-목표)
- [STAGE 1: 데이터 전처리](https://github.com/JungSooYeon823/portfolio/blob/main/2.RFM%20%EB%B6%84%EC%84%9D%20%EB%B0%8F%20%ED%81%B4%EB%9F%AC%EC%8A%A4%ED%84%B0%EB%A7%81%20%EA%B8%B0%EB%B0%98%20%EA%B3%A0%EA%B0%9D%20%EC%84%B8%EB%B6%84%ED%99%94%EB%A5%BC%20%ED%86%B5%ED%95%9C%C2%A0%EB%A7%9E%EC%B6%A4%20%EC%83%81%ED%92%88%20%EC%A0%9C%EC%95%88%20%EB%B0%8F%20%EC%84%B8%EA%B7%B8%EB%A8%BC%ED%8A%B8%20%ED%99%9C%EC%9A%A9%20%EC%A0%84%EB%9E%B5%20%EC%88%98%EB%A6%BD/README.md#-stage-2-데이터-전처리)
	- [결측치 & 중복 데이터 처리](https://github.com/JungSooYeon823/portfolio/blob/main/2.RFM%20%EB%B6%84%EC%84%9D%20%EB%B0%8F%20%ED%81%B4%EB%9F%AC%EC%8A%A4%ED%84%B0%EB%A7%81%20%EA%B8%B0%EB%B0%98%20%EA%B3%A0%EA%B0%9D%20%EC%84%B8%EB%B6%84%ED%99%94%EB%A5%BC%20%ED%86%B5%ED%95%9C%C2%A0%EB%A7%9E%EC%B6%A4%20%EC%83%81%ED%92%88%20%EC%A0%9C%EC%95%88%20%EB%B0%8F%20%EC%84%B8%EA%B7%B8%EB%A8%BC%ED%8A%B8%20%ED%99%9C%EC%9A%A9%20%EC%A0%84%EB%9E%B5%20%EC%88%98%EB%A6%BD/README.md#-결측치-&-중복-데이터-처리)
	- [변수 처리](https://github.com/JungSooYeon823/portfolio/blob/main/2.RFM%20%EB%B6%84%EC%84%9D%20%EB%B0%8F%20%ED%81%B4%EB%9F%AC%EC%8A%A4%ED%84%B0%EB%A7%81%20%EA%B8%B0%EB%B0%98%20%EA%B3%A0%EA%B0%9D%20%EC%84%B8%EB%B6%84%ED%99%94%EB%A5%BC%20%ED%86%B5%ED%95%9C%C2%A0%EB%A7%9E%EC%B6%A4%20%EC%83%81%ED%92%88%20%EC%A0%9C%EC%95%88%20%EB%B0%8F%20%EC%84%B8%EA%B7%B8%EB%A8%BC%ED%8A%B8%20%ED%99%9C%EC%9A%A9%20%EC%A0%84%EB%9E%B5%20%EC%88%98%EB%A6%BD/README.md#-변수-처리)
- [STAGE 2: EDA](https://github.com/JungSooYeon823/portfolio/blob/main/2.RFM%20%EB%B6%84%EC%84%9D%20%EB%B0%8F%20%ED%81%B4%EB%9F%AC%EC%8A%A4%ED%84%B0%EB%A7%81%20%EA%B8%B0%EB%B0%98%20%EA%B3%A0%EA%B0%9D%20%EC%84%B8%EB%B6%84%ED%99%94%EB%A5%BC%20%ED%86%B5%ED%95%9C%C2%A0%EB%A7%9E%EC%B6%A4%20%EC%83%81%ED%92%88%20%EC%A0%9C%EC%95%88%20%EB%B0%8F%20%EC%84%B8%EA%B7%B8%EB%A8%BC%ED%8A%B8%20%ED%99%9C%EC%9A%A9%20%EC%A0%84%EB%9E%B5%20%EC%88%98%EB%A6%BD/README.md#-stage-2-EDA)
	- [판매 트렌드](https://github.com/JungSooYeon823/portfolio/blob/main/2.RFM%20%EB%B6%84%EC%84%9D%20%EB%B0%8F%20%ED%81%B4%EB%9F%AC%EC%8A%A4%ED%84%B0%EB%A7%81%20%EA%B8%B0%EB%B0%98%20%EA%B3%A0%EA%B0%9D%20%EC%84%B8%EB%B6%84%ED%99%94%EB%A5%BC%20%ED%86%B5%ED%95%9C%C2%A0%EB%A7%9E%EC%B6%A4%20%EC%83%81%ED%92%88%20%EC%A0%9C%EC%95%88%20%EB%B0%8F%20%EC%84%B8%EA%B7%B8%EB%A8%BC%ED%8A%B8%20%ED%99%9C%EC%9A%A9%20%EC%A0%84%EB%9E%B5%20%EC%88%98%EB%A6%BD/README.md#-판매-트렌드)
	- [국가](https://github.com/JungSooYeon823/portfolio/blob/main/2.RFM%20%EB%B6%84%EC%84%9D%20%EB%B0%8F%20%ED%81%B4%EB%9F%AC%EC%8A%A4%ED%84%B0%EB%A7%81%20%EA%B8%B0%EB%B0%98%20%EA%B3%A0%EA%B0%9D%20%EC%84%B8%EB%B6%84%ED%99%94%EB%A5%BC%20%ED%86%B5%ED%95%9C%C2%A0%EB%A7%9E%EC%B6%A4%20%EC%83%81%ED%92%88%20%EC%A0%9C%EC%95%88%20%EB%B0%8F%20%EC%84%B8%EA%B7%B8%EB%A8%BC%ED%8A%B8%20%ED%99%9C%EC%9A%A9%20%EC%A0%84%EB%9E%B5%20%EC%88%98%EB%A6%BD/README.md#-국가)
	- [상품](https://github.com/JungSooYeon823/portfolio/blob/main/2.RFM%20%EB%B6%84%EC%84%9D%20%EB%B0%8F%20%ED%81%B4%EB%9F%AC%EC%8A%A4%ED%84%B0%EB%A7%81%20%EA%B8%B0%EB%B0%98%20%EA%B3%A0%EA%B0%9D%20%EC%84%B8%EB%B6%84%ED%99%94%EB%A5%BC%20%ED%86%B5%ED%95%9C%C2%A0%EB%A7%9E%EC%B6%A4%20%EC%83%81%ED%92%88%20%EC%A0%9C%EC%95%88%20%EB%B0%8F%20%EC%84%B8%EA%B7%B8%EB%A8%BC%ED%8A%B8%20%ED%99%9C%EC%9A%A9%20%EC%A0%84%EB%9E%B5%20%EC%88%98%EB%A6%BD/README.md#-상품)	
- [STAGE 3:RFM 분석](https://github.com/JungSooYeon823/portfolio/blob/main/2.RFM%20%EB%B6%84%EC%84%9D%20%EB%B0%8F%20%ED%81%B4%EB%9F%AC%EC%8A%A4%ED%84%B0%EB%A7%81%20%EA%B8%B0%EB%B0%98%20%EA%B3%A0%EA%B0%9D%20%EC%84%B8%EB%B6%84%ED%99%94%EB%A5%BC%20%ED%86%B5%ED%95%9C%C2%A0%EB%A7%9E%EC%B6%A4%20%EC%83%81%ED%92%88%20%EC%A0%9C%EC%95%88%20%EB%B0%8F%20%EC%84%B8%EA%B7%B8%EB%A8%BC%ED%8A%B8%20%ED%99%9C%EC%9A%A9%20%EC%A0%84%EB%9E%B5%20%EC%88%98%EB%A6%BD/README.md#-stage-3-RFM-분석)
	- [RFM Segment 특성 분석](https://github.com/JungSooYeon823/portfolio/blob/main/2.RFM%20%EB%B6%84%EC%84%9D%20%EB%B0%8F%20%ED%81%B4%EB%9F%AC%EC%8A%A4%ED%84%B0%EB%A7%81%20%EA%B8%B0%EB%B0%98%20%EA%B3%A0%EA%B0%9D%20%EC%84%B8%EB%B6%84%ED%99%94%EB%A5%BC%20%ED%86%B5%ED%95%9C%C2%A0%EB%A7%9E%EC%B6%A4%20%EC%83%81%ED%92%88%20%EC%A0%9C%EC%95%88%20%EB%B0%8F%20%EC%84%B8%EA%B7%B8%EB%A8%BC%ED%8A%B8%20%ED%99%9C%EC%9A%A9%20%EC%A0%84%EB%9E%B5%20%EC%88%98%EB%A6%BD/README.md#-RFM-Segment-특성-분석)
- [STAGE 4: K-means 클러스터링](https://github.com/faizns/Predict-Customer-Personality-to-Boost-Marketing-Campaign/blob/main/README.md#-stage-4-customer-personality-analysis)
	- [클러스터별 특성](https://github.com/JungSooYeon823/portfolio/blob/main/2.RFM%20%EB%B6%84%EC%84%9D%20%EB%B0%8F%20%ED%81%B4%EB%9F%AC%EC%8A%A4%ED%84%B0%EB%A7%81%20%EA%B8%B0%EB%B0%98%20%EA%B3%A0%EA%B0%9D%20%EC%84%B8%EB%B6%84%ED%99%94%EB%A5%BC%20%ED%86%B5%ED%95%9C%C2%A0%EB%A7%9E%EC%B6%A4%20%EC%83%81%ED%92%88%20%EC%A0%9C%EC%95%88%20%EB%B0%8F%20%EC%84%B8%EA%B7%B8%EB%A8%BC%ED%8A%B8%20%ED%99%9C%EC%9A%A9%20%EC%A0%84%EB%9E%B5%20%EC%88%98%EB%A6%BD/README.md#-클러스터별-특성)
 	- [클러스터별 활용 방안](https://github.com/JungSooYeon823/portfolio/blob/main/2.RFM%20%EB%B6%84%EC%84%9D%20%EB%B0%8F%20%ED%81%B4%EB%9F%AC%EC%8A%A4%ED%84%B0%EB%A7%81%20%EA%B8%B0%EB%B0%98%20%EA%B3%A0%EA%B0%9D%20%EC%84%B8%EB%B6%84%ED%99%94%EB%A5%BC%20%ED%86%B5%ED%95%9C%C2%A0%EB%A7%9E%EC%B6%A4%20%EC%83%81%ED%92%88%20%EC%A0%9C%EC%95%88%20%EB%B0%8F%20%EC%84%B8%EA%B7%B8%EB%A8%BC%ED%8A%B8%20%ED%99%9C%EC%9A%A9%20%EC%A0%84%EB%9E%B5%20%EC%88%98%EB%A6%BD/README.md#-클러스터별-활용-방안)
- [STAGE 5: 장바구니 분석](https://github.com/JungSooYeon823/portfolio/blob/main/2.RFM%20%EB%B6%84%EC%84%9D%20%EB%B0%8F%20%ED%81%B4%EB%9F%AC%EC%8A%A4%ED%84%B0%EB%A7%81%20%EA%B8%B0%EB%B0%98%20%EA%B3%A0%EA%B0%9D%20%EC%84%B8%EB%B6%84%ED%99%94%EB%A5%BC%20%ED%86%B5%ED%95%9C%C2%A0%EB%A7%9E%EC%B6%A4%20%EC%83%81%ED%92%88%20%EC%A0%9C%EC%95%88%20%EB%B0%8F%20%EC%84%B8%EA%B7%B8%EB%A8%BC%ED%8A%B8%20%ED%99%9C%EC%9A%A9%20%EC%A0%84%EB%9E%B5%20%EC%88%98%EB%A6%BD/README.md#-stage-5-장바구니-분석)
- [STAGE 6: 추천시스템](https://github.com/JungSooYeon823/portfolio/blob/main/2.RFM%20%EB%B6%84%EC%84%9D%20%EB%B0%8F%20%ED%81%B4%EB%9F%AC%EC%8A%A4%ED%84%B0%EB%A7%81%20%EA%B8%B0%EB%B0%98%20%EA%B3%A0%EA%B0%9D%20%EC%84%B8%EB%B6%84%ED%99%94%EB%A5%BC%20%ED%86%B5%ED%95%9C%C2%A0%EB%A7%9E%EC%B6%A4%20%EC%83%81%ED%92%88%20%EC%A0%9C%EC%95%88%20%EB%B0%8F%20%EC%84%B8%EA%B7%B8%EB%A8%BC%ED%8A%B8%20%ED%99%9C%EC%9A%A9%20%EC%A0%84%EB%9E%B5%20%EC%88%98%EB%A6%BD/README.md#-stage-6-추천시스템)
<br>
<br>

---

## 📂 **STAGE 0: 프로젝트 개요**

### 기획 의도
기존의 일반적인 상품 추천보다 고객의 특성과 선호도를 고려한 개인화된 상품 추천 서비스를 제공하여, 고객 만족도를 높이는 것이 목표 <br>
<br>

### 문제 정의
RFM 분석과 K-means 클러스터링을 통해 고도화된 고객 세분화를 통해, 보다 고객특성에 맞는 맞춤 상품 제안 .<br>
<br>

### 분석 목표 
고객 세분화 및 상품 추천 결과를 기반으로 한 효과적인 전략을 제시하여 ,매출 증대 및 이탈 방지

<br>
<br>

---
## 📂 **STAGE 1: 데이터 전처리**
### 결측치 & 중복 데이터 처리

 **구분** | **데이터 전처리**  | 
--------------------|--------------|
결측치 |  CustomerID 의 결측치는 약 25%, Description 은 0.27%로 ,분석에 편향이 발생할 수 있으므로, 삭제 처리
중복 데이터 |  중복 데이터 확인됨으로, keep=False로 설정하여, 중복 데이터 삭제 
<br>

### 변수 처리 

 **변수명** | **변수 설명** |
-----------------|--------------|
Year | 주문 년도 
Month | 주문 월
Day | 주문 일
Day_of_week | 주문 요일
YearMonthDay | 주문년도-월-일
YearMonth | 주문년도-월
Hour | 시간
Total_purchase | 제품단가 X 가격 => 총 구매금액



<br>
<br>

## 📂 **STAGE 2: EDA**
### 판매 트렌드

![20240117_142526](https://github.com/JungSooYeon823/portfolio/assets/121957252/c7cecfe5-24b7-4a23-86cf-9cd8f9f947c8)

-  2010-12 ~ 2011-08까지는 안정적인 판매추세를 보이나,2011-09~10월에 판매량이 급증 
- '2011-12 - 09일' 최대 매출 184170$ 달성 ⇒ 평균 매출 대비 543% 상승 시기

![20240117_142704](https://github.com/JungSooYeon823/portfolio/assets/121957252/dba038a8-f296-423c-87f2-480125f0d2de)

- 9월 기점으로 판매 금액 증가 추세 ⇒11월 최대 판매 금액 달성
- 목요일 낮 12시에 최대 매출이 발생하며,주로  평일 화~목요일/ 낮 12시~오후 14시의 판매량이 가장 우수하다.


### 국가
![20240117_142808](https://github.com/JungSooYeon823/portfolio/assets/121957252/c10d911e-d7c6-4a67-b0ad-c72171433ce5)

- 'United Kingdom'(영국)의 판매 점유율은 약 89%로, 과반수 이상의 매출을 점유하고 있다.
- 'Saudi Arabia' (사우디 아라비아)의 판매 금액이 가장 낮으며,약 0.023%의 점유율


### 상품
![20240117_142825](https://github.com/JungSooYeon823/portfolio/assets/121957252/e8ca0f9d-b74a-40ed-9580-60d1c9aa4e55)

- 가장 자주 구매하는 상품은  'WHITE HANGING HEART T-LIGHT HOLDER' (하얀색 하트 모양의 촛불 홀더)
- 가장 많은 수량 구매된 상품은 'PAPER CRAFT LITTLE BIRDIE' (종이로 만든 새모형)

  ⇒ 공통적으로 조명,장식품 등 상품이 상위 10위안에 랭크되어 있음을 알 수 있다.
  

---
## 📂 **STAGE 3: RFM분석**


![20240117_145214](https://github.com/JungSooYeon823/portfolio/assets/121957252/542d6bdf-76ed-46c7-953f-6a2d50c7fde2)




#### RFM Segment 특성 분석 

 **RFM Segment 구분** | **설명** |
-----------------|--------------|
VIP|가장 최근 활동/ 가장 높은 구매 빈도 /가장 높은 구매금액 (높은 가치 창출 고객)
Loyal custoemr|최근 활동 /VIP에 비해 낮은 구매 빈도/ VIP에 비해 낮은 금액 소진   (충성도 높은 고객)
Potential Loyalists|상대적으로 최근 구매 /높은 구매 빈도/ 높은 구매 금액  (잠재적 고객)
New customers| 최근 유입/ 낮은 빈도/낮은 구매 금액 (신규 고객)
Promising|평균적인 최근성/평균 빈도/평균 구매 금액 (가치를 높일 가능성 있는 고객)
Need Attention|낮은 구매 빈도/낮은 구매 금액  (관심이 필요한 고객)
About To Sleep|활동은 있었지만, 더 이상 활발하지 않은 고객 (잠들기 직전 고객)
Cannot lose them|평균 이하 최근성/낮은 구매 빈도/평균 구매 금액 값을 가진 고객(잃을수 없는 고객)
At-Risk |낮은 최근성/낮은 구매 빈도/평균 구매 금액 값을 가진 고객 (이탈 위험 고객)
Hibernating | 가장 낮은 최근성/가장 낮은 빈도를 가진 고객 


---
## 📂 **STAGE 4: K-means 클러스터링**
![20240117_143645](https://github.com/JungSooYeon823/portfolio/assets/121957252/8950c8c2-14ea-4a80-b012-0f329df0f2dd)

- Elbow Method : 6 / Silhoutette Score: 4
- 두 지표를 함께 고려하여, 클러스터 개수  4 선택 ⇒ 클러스터 4개로 분류했을때, 실루엣 계수는 0.442로 가장 높으며, 개별 군집의 평균 실루엣 계수 값이 비교적 균일하다.


#### 클러스터별 특성  
![다운로드](https://github.com/JungSooYeon823/portfolio/assets/121957252/b7cedecb-8899-4ef2-a087-a993e07ccda4)


#### 클러스터별 활용 방안

- #### Cluster 0 
	- 고객 세그먼트 특성
  		- 월별 지출 변동이 낮은편으로, 꾸준한 구매 패턴이 있지만 , 주문 빈도와 구매액은 가장 낮다.
    		- 홈 인테리어 소품 관련 상품을 선호한다.
   		- 낮12~ 14시에 집중적으로 구매하는 패턴이 있다.
   		- At-Risk(이탈 위험 고객) 43.4% , Cannot lose them(놓칠수 없는 고객) 23.3% 비중
  	- 고객 세그먼트 활용 전략
  		- At-Risk (이탈 위험 고객)
  			- 리워드 및 할인 제공: 추가 리워드나 할인을 제공하여 이탈 방지
  			- 설문조사 및 피드백 요청: 고객의 불만,이탈 원인을 파악하기 위해 설문조사요청  ⇒ 서비스나 상품 개선 시행.
		- Cannot lose Them(잃을수 없는 고객)
  			- 개인화된 혜택 제공: 할인, 멤버십 혜택, 또는 독점적인 프로모션을 통해 이탈 방지
  			- 특별한 이벤트 및 선점 기회 제공:특별한 이벤트나 선점 기회를 제공하여 구매 유도
  			- 낮 12~14시에 특별한 프로모션 제공
  	- 장바구니 분석 +추천시스템 활용 전략
  		- 홈 인테리어 관련 상품에 대한 개인화된 추천 서비스 제공.
  		- 이탈 위험이 있는 사용자에게는 이전에 관심을 보였던 상품, 카테고리를 중심으로 개인화된 상품 추천

- #### Cluster 1
	- 고객 세그먼트 특성
 		- 주문당 수량 및 주문당 구매액이 비교적 높은 그룹으로, 대량 구매를 선호하는 구매 패턴
   		- 이벤트나 파티에 사용되는 상품을 선호한다.
     		- Promising (유망한 고객) 38.6% ,About to sleep(잠들기 직전 고객 ) 31.4% 비중
       - 고객 세그먼트 활용 전략
       		- Promising(유망한 고객)
         		- 추가 혜택 및 프로모션 제공: 추가 혜택이나 독점적인 프로모션을 제공하여 더 많은 구매를 유도
           		- 추가 서비스 및 제품 소개:신규 서비스나 제품을 소개하여 구매 유도
             	-  About To Sleep (곧 잠들 예정의 고객 )
              		- 개인화된 알림 및 특별 제안 제공: 개인화된 알림이나 특별 제안을 통해 다시 관심을 유도
                	- 재구매 유도 프로그램 도입: 재구매를 유도하는 CRM 메세지 전송 및 리텐션 마케팅 진행
                 	- 포인트 및 할인 유도 :추가 포인트나 할인을 제공하여 구매 유도
	- 장바구니 분석 +추천시스템 활용 전략
 		- 추가 구매를 유도하는 번들 상품 제안:장바구니에 담긴 상품 간의 연관성을 고려하여,번들 상품을 제안
   		- 개인화된 추천 시스템 : 이벤트 상품을 구매하는 경향으로 관련 상품 추천
 

- #### Cluster 2
	- 고객 세그먼트 특성
 		- 월별 지출 변동이 큰 편으로, 10~12월 겨울 시즌에 구매가 활발한 패턴을 보인다. 
   		- 주문당 수량 및 주문당 구매액이 비교적 낮은 것으로, 소량 구매를 선호하는 구매 패턴
     		- 크리스마스 관련 상품 및 런치백 등의 잡화류 상품을 선호한다.
       		- Loyal customer(충성 고객) 37.3%,New customer(신규 고객) 35.2% 비중 
       - 고객 세그먼트 활용 전략
       		- Loyal Customer (충성 고객)
         		- 추가 혜택 및 리워드 프로그램: 충성도를 인정하고 보상하는 리워드 프로그램을 제공하여 계속해서 구매 유도.
           		- 개별적인 감사 메세지: 고객에게 개별적으로 감사의 뜻을 전하는 메시지 전송
             	-  New Customers (신규 고객)
              		- 환영 혜택 및 할인 제공:초기 구매에 대한 환영 혜택이나 할인을 제공하여, 브랜드에 대한 긍정적인 경험을 제공
                	- 계절 별 프로모션 및 할인:겨울 시즌에 특화된 할인 프로그램 도입하여 계절에 따른 구매를 유도. 
	- 장바구니 분석 +추천시스템 활용 전략
 		- 시즌별 상품 추천 :선호도 분석을 통해 겨울 시즌에 가장 선호하는 상품 식별 및 계절 상품 추천 
   		

- #### Cluster 3
	- 고객 세그먼트 특성
 		- 주문 건수와 총 구매액이 가장 높은 그룹
   		- 다른 클러스터 대비 비교적 다양한 상품에서 선호도가 나타남
     		- VIP 66.7%,Potential Loyalists(유망한 충성 고객) 24.9%
       - 고객 세그먼트 활용 전략
       		- VIP 고객
         		- VIP 멤버십 프로그램 운영: VIP와 Potential Loyalists 그룹에 대한 멤버십 프로그램 도입.
           		- 선점적인 새로운 상품 소개:새로운 상품이나 서비스를 먼저 체험할 수 있는 기회를 제공하여 로얄티 증대
             		- 우선 배송 및 서비스 제공:빠른 배송 서비스나 24시간 고객 서비스 등을 우선적으로 제공
             	-  Potential Loyalists (잠재적 충성고객)
              		- 추가 혜택 및 가치 제시:높은 구매 빈도와 금액에 대한 추가 혜택을 제시하여, 실제 충성고객으로 성장하도록 유도
                	- 추가 서비스 및 소식 제공 : 최신 상품이나 이벤트에 대한 정보를 제공하여, 고객의 참여를 유도 
	- 장바구니 분석 +추천시스템 활용 전략
 		- 최근 구매 이력 기반 추천:VIP 및 Loyal Customer의 최근 구매 이력을 기반으로 ,유사한 상품 추천
   		- 고가 상품 및 프리미엄 아이템 추천:높은 구매 빈도와 금액을 갖는 이 세그먼트에게는 고가 상품이나,프리미엄 아이템을 중심 추천




## 📂 **STAGE 5: 장바구니 분석**

![khk](https://github.com/JungSooYeon823/portfolio/assets/121957252/aca7f04c-caec-458a-9130-8a19a0a56cf5)

- 지지도  0.2이상,신뢰도 0.7이상 연관규칙 5가지 도출

  ⇒ 두 제품 간의 연관성이 높으므로, 이를 함께 마케팅하거나 특별한 할인 혜택을 제공할 수 있다.

  ⇒ 이를 함께 판매하는등의 상품 번들구성을 기획할 수 있다.   

## 📂 **STAGE 6: 추천시스템**

![20240117_145046](https://github.com/JungSooYeon823/portfolio/assets/121957252/a42424ac-47c3-4f42-8547-f9a12c8edcac)

- 클러스터 기반 추천 시스템
	- 사용자를 클러스터로 그룹화하여 취향 파악 ⇒ 각 클러스터에 대한 추천 제공
 	- 이미 구매한 상품을 제외하고, 클러스터와 고객 기반으로 n개의 상품을 추천 

