# 신용평가모형을 활용한 대구지역 지역 소멸 등급 5등급 체계 구축 : 대구지역 활성화 방안

> ## 1. 분석개요
본 프로젝트는 대구광역시의 읍면동 단위 등급 체계를 구축하고, 신용평가모형을 활용한 지방소멸 위험도 분석을 통해 정책 가이드를 제공하는 것을 목표로 합니다. 이를 통해 지역별 특성을 고려한 맞춤형 활성화 방안을 제시하고자 합니다.

### 1️⃣ 지방소멸 위험 지역 식별
- 신용평가모형을 활용하여 대구광역시 읍면동별 지방소멸 위험도를 분석합니다.
- 소멸 위험이 높은 지역을 정확히 파악하여, 지역별 특성을 반영한 맞춤형 정책 수립의 기초 자료를 제공합니다.
### 2️⃣ 대구광역시 정책 방향 제시
- 분석 결과를 바탕으로 각 읍면동에 적합한 정책 가이드를 제시합니다.
- 현재 및 미래의 지방소멸 문제 해결을 위한 실질적인 방안을 마련합니다.
### 3️⃣ 신용평가모형 활용
- 금융기관에서 사용하는 신용평가모형을 지방소멸 문제에 적용하여 차별화된 분석을 수행합니다.
- 기존 경제 지표 및 인구 통계 기반 예측 방식보다 정밀하고 과학적인 예측 결과를 도출합니다.
### 4️⃣ Tableau 대시보드 구축
- 신용평가모형의 분석 결과를 시각적으로 표현하는 Tableau 대시보드를 구축합니다.
- 정책 결정자, 관련 기관, 일반 시민들이 데이터를 쉽게 해석하고 활용할 수 있도록 지원합니다.

> ## 2. 분석배경
<img src="https://github.com/user-attachments/assets/e04c41fa-4be8-4b9c-9311-7f89effd19a6" width="800">
<img src="https://github.com/user-attachments/assets/0ef7456b-4713-4bb0-8891-bc4e5044987a" width="800">

#### ■ 대구광역시의 인구 감소 문제: 지역사회 발전과 지속 가능성은 인구 동태에 영향을 받지만, 대구는 심각한 인구 감소에 직면해 있음.

#### ■ 청년층 수도권 유출: 2022년 기준, 대구에서 1만 1519명의 순유출 발생, 특히 20대 청년층의 유출이 두드러짐.

#### ■ 산업 구조 문제: 대기업 본사·공장·연구소 부족, 중소기업 비중이 높은 산업 구조로 인해 주요 대학 졸업생들이 타 지역으로 유출되는 현상이 지속됨.

> ## 3. 분석요약
### 1️⃣ 활용 데이터
<table border="1">
    <thead>
        <tr>
            <th>부문</th>
            <th>세부 항목</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><strong>인구 부문</strong></td>
            <td>주민등록인구 및 세대 현황, 고령 인구, 20~39세 여성 인구</td>
        </tr>
        <tr>
            <td><strong>경제 부문</strong></td>
            <td>현대카드 나이대별 매출 데이터, 총 종사자 수</td>
        </tr>
        <tr>
            <td><strong>생활서비스 부문</strong></td>
            <td>은행·부동산업 종사자 수</td>
        </tr>
        <tr>
            <td><strong>여가생활 부문</strong></td>
            <td>생활체육시설·노래방 종사자 수</td>
        </tr>
        <tr>
            <td><strong>음식 부문</strong></td>
            <td>카페·패스트푸드 종사자 수</td>
        </tr>
        <tr>
            <td><strong>교육 부문</strong></td>
            <td>기술직업훈련·어린이보육원·초등·중등·고등학교·어학원 종사자 수</td>
        </tr>
        <tr>
            <td><strong>교통 부문</strong></td>
            <td>이륜차·PM 사고 건수, 교통량</td>
        </tr>
        <tr>
            <td><strong>공공 부문</strong></td>
            <td>경찰·행정기관 종사자 수</td>
        </tr>
    </tbody>
</table>

### 2️⃣ 분석 도구
Python, QGIS, Tableau, SQL

### 3️⃣ 분석 기법
신용평가모형 개발 (scorecardpy)

- 모델링 및 변수 선택
  1. 로지스틱 회귀모형
  2. Information Value (IV) 기반 변수 선택
  3. WOE Binning (계급 세분화)
  4. Fine classing & Coarse classing
  5. K-S 통계량 기반 변수 선택
  6. 독립 표본 t-검정 (Independent Samples t-test)
  7. 스피어만 상관계수 기반 다중공선성 확인
  8. LASSO 회귀모형을 활용한 변수 선택

모형 성능 및 안정성 평가
- AUROC, K-S 통계량, PSI(모형 안정성 평가)
- Score 등급화 및 위험률 역전 현상 확인

> ## 4. 분석방법

### 4.1 데이터 수집 및 구축

### 1️⃣ 종속 변수 정의: 지방소멸위험지수
<img src="https://github.com/user-attachments/assets/9c755564-5dba-48b6-9ce8-1f1cf2579a0f" width="1000">

