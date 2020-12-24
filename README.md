# nsmcemotionanalysis

<프로젝트 목적>
 - 2020 년 가을학기 임희석 교수님 수업(디지털 금융공학 위한 자연언어처리기술)의
   NSMC(한글 영화리뷰) 감정 분석 모델 구축

- 기 공개된 Source Code를 참조
  - https://github.com/deepseasw/bert-naver-movie-review

- 공개 된 코드분석 및 수정을 통해 주석을 달아 감정분석기 모델 이해도 증진 및 <br>
  감정분석 평가율 제고를 위해 노력했습니다.
  
 <이용 모델>
 - BERT Model
 - Test Data 로서 ko_data 파일 사용
 - 결과 File 저장명 지정
 - Hugging Face의 트랜스포머 모델 활용

<진행 순서>
 - 네이버 영화리뷰 감정분석 데이터 다운로드
 - 판다스로 훈련셋과 테스트셋 데이터 로드
 - BERT 입력 형식에 맞게 변환
 - BERT 토크나이저로 문장을 토큰으로 분리
 - 입력 토큰 최대 시퀀스 길이(MAX_LEN=128)
 - 토큰을 숫자 인덱스로 변환
 - 문장을 MAX_LEN 길이에 맞게 자르고, 부족 부분을 패딩 0으로 채움
 - 어텐션 마스크 초기화
 - 훈련셋과 검증셋으로 분리
 - Batch_size = 32

<모델링>
 - RoBERTa Model 활용 진행
 - Optimizer adamw 설정
 - BERT-Large 정확도 향상 한계 존재 RoBERTa 모델 통해 정확도 향상

<Training 및 Validation>
 - Epoch 변경해 가며 반복
 - 제출 Data 예측
 
 # 사용데이터
   - https://github.com/e9t/nsmc.git(네이버 영화리뷰 감정분석 데이터)
   - ko_data.csv
  # 실행 진행 과정
   - soogonKIM_2019516010_nsmc_emotion_analysis을 구글 colab에서 GPU를 사용해 실행하였고
   - 총 3Epoch 를 실행해서 Epoch 당 20분 정도 소요 되었으며
     (Epoch 를 3~6회 정도로 조정해 수행해 보았으나, 큰 개선은 없어 4Epoch로 최종결과물을 도출 하였습니다)
   - Test accuracy는 87% 정도가 나왔습니다.
   - 상기 사용데이터를 불러와 예측을 수행 하였습니다.
