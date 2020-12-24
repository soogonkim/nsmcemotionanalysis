# nsmcemotionanalysis

# friendsemotionanalysis


<프로젝트 목적>
 - 2020 년 가을학기 임희석 교수님 수업(디지털 금융공학 위한 자연언어처리기술)의
   NSMC(한글 영화리뷰) 감정 분석 모델 구축

- 기 공개된 Source Code를 참조
  - https://github.com/deepseasw/bert-naver-movie-review

- 공개 된 코드분석 및 수정을 통해 주석을 달아 감정분석기 모델 이해도 증진 및 <br>
  감정분석 평가율 제고를 위해 노력했습니다.
  
 <이용 모델>
 - Bert Model
 
 <경로 및 max_len 설정>
 - Test Data 로서 ko_data 파일 사용
 - 결과 File 저장명 지정
 - utterance max 값 80으로 설정

<데이터 불러오기>
 - 학습 Data Type Dictionary형으로 정의
 - Data 확대를 위해 train+dev+test 전체 활용
 - Bert 이용 위한 전처리
 - Bert 모델 활용 위해, 클래스 구분자 '[CLS]'및 문장 구분자 '[SEP]'사용
 - 감정 레이블 Data를 category형으로 지정
 - Mapping : label을 str -> index(long)으로 변환

<데이터 전처리>
 - RoBERTa Model 활용 Token화 진행
 - Large 모델 활용
 - 대소문자 구분
  [RoBERTa] link
  https://brunch.co.kr/@choseunghyek/7
  https://blog.naver.com/beneyh3000/222074120459

<모델링>
 - RoBERTa Model 활용 진행
 - Optimizer adamw 설정
 - BERT-Large 정확도 향상 한계 존재 RoBERTa 모델 통해 정확도 향상

<Training 및 Validation>
 - Epoch 변경해 가며 반복
 - 제출 Data 예측
 
 # 사용데이터
   - friends_dev.json
   - friends_test.json
   - friends_train.json
   - en_data.csv
  # 실행 진행 과정
   - soogonKIM_2019516010_friends.ipynb을 구글 colab에서 GPU 사용해 실행하였고
   - 총 3Epoch 를 실행해서 Epoch 당 12분 정도 소요 되었으며
     (Epoch 를 3~6회 정도로 조정해 수행해 보았으나, 큰 개선은 없어 3Epoch로 최종결과물을 도출 하였습니다)
   - Test accuracy는 62.5% ~ 64.5% 정도가 나왔습니다.
   - 상기 사용데이터를 불러와 예측을 수행 하였습니다.