- 정의: 만 20 ~ 39세 여성 인구를 만 65세 이상 인구로 나눈 값으로, 일본 사회학자 마스다 히로야가 처음 개념화한 지표입니다.

위험 기준:
<table border="1">
    <thead>
        <tr>
            <th>소멸위험지수</th>
            <th>위험 수준</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1.5 이상</td>
            <td>소멸 저위험</td>
        </tr>
        <tr>
            <td>1.0 ~ 1.5</td>
            <td>보통</td>
        </tr>
        <tr>
            <td>0.5 ~ 1.0</td>
            <td>주의</td>
        </tr>
        <tr>
            <td>0.2 ~ 0.5</td>
            <td>소멸 위험</td>
        </tr>
        <tr>
            <td>0.2 미만</td>
            <td>소멸 고위험</td>
        </tr>
    </tbody>
</table>


분류 방식:
- 지방소멸위험지수 < 0.5 → 소멸 위험 지역(1)
- 지방소멸위험지수 ≥ 0.5 → 비위험 지역(0)

각 동별 만 65세 이상 인구 및 만 20~39세 여성 인구를 추출하여 지방소멸위험지수를 계산하고, ‘위험 여부’ 변수(0 또는 1)를 생성하였습니다.

### 2️⃣ 독립 변수 선정 기준
본 분석은 대구광역시 읍면동 등급 체계를 구축하고 정책 가이드를 제공하는 것이 목적이므로, 지역의 부족한 부분과 활성화가 필요한 요소를 판단하기 위해 다양한 부문에서 독립 변수를 선정하였습니다.

<table border="1">
    <thead>
        <tr>
            <th>부문</th>
            <th>목적</th>
            <th>변수</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><strong>인구 부문</strong></td>
            <td>지역 내 인구 구조 및 변화에 따른 사회·경제적 영향을 예측</td>
            <td>1인·2인·3~4인·5~6인·7인 가구 수, 상주 인구, 세대 수, 세대당 인구수, 남녀 인구수, 남녀비율</td>
        </tr>
        <tr>
            <td><strong>경제 부문</strong></td>
            <td>경제 활성화 수준과 기술 발전 정도 예측</td>
            <td>총 종사자 수, 나이대별 매출액</td>
        </tr>
        <tr>
            <td><strong>소매업 부문</strong></td>
            <td>상업 시설 활성화 정도 분석 및 소상공인 역할 평가</td>
            <td>백화점·중대형마트 종사자 수, 편의점 종사자 수</td>
        </tr>
        <tr>
            <td><strong>생활서비스 부문</strong></td>
            <td>지역 내 생활 편의성과 서비스 품질 평가</td>
            <td>은행 종사자 수, 부동산업 종사자 수</td>
        </tr>
        <tr>
            <td><strong>여가생활 부문</strong></td>
            <td>문화시설 발전 수준 및 주민 여가생활의 풍요도 예측</td>
            <td>생활체육시설 종사자 수, 노래방 종사자 수</td>
        </tr>
        <tr>
            <td><strong>음식 부문</strong></td>
            <td>지역 내 음식 서비스 활성화 정도 예측</td>
            <td>카페 종사자 수, 패스트푸드 종사자 수</td>
        </tr>
        <tr>
            <td><strong>교육 부문</strong></td>
            <td>교육 인프라 및 지역 내 교육 환경 발전 수준 평가</td>
            <td>어린이보육원, 초·중·고등학교, 어학원 종사자 수</td>
        </tr>
        <tr>
            <td><strong>교통 부문</strong></td>
            <td>지역 내 교통 안전 및 이동 편의성 분석</td>
            <td>교통량, 이륜차·PM 사고 건수</td>
        </tr>
        <tr>
            <td><strong>공공 부문</strong></td>
            <td>행정 및 공공 서비스 수준 평가</td>
            <td>경찰 종사자 수, 행정기관 종사자 수</td>
        </tr>
        <tr>
            <td><strong>건축 부문</strong></td>
            <td>부동산 시장 및 주거 환경 개선 분석</td>
            <td>아파트 실거래 매매 횟수, 지가변동률</td>
        </tr>
    </tbody>
</table>


### 3️⃣ 데이터 병합 및 시계열 처리
- 각 부문별 데이터를 하나의 데이터 프레임으로 통합하기 위해, 하위 행정동을 최상위 행정동 단위로 변환하여 행정동, 년도, 분기 기준으로 **합산(SUM)**하여 독립 변수를 계산하였습니다.
- 다만, 일부 변수(지방소멸위험지수, 지가변동률, 세대당 인구수, 남녀비율)는 비율형 데이터이므로, 하위 행정동 수만큼 나누어 평균값을 계산하였습니다.
- 혁신동(2020년 10월 생성)과 유천동(2021년 11월 생성)은 현대카드 데이터에서 각각 안심동과 진천동으로 카운트되었기 때문에, 안심동·진천동 데이터로 변환하여 처리하였습니다.

