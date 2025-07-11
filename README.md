# K_VAN Korea
<p align="center">
  <img width="500" height="250" alt="Image" src="https://github.com/user-attachments/assets/3cc09cba-ced2-4245-8fcc-9e1ca1b61b29" />
</p>

## 근무 스케줄 자동화 프로젝트 결과물

### 프로젝트 개요
목적 : 운전자 별 근무표 자동 생성, 구역별/운전자별 근무 통계, 월별·연간 급여 자동 산출 및 시각화\
주요 기능 : 

- 근무 패턴 자동 순환 및 공휴일 / 주말 패턴 적용
- 근무 구역 별 근무 시간·수당 자동 반영
- 엑셀 및 시각화 결과물 자동 생성


<div align="center"><h1>📚 STACKS</h1></div>

<div align="center">
<img src="https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
<img src="https://img.shields.io/badge/googlecolab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white" />
<img src="https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" />
<img src="https://img.shields.io/badge/openpyxl-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white" />
<img src="https://img.shields.io/badge/matplotlib-FF7F00?style=for-the-badge&logo=python&logoColor=white" />
<img src="https://img.shields.io/badge/holidays-0078D7?style=for-the-badge&logo=python&logoColor=white" />
</div>



## 주요 코드 구조

### 기본 설정

- 공휴일 자동 인식 : holidays 패키지 활용
- 평일/주말 추가시간 : weekday_add, weekend_add
- 주말/공휴일 1.5배 적용 구역 : weekend_15x 리스트

### 근무 패턴 정의

- 평일, 토요일, 일요일 패턴\
각 패턴은 운전자 수에 맞게 자동 순환 적용

### 스케줄 생성 로직

- 주요 함수:
     - make_schedule_with_majority_shift: 근무 패턴 및 운전자 순환 적용
     - schedule_to_dataframe: 스케줄 DataFrame 변환
     - apply_color_to_excel: 엑셀 시트 색상 자동 적용

### 근무 통계 및 급여 산출

- 구역별/운전자별 근무 집계:
    - count_work_by_driver_and_area
    - create_pivot_work_df

- 월별/연별 급여 계산:
    - calc_monthly_and_yearly_pay
    - 시급: 주휴수당 포함 12,036원 자동 반영

### 시각화

- 특정 날짜별 운전자 근무시간 시각화:
    - visualize_schedule_for_date 함수
    - 근무구역별 시작/종료시간, 이중차량 구역, 휴식시간 표시


## 산출물 예시

### 엑셀 파일 구조

- Schedule_sheet.xlsx
    - 1_근무스케줄 : 운전자별 1년치 일일 근무표
    - 2_구역별근무요약 : 구역별·운전자별 평일/주말/총 근무 횟수
    - 3_월별연간급여 : 운전자별 월별·연간 급여 집계

### 구역별 근무시간

<img width="349" height="387" alt="Image" src="https://github.com/user-attachments/assets/37c65a26-355d-4a9a-a351-1439e08765ae" />
<img width="349" height="369" alt="Image" src="https://github.com/user-attachments/assets/67c41065-4c7b-4137-b9ac-055403baefb1" />

### 1일 근무표 시각화

<img width="782" height="721" alt="image" src="https://github.com/user-attachments/assets/f88c3bc6-efc7-497a-bdad-3e5cf5deb660" />

## 사용 방법

1. 코드 실행 시 20255년 1월 1일부터 1년치 스케줄 자동 생성
2. 엑셀 파일 자동 저장 및 색상 적용
3. 원하는 날짜별 근무시간 시각화 가능\
(예시: visualize_schedule_for_date(schedule, date_list, data, drivers, "2025-07-12"))

## 참고 사항

- 공휴일 자동 반영, 근무구역별 시간/수당/패턴 모두 자동화
    - 주말 수당 x1.5
    - 야근 수당 x1.5
    - 주말 야근 수당 x 2

- 엑셀, 표, 시각화 등 결과물은 코드 실행 후 자동 생성됨
- 코드 및 결과물은 한글 환경(폰트, 공휴일 등 최적화)

- 근무표 출력 예시
<img width="1358" height="420" alt="Image" src="https://github.com/user-attachments/assets/b46b6ff7-6f30-4a3c-8a3c-2bca3083bbf5" />
