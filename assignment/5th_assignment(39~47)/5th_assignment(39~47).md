# Fifth Study Week

- 38강: [퀵테이블계산(2)](#38-퀵테이블계산2)

- 39강: [LOD](#39강-lod)

- 40강: [EXCLUDE](#40-lod-exclude)

- 41강: [INCLUDE](#41-lod-include)

- 42강 : [매개변수](#42-매개변수)

* (43강이 없어 패스합니다)
- 44강: [매개변수 실습](#44-매개변수-실습)

- 45강: [마크카드](#45-워크시트-마크카드)

- 46강: [서식계층](#46-서식-계층)

- 47강: [워크시트](#47-워크시트-서식)

- [문제1](#문제-1)

- [문제2](#문제-2)

- [문제3](#문제-3)

## Study Schedule

| 강의 범위     | 강의 이수 여부 | 링크                                                                                                        |
|--------------|---------|-----------------------------------------------------------------------------------------------------------|
| 1~9강        |  ✅      | [링크](https://www.youtube.com/watch?v=AXkaUrJs-Ko&list=PL87tgIIryGsa5vdz6MsaOEF8PK-YqK3fz&index=84)       |
| 10~19강      | ✅      | [링크](https://www.youtube.com/watch?v=AXkaUrJs-Ko&list=PL87tgIIryGsa5vdz6MsaOEF8PK-YqK3fz&index=75)       |
| 20~29강      | ✅      | [링크](https://www.youtube.com/watch?v=AXkaUrJs-Ko&list=PL87tgIIryGsa5vdz6MsaOEF8PK-YqK3fz&index=65)       |
| 30~39강      | ✅      | [링크](https://www.youtube.com/watch?v=e6J0Ljd6h44&list=PL87tgIIryGsa5vdz6MsaOEF8PK-YqK3fz&index=55)       |
| 40~49강      | 🍽️      | [링크](https://www.youtube.com/watch?v=AXkaUrJs-Ko&list=PL87tgIIryGsa5vdz6MsaOEF8PK-YqK3fz&index=45)       |
| 50~59강      | 🍽️      | [링크](https://www.youtube.com/watch?v=AXkaUrJs-Ko&list=PL87tgIIryGsa5vdz6MsaOEF8PK-YqK3fz&index=35)       |
| 60~69강      | 🍽️      | [링크](https://www.youtube.com/watch?v=AXkaUrJs-Ko&list=PL87tgIIryGsa5vdz6MsaOEF8PK-YqK3fz&index=25)       |
| 70~79강      | 🍽️      | [링크](https://www.youtube.com/watch?v=AXkaUrJs-Ko&list=PL87tgIIryGsa5vdz6MsaOEF8PK-YqK3fz&index=15)       |
| 80~89강      | 🍽️      | [링크](https://www.youtube.com/watch?v=AXkaUrJs-Ko&list=PL87tgIIryGsa5vdz6MsaOEF8PK-YqK3fz&index=5)        |


<!-- 여기까진 그대로 둬 주세요-->

> **🧞‍♀️ 오늘의 스터디는 지니와 함께합니다.**

## 38. 퀵테이블계산(2)

<!-- 이동평균, YTD 총계, 전년 대비 성장률, YTD 성장률 등 본 강의에서 알게 된 점을 적어주세요 -->

- 이동평균
    - 이전의 값부터 현재까지 값에 대한 평균
    - 주식 데이터에 주로 사용

- YTD 총계
    - 특정 시점을 기준으로 해당 연도부터 그 시점까지 총계
    - 기본적으로 누계와 같은 개념이지만 연도보다 하위레벨 필드인 __분기 또는 월이 있어야 사용할 수 있음__
    - 태블로에서는 기본적으로 각 년도의 매출의 누계가 월별로 작성됨

- 전년 대비 성장률
    - 같은 월을 기준으로 이전 년도 대비 얼마 정도 성장했는지를 살펴보는데 활용
    - 데이터 상 첫 번째 년도는 이전 년도의 데이터가 없기 때문에 공백으로 표시

- YTD 성장률
    - 퀵 테이블 계산 => YTD 성장률
    - 성장률 값을 확인하기 위해 매출 필드를 더블 클릭 => 측정값 필드에 있는 계산된 매출 필드 더블 클릭 => 오류 메시지 발생 ( 단일 계산식이 아니기 때문 )
    - 계산된 매출 필드를 컨트롤 누른 채 데이터 패널로 드래그 앤 드랍 => 계산 1, 계산 1 1 생성
    - 계산 1 : YTD 총계, 계산 1 1 : YTD 성장률 

## 39강. LOD

<!-- INCLUDE, EXCLUDE, FIXED 등 본 강의에서 알게 된 LOD 표현식에 대해 알게 된 점을 적어주세요. -->

- LOD
    - Level of Detail, 뷰의 세부 수준
    - 현재 뷰에는 영향을 받지 않고, 본인이 원하는 세부 수준에서 계산을 수행할 수 있음
    - 계산할 수준을 세부적으로 제어 가능함
    - ex) 측정값에 매출, 행에 지역 필드를 넣으면 지역별로 매출의 합계가 표현됨 => 현재 차원이 '지역'이기에 '지역' 차원의 수준에 따라 매출이 계산되고 있음

- FIXED LOD
    - 현재 뷰에 있는 차원과 상관없이 계산된 필드에서 원하는 차원을 따라 계산함
    1. FIXED에서 설정한 차원이 뷰에 포함되어 있을 때
    
    ![5th_assignment_01](../5th_assignment(39~47)/5th_assignment_image/5th_assignment_01.png)


    - '지역' 차원은 '국가/지역' 차원 안에 포함되어 있음
    - 지역별 매출 필드를 넣으면 국가/지역 차원에서 보여지더라도 지역 차원에서 계산된 매출의 합을 볼 수 있음

    2. FIXED에서 설정한 차원이 뷰에 포함되어 있지 않을 때

    ![5th_assignment_02](../5th_assignment(39~47)/5th_assignment_image/5th_assignment_02.png)

    - '지역' 차원에서 '범주'별 매출의 합을 표현하고 싶음

## 40. LOD EXCLUDE

<!-- INCLUDE, EXCLUDE, FIXED 등 본 강의에서 알게 된 LOD 표현식에 대해 알게 된 점을 적고, 아래 두 질문에 답해보세요 :) -->

> **🧞‍♀️ FIXED와 EXCLUDE을 사용하는 경우의 차이가 무엇인가요?**

- EXCLUDE LOD
    - 현재 뷰에서 특정 차원을 제외하여 계산할 때 사용
    - ex) 각 제품의 하위 범주에 따라 매출을 보기 위해서는 범주, 하위 범주 필드 수준까지 보여야 함 => 여기서 범주별 매출을 보기 위해서는 FIXED나 EXCLUDE 사용

    ![5th_assignment_03](../5th_assignment(39~47)/5th_assignment_image/5th_assignment_03.png)

    ![5th_assignment_04](../5th_assignment(39~47)/5th_assignment_image/5th_assignment_04.png)


```
1. 위의 예시에서 '하위 범주'보다 세부 수준인 '제조업체'까지 보게 되면 FIXED를 사용한 필드의 값은 변경되지 않지만 EXCLUDE를 사용한 필드의 값은 세부 수준인 '제조업체'의 매출의 합으로 바뀜

2. '하위 범주' 필드로 필터를 걸어 특정 하위 범주를 선택 해제하면 FIXED를 사용한 필드의 값은 변경되지 않지만 EXCLUDE를 사용한 필드의 값은 영향을 받음
```

> **🧞‍♀️ 왜 ATTR 함수를 사용하나요?**

```
EXCLUDE로 만든 계산된 필드의 값을 SUM([매출])을 통한 하위 범주 수준에서 계산할려면 ATTR 함수를 사용하여 집계 수준을 맞춘 뒤 계산해야 하기 때문
```


## 41. LOD INCLUDE

<!-- INCLUDE, EXCLUDE, FIXED 등 본 강의에서 알게 된 LOD 표현식에 대해 알게 된 점을 적고, 아래 두 질문에 답해보세요 :) -->

- INCLUDE LOD
    - 현재 뷰에서 특정 차원을 추가아여 계산할 때 사용

> **🧞‍♀️ 그렇다면 어떤 경우에 각 표현식을 사용하나요? 예시와 함께 적어보아요**


```
- FIXED LOD : 뷰에 표시되는 값이 차원인 경우 (FIXED LOD는 차원, 측정값을 반환)
- INCLUDE, EXCLUDE LOD : 반환 값이 차원 필터의 영향을 받게 되는 경우 (측정값만 반환)
```

## 42. 매개변수

<!-- 매개변수에 대해 알게 된 점을 적어주세요 -->

- 매개변수
    - 고정된 상수값이 아닌 동적인 값, 변경하기 위해서 활용하는 기능
    - 반드시 계산식, 필터, 참조선과 함께 사용됨

> **🧞‍♀️ 집합에도 매개변수를 적용할 수 있나요? 시도해봅시다**

```
됩니다
```

## 44. 매개변수 실습
(43번 강의가 없어 패스합니다)

<!-- 매개변수에 대해 알게 된 점을 적어주세요 -->

- 참조선

![5th_assignment_05](../5th_assignment(39~47)/5th_assignment_image/5th_assignment_05.png)

- 참조구간

![5th_assignment_06](../5th_assignment(39~47)/5th_assignment_image/5th_assignment_06.png)

## 45. 워크시트 마크카드

<!-- 마크카드에 대해 알게 된 점을 적어주세요 -->

- 드롭 다운 메뉴
    - 마크의 표현 방식 선택
- 색상
- 크기
- 레이블
    - 레이블의 텍스트, 폰트, 크기, 방향 
- 세부 정보
- 도구 설명


## 46. 서식 계층

<!-- 서식계층에 대해 알게 된 점을 적어주세요 -->

- 서식 계층 구조
![5th_assignment_07](../5th_assignment(39~47)/5th_assignment_image/5th_assignment_07.png)

> **🧞‍♀️ 서식계층을 일반적인 것에서 구체적인 것 순서로 기입해보세요**


```
워크 시트 서식
행 / 열 서식
특정 필드
필드 레이블
도구설명 / 제목 / 마크
```


## 47. 워크시트 서식

<!-- 워크시트 서식에 대해 알게 된 점을 적어주세요!-->

- 글꼴
    - 워크시트 내 표시되어 있는 텍스트들의 글꼴, 색상, 크기 설정
- 맞춤
    - 워크시트 내 표시되어 있는 텍스트들의 정렬, 방향 설정
- 음영
    - 워크시트 내 표시되어 잇는 데이터 셀의 음영 적용


## 문제 리스트

### 문제 1.

다음은 Tableau의 다양한 계산을 사용할 수 있는 경우를 빈칸으로 두고 문제를 작성한 것입니다. 각 빈칸에 적합한 계산 유형을 채워보세요.

보기
> **누계, 차이, 비율 차이, 구성 비율, 순위, 백분위수, 이동 평균, YTD 총계, 통합 성장률, 전년 대비 성장률, YTD 성장률**

| 계산 유형               | 설명                                                                 | 사용 예시                                                                                          |
|-------------------------|----------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------|
| 누계           | 데이터의 누적 합계를 계산                                             | 한 기업이 월별 매출 데이터를 누적하여 연간 매출 추이를 보고 싶을 때 사용                                      |
| 차이           | 연속 데이터 포인트 간의 차이를 계산                                    | 한 기업이 월별 매출 데이터에서 전월 대비 매출 증감량을 분석하고 싶은 경우                                        |
| 비율 차이           | 연속 데이터 포인트 간의 비율 변화를 계산                               | 한 기업이 월별 매출 데이터에서 전월 대비 매출 증감률(%)을 분석하고 싶은 경우                                      |
| 구성 비율            | 전체에서 각 데이터 포인트의 비율을 계산                                | 한 기업이 전체 매출에서 각 제품군이 차지하는 비율을 보고 싶을 때 사용                                           |
| 순위            | 데이터의 순위를 매깁니다                                              | 한 기업이 제품별 매출 데이터를 순위별로 정렬하여 상위 10개 제품을 분석하고 싶은 경우                              |
| 백분위수           | 데이터의 백분위를 계산                                               | 한 기업이 고객별 구매 금액 데이터를 백분위수로 나누어 상위 25% 고객을 분석하고 싶은 경우                          |
| 이동평균            | 일정 기간의 평균을 계산                                               | 한 기업이 주간 매출 데이터에서 4주 이동 평균을 계산하여 트렌드를 분석하고 싶은 경우                              |
| YTD 총계            | 연초부터 현재까지의 총계를 계산                                      | 한 기업이 월별 매출 데이터를 연초부터 현재까지 누적하여 연간 매출 목표 달성 여부를 분석하고 싶은 경우             |
| 통합 성장률          | 일정 기간 동안의 연평균 성장률을 계산                                  | 한 기업이 5년 간 매출 데이터를 바탕으로 연평균 성장률(CAGR)을 계산하고 싶은 경우                                  |
| 전년 대비 성장률            | 전년 동기간 대비 성장률을 계산                                        | 한 기업이 월별 매출 데이터에서 전년 동월 대비 매출 성장률을 분석하고 싶은 경우                                    |
| YTD 성장률ㅍ            | 연초부터 현재까지의 성장률을 계산                                     | 한 기업이 올해 연초부터 현재까지의 매출이 전년 동기 대비 얼마나 성장했는지 분석하고 싶은 경우                     |

> 사용 예시를 참고하여 실제 경우처럼 생각하며 고민해보아요 :)

## 문제 2.

```
가장 많이 주문한 사람들은 물건 배송을 빨리 받았을까요?
조건을 준수하여 아래 이미지를 만들어봆시다.
1) 국가/지역별(이하 '나라'로 통칭), 범주별로 배송일자가 다를 수 있으니 먼저, 나라별/범주별로 평균 배송일자를 설정한 뒤,
2) 각 나라에서 가장 많이 주문한 사람의 이름을 첫 번째 열,
3) 그 사람이 주문한 제품 이름을 2번째 열,
4) 각 상품이 배송까지 걸린 날 수를 표현하고
5) 그리고 만약 배송이 각 나라/범주별 평균보다 빨랐다면 '빠름', 같다면 '평균', 느리다면 '느림' 으로 print 해주세요. 
```

![이미지주소](https://github.com/yousrchive/BUSINESS-INTELLIGENCE-TABLEAU/blob/main/study/img/2nd%20study/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202024-08-13%20%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB%2010.12.36.png?raw=true)

<!-- 여기까지 오는 과정 중 알게 된 점을 기입하고, 결과는 시트 명을 본인 이름으로 바꾸어 표시해주세요.-->

1. 계산된 필드 '배송까지 걸린 일수' 생성

![5th_assignment_08](../5th_assignment(39~47)/5th_assignment_image/5th_assignment_08.png)

2. 계산된 필드 '나라별/범주별 평균 배송까지 걸린 일수' 생성
    - 문제에서는 국가/지역 차원과 범주 차원을 행 선반에 올려두지 않았기 때문에 FIXED LOD를 사용하여 국가/지역 차원과 범주 차원에서의 평균 배송 일자를 표현

![5th_assignment_09](../5th_assignment(39~47)/5th_assignment_image/5th_assignment_09.png)

3. 계산된 필드 '배송까지 걸린 일수'와 계산된 필드 '나라별/범주별 평균 배송까지 걸린 일수'를 비교하여 빠름, 평균, 느림이 나타나게 하는 계산된 필드 '배송 속도 수준' 생성

![5th_assignment_10](../5th_assignment(39~47)/5th_assignment_image/5th_assignment_10.png)

4. 결과
    - 행 선반에 고객 이름, 제품 이름, 배송 속도 수준 필드 드래그 앤 드랍
    - 마크 카드 색상에 '배송 속도 수준' 드래그 앤 드랍
    - 마크 카드 텍스트에 '배송까지 걸린 일수' 드래그 앤 드랍

![5th_assignment_11](../5th_assignment(39~47)/5th_assignment_image/5th_assignment_11.png)

## 문제 3.

```
채원이는 태블로를 쓰실 수 없는 상사분께 보고하기 위한 대시보드를 만들고 싶어요. 

제품 중분류별로 구분하되 매개변수로써 수익, 매출, 수량을 입력하면 저절로 각각 지표에 해당하는 그래프로 바뀌도록 설계하고자 해요.

 어떤 값이 각 지표의 평균보다 낮은 값을 갖고 있다면 색깔을 주황색으로, 그것보다 높다면 파란색으로 표시하고 싶어요. 그 평균값은 각 지표별로 달라야 해요.
```