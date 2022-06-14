
# 시대상황을 반영한 도서 트렌드 분석

### “책은 시대상황과 연관이 있을까?”

데이터 출처 :    
(교보문고 베스트셀러) http://www.kyobobook.co.kr/bestSellerNew/bestseller.laf?orderClick=D0a   
(네이버쇼핑- 도서) https://search.shopping.naver.com/search/category/100006534

## 목적
<img src="https://user-images.githubusercontent.com/97740175/173655617-51f66438-9bb2-4ae4-a56e-a4cdcc03cee1.png" width="60%" height="60%"></img>


#### *"왜 경제코너에는  주식에  대한 책만 많을까?"*

이 프로젝트는 서점에 판매되는 비슷한 책제목에 대한 호기심에서 시작됐습니다.     
왜 분야마다 특정 키워드에 대한 책이 많이 진열되어있는지 궁금했고, 어쩌면 “현시대의 트렌드가 책에  반영”   될수도 있다는 생각이 들었습니다.    
그동안 배운 파이썬과 분석툴을 이용해 실제로 트렌드는 책과 연관성이 있는지 알아보기로 했습니다.   

## 기간
2021.01.14 - 2021.01.21  (1주일)

## 팀 구성
본인 외 3인

## 팀 내 역할
데이터 분석과 시각화, flask와 bootstra를 이용한 웹구현

## 사용 기술
python, HTML

## 개발 과정 
#### 분석내용

교보문고의 베스트 셀러와 네이버쇼핑의 최근 도서목록을 웹스크래필 해왔습니다   
도서의 경우 카테고리가 잘 나눠져 있어 분석에 용이하다는 선정이유도 있었습니다.

#### 가설설정
데이터를 통해 검증하기 위한 가정을 5가지 세웠습니다.  

첫번째로, 책은 시대상황을 정말 반영할까? 입니다.    
확실한 데이터 비교를 위해 시대상황이 가장 빠르게 바뀌었던 코로나 발생을 기준으로 전후2년씩 총4년의 베스트셀러 분야와 도서명을 분석했습니다.  

두번째로, 전체카테고리 중에서 시대상황에 더 민감하게 반영될것이라 예측되는 4개의 분야를 선정했습니다. 경제/경영, 여행, 컴퓨터/it, 취미/여가 분야를 선정했습니다.  

1. 경제/경영 :  코로나 이후 불안정한 고용환경의 영향으로 비트코인이나 주식등 투자분야가 강세를 보일것이다.  
2. 여행: 해외여행이 불가능해지면서 국내여행과 제주도에 대한 관심이 증가할것이다.
3. 컴퓨터/it: 디지털 산업에 대한 정부의 투자와 인공지능에 대한 관심으로 AI관련 키워드가 많을 것이다. 
4. 취미/여가: 외부활동이 제한 되면서 실내에서 할 수 있는 취미활동이 증가할것이다.

### 웹페이지
- 구성
<img src="https://user-images.githubusercontent.com/97740175/173659741-e70c15c5-c371-4e21-86c6-a01bdb610f1c.png" width="60%" height="60%"></img>
> - index.html : 그림한장과 그림을 클릭하면 다음페이지인, index페이지로 넘어갑니다
> - index2.html : 프로젝트에 대한 설명페이지입니다. 이어지는 다음 페이지는 main페이지입니다. 상단에 navbar로 페이지 이동이 가능합니다
> - main.html : 시각화 자료롸 분석 결과를 표시합니다. 페이지는 스크롤박스로 구성되어있습니다. 각 분석 파트마다 스크롤 네비게이션으로 이동이 가능합니다.
> - team.html : 팀구성원을 표시합니다. navbar로 이동가능하게 구현되었습니다. 
> - thx.html : main페이지에서 이동되는 인사페이지입니다.

### 1. 스크래핑
네이버쇼핑에서 데이터를 수집하기 위해 UIPath를 이용해 스크래핑했습니다. 타게팅 과정중 페이지에 한번에 모든 목록이뜨지않는 문제를 스크롤 액티비치로 해결했습니다.
 
### 2. 전처리
스크래핑이 완료된 데이터의 전처리를 진행했습니다. 스크래핑 과정 중 공백문자가 문자열로 인식된 경우, 제공된 디테일 데이터중 빈칸이있어 각 영화당 리스트의 길이가 달라지는 경우의 문제를 처리했습니다. 


### 4. 시각화를 통한 분석
* 파이차트
종합 베스트 셀러 분야별 키워드를 파이차트로 표현했습니다.

* 막대그래프
종합 베스트셀러 분야별 키워드를 막대그래프로 표현했습니다
년도와 빈도수를 축으로 삼아 막대그래표 표시

* 워드클라우드
데이터프레임에서 필요한 컬럼의 내용을 가져와 형태소 분석기로 키워드 딕셔너리를 생성했습니다.   
딕셔너리 데이터로 마스크 이미지를 씌운 워드클라우드로 빈도 시각화를 진행했습니다

### 결론

도서는 시대상황을 어느정도 반영하지만, 충분히 반영되기 위해서는 한해정도의 기간이 필요하다 판단했습니다

-------------------------

## 회고
- flask를 활용하여 발표를 하게된다 생각하여 페이지를 구상하는것에 맞춰 페이지를 구성했었습니다. 그러다보니 웹페이지보단 발표용 ppt를 대신하는 발표용 사이트로만 구현이 된것같은 부분이 조금 아쉽습니다. 저희조는 분석과 시각화가 중점이었고, 그마져도 분석결과를 한페이지에 긴 스크롤 형식으로 만들었기에 많은 페이지가 필요하진않았습니다. 그래서 좀더 추가해보고자 처음과 마지막같은 불필요한 페이지가 들어간것도 같습니다.