### 4.2 신용평가모형 개발과정 - scorecardpy in python
본 연구는 신용평가모형(scorecardpy)을 활용하여 지방소멸 위험도를 평가하고, 데이터 기반 정책 수립을 위한 과학적 접근법을 제시하는 것을 목표로 합니다. 이를 위해 IV(정보 가치), WOE 변환, 로지스틱 회귀, LASSO, KS 통계량, AUC 평가 등 다양한 분석 기법을 적용하여 최적의 변수 선정 및 예측 모델 구축을 수행하였습니다.

### 1️⃣ Scorecardpy 개요
- Scorecardpy는 신용 점수카드 모델을 개발하는 파이썬 라이브러리로, 정보 가치(IV) 계산, WOE 변환, 신용평가 모델링 등을 지원합니다.
- 이를 활용하여 지방소멸 위험도 점수를 산출하고, 등급 분류 체계를 구축하였습니다.

### 2️⃣ 변수 선택 과정
<table border="1">
    <thead>
        <tr>
            <th>단계</th>
            <th>설명</th>
            <th>제외된 변수</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><strong>1차 변수 선택</strong><br>(IV 기반 변수 제거)</td>
            <td>
                - IV(정보 가치): 예측 변수의 유용성을 평가하는 지표로, 값이 높을수록 종속 변수(소멸 위험) 예측에 중요함.<br>
                - 기준: IV 값이 0.3 미만인 변수를 제거하여 모델의 복잡성을 줄이고 계산 효율성을 향상.<br>
                - 예외 변수: '현대카드 나이대별 매출액'은 중요도가 높아 1차 제거 대상에서 제외하고 2차 변수 선택에서 평가.
            </td>
            <td>'1인가구수', '2인가구수', '3~4인가구수', '남자인구수', '상주인구', '세대수', '여자인구수'</td>
        </tr>
        <tr>
            <td><strong>2차 변수 선택</strong><br>(WOE 변환 및 계급 세분화)</td>
            <td>
                - Fine Classing (계급 세분화): 변수 값을 세분화하여 독립변수와 종속변수(소멸 위험) 간 관계를 명확히 분석.<br>
                - Coarse Classing (성김화): 너무 세밀하게 분할된 구간을 합쳐 모델의 안정성 및 해석력 향상.<br>
                - WOE(Weight of Evidence) 기반 변환: 종속 변수와의 관계를 분석하여 유사한 불량률을 가진 범주를 하나로 묶음.<br>
                - 계급 내에서 불량률이 순차적으로 증가하도록 역전 현상 방지.
            </td>
            <td>적용 변수: 총 41개 독립변수(5~6인가구수, 남녀비율, 금융업 종사자수, 교통량 등)</td>
        </tr>
        <tr>
            <td><strong>3차 변수 선택</strong><br>(KS 통계량 및 독립 표본 t-검정)</td>
            <td>
                - KS(Kolmogorov-Smirnov) 통계량: 두 그룹(소멸 위험 지역 vs 비위험 지역) 간의 차이를 정량적으로 평가.<br>
                - 독립 표본 t-검정: 변수별 평균 차이가 유의미한지 검증.
            </td>
            <td>'지가변동률' (유의미한 차이가 없음)</td>
        </tr>
        <tr>
            <td><strong>4차 변수 선택</strong><br>(스피어만 상관 계수를 활용한 다중공선성 제거)</td>
            <td>
                - 스피어만 상관 계수: 변수 간 높은 상관관계를 분석하여 다중공선성 문제 방지.
            </td>
            <td>'어린이보육업종사자수_woe', '편의점종사자수_woe', '주택수_woe'</td>
        </tr>
        <tr>
            <td><strong>최종 변수 선택</strong><br>(로지스틱 회귀 및 LASSO 적용)</td>
            <td>
                - LASSO (L1 규제)를 적용하여 모델의 복잡도를 줄이고 과적합 방지.
            </td>
            <td>'생활체육시설종사자수', '남녀비율', 'MAN_SALE_AMT_10G_woe'</td>
        </tr>
    </tbody>
</table>

### 3️⃣ 모델 평가: KS 통계량 및 AUC
<table border="1">
    <thead>
        <tr>
            <th>지표</th>
            <th>학습 데이터</th>
            <th>검증 데이터</th>
            <th>설명</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><strong>KS(Kolmogorov-Smirnov) 통계량</strong></td>
            <td>0.7824</td>
            <td>0.7942</td>
            <td>모형이 소멸 위험 지역과 비위험 지역을 잘 구분하고 있음을 의미</td>
        </tr>
        <tr>
            <td><strong>AUC(Area Under the ROC Curve)</strong></td>
            <td>0.9527</td>
            <td>0.963</td>
            <td>높은 AUC 값 → 모델의 예측 성능이 우수함을 의미</td>
        </tr>
    </tbody>
</table>

### 4️⃣ 소멸 위험 등급화 및 역전 현상 방지
- 로지스틱 회귀 기반 스코어 카드 생성
- 읍면동별 소멸 위험도를 5개 등급으로 분류
- 각 등급 간 위험도가 순차적으로 증가하도록 설계하여 역전 현상 방지
