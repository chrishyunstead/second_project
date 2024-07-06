# second_project(팀 프로젝트)
![image](OOF_배경화면.jpg)
# OOF(Oracle of Football) 플랫폼구축 프로젝트

## 기획 목표: 유럽5대축구리그의선수및경기내용Data를기반으로 구현한 기능서비스를 통해 축구스카우터, 게임유저 및 팬들에게 경쟁력있는 서비스제공

## R&R: 데이터전처리, 머신러닝/딥러닝모델학습및구현

## 서비스기능 
1) 신규선수속성에대한유망주여부예측
2) 신규선수속성에대한포지션별유사선수분류조회
3) 선수별속성비교시각화
4) Langchain기반선수정보데이터분석Chatbot
5) 딥러닝(Softmax) 기반승부예측
6) Langchain기반경기내용조회Chatbot
7) Langchain기반Foot-Ball RSS(Rich Site Summary) 요약봇


## 서비스 타겟
1) 축구팀스카우터
2) 축구게임(FIFA, FM, FC 등) 유저
3) 해외및국내축구팬

###  데이터 속성 정리

#### 1) FM INSIDE
데이터 소개: 전세계축구리그및팀소속스카우들이선수에대한포지션별속성을수치화한데이터
데이터 출처: FM Inside (https://fminside.net)
수집방법 및 건수: 크롤링(Selenium, BeautifulSoup) / 25,862건
활용방안: LangChain기반선수분석Chatbot / 유망주& 선수별잠재력예측 / 포지션별유사선수클러스터링

#### 2) FOTMOB
데이터 소개: 23~4년도유럽5대축구리그별경기결과& 출전선수라인업
데이터 출처: TransformMarkt(https://transfermarket.com)
수집방법 및 건수: 크롤링(Selenium, BeautifulSoup) / 12,913 건
활용방안: Langchain기반경기내용조회Chatbot / 팀, 포지션별속성수치기반으로승부예측

#### 3) TransferMarket
데이터 소개: 24년도유럽5대축구리그1~5부선수별Market Value
데이터 출처: FotMob(https://fotmob.com)
수집방법 및 건수: 크롤링(Selenium, BeautifulSoup) / 1,471건
활용방안: 포지션별유사선수클러스터링 / 선수Market Value예측


### 프로젝트 수행 내용

### AI모델링(1): ML / 유망주 & 선수별 능력치 및 잠재력 예측
  - 활용데이터 : FMInside사이트의Players 속성Values
  - 활용용도 (1) : 데이터에의해 학습된 머신러닝모델로 능력치 및 잠재력 예측모델 구축
  - 활용용도 (2) : 능력치에 의거한 유망한 선수 판별가능
  - 코드 링크: (능력치 및 잠재력 예측/수비수_능력치, 잠재력 예측.ipynb)

### AI모델링(2): ML / 포지션별 유사선수 분류 및 조회 
  - 활용데이터 : FMInside사이트의Players 속성Values
  - 활용용도 (1) : 포지션별주요능력치를KNN 모델에학습
  - 활용용도 (2) : 주요능력치와유사한10명의선수분류, 조회
  - 코드 링크: (KNN 유사선수 분류/Knn_DC (2).ipynb)

### AI모델링(3): ML / 선수 Market Value 예측 
  - 활용데이터 : FMInside사이트의Players 속성Values, Transform Market의24년도유럽5대축구리그1~5부선수별Market Value
  - 활용용도 : 포지션별능력치, 잠재력속성을24년도선수별Market Vlaue와맵핑해선수별Market Value예측모델구축
  - 코드 링크: (몸값 예측/수비수(DC)몸값예측.ipynb)


### AI모델링(4): DL / 승부 예측 
  - 활용데이터 : FMInside사이트의Players 속성Values, FotMob23~4년도유럽5대축구리그별경기결과& 출전선수라인업
  - 활용용도 : 포지션별평균능력치와23~4년도경기결과를토대로승부예측딥러닝모델학습
  - 코드 링크: (승부예측/승부예측.ipynb)

#### 중점사항
- WBS상시확인▶과업별 진도파악을 통한 기한내 프로젝트 완성에 주력
- 코드컨벤션기반 코딩 주력▶생산성 향상 및 코드인계간 빠른 의사결정으로 과업진행
- 데이터EDA 및 리뷰 강조
- 기능별 구현을 위한 다양한 함수(머신러닝, 딥러닝내장함수)적용 및 리뷰, 선정
- 주사용자, 즉 고객입장에서의 서비스/기능정의 및 구현에 주력
- 기능구현별 코드 최적화를 위한 상시코드 디버깅 작업
 
 #### 미흡사항
- 모델 튜닝할 시간이 부족
- 함수정의및호출기반의코딩습관부족
- 라이브러리별버젼충돌에대한상황조치의숙달정도부족

#### 스트림릿
https://sayoof-adios.streamlit.app/
