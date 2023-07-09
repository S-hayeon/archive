# Intro

- 홈플러스 GCP 프로젝트 - ETL pipeline부문 
  - Extract - n개의 OPEN API 제공처로부터 데이터를 추출한다
  - Transform - 추출한 데이터를 현업 사용처에 맞추어 가공한다
  - Load - 비가공 데이터를 data lake에, 가공한 데이터를 data-warehouse에 각각 저장한다

# Flow

<img width="1431" alt="Screen Shot 2023-06-16 at 3 32 34 AM" src="https://github.com/S-hayeon/archive/assets/25574165/71912b95-8759-4636-ba94-e04b8630b2af">



# Details

- API spec에 맞추어 request 생성
- dataframe으로 변환
- 데이터 가공
- csv형태로 스토리지 업로드
- DB insert

