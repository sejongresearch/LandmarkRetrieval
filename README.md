#  세종대 인근 랜드마크 분류기 프로젝트

## 목표

<p align="center">
<img src="https://user-images.githubusercontent.com/44772344/58701146-24cdf800-83dd-11e9-924d-4e5e247bfec3.png">
</p>

## 데이터셋 
### train : 직접 촬영한 데이터셋 / test : 직접 촬영한 데이터셋(train에 포함 x) + 네이버 로드뷰 캡쳐 

### 클래스 : 장소(train,test)
### 0 : AI센터(169장) 
### 1 : 시계탑(98장,15장)
### 2 : 어린이대공원 정문(160장,15장) 
### 3 : 세종대 정문(89장,15장) 
### 4 : 박물관(101장,15장) 
### 5 :  석상(95장,15장) 
### 6 : 기숙사(33장,15장)


## 한달 진행상황
- 데이터 수집
- 학습을 위한 데이터 전처리
- 학습 모델 구현 및 정확도 테스트

## 전체 계획대비 진행상황
#### 완료
- 학습을 위한 데이터 전처리
- 학습 모델 구현 및 정확도 테스트
- 데이터 수집
#### 진행 예정
- 데이터 추가 수집
- 기본 네트워크 변경하기 ( 현재 Resnet18을 VGG16, VGG19 등 여러 네트워크로 변경하기 )
- 데이터 추가 전처리 (밝기에 대한 민감도를 줄이기 위한 opencv를 활용한 이진화)
- Image Retrieval 추가
- 정확도가 낮은 요인 분석
- 모델 최적화
- 데모 제작

#### 진행 코드
- [데이터전처리](https://github.com/socome/2019.Spring.AI_Leader/blob/master/%EB%8D%B0%EC%9D%B4%ED%84%B0_%EC%A0%84%EC%B2%98%EB%A6%AC_ipynb%EC%9D%98_%EC%82%AC%EB%B3%B8.ipynb)
- [전체 모델 (현재 정확도 = 0.71)](https://github.com/suimn416/2019.Spring.AI_Leader/blob/master/VLADNet_jwkim.ipynb) 
  [[참고한 코드](https://github.com/lyakaap/NetVLAD-pytorch)]
- [전체 모델 (keras 버전) 구현 중(미완)](https://drive.google.com/file/d/1OyTXv6IG5E1Uq1ASOLUc9dz-kyDvu-Si/view?usp=sharing)

- [Train_code](https://github.com/socome/2019.Spring.AI_Leader/blob/master/VLADNet_jwkim_train.ipynb)

- [Test_code](https://github.com/socome/2019.Spring.AI_Leader/blob/master/VLADNet_jwkim_test.ipynb) 

#### 문제발생 (진행중)
기숙사의 경우 정확도 0퍼센트</br>
기숙사는 AI센터 or 세종대 정문으로 분류(AI센터는 그렇다해도 세종대 정문은 무엇..?)</br>
-> 확인이 필요

## 결과(TSNE을 통한 차원감소) [TSNE란?](https://bcho.tistory.com/1210)

##### train data set visualization
<p align="center">
<img width="460" height="300" src="https://user-images.githubusercontent.com/44772344/58684401-24b90280-83b3-11e9-9bbe-921b259c093b.png">
</p>

##### test data set visualization
<p align="center">
<img width="460" height="300" src="https://user-images.githubusercontent.com/44772344/58684571-a90b8580-83b3-11e9-9084-977ba7c185a9.png">
</p>



              precision    recall  f1-score   support                confusion matrix
                                                                      0  1  2  3  4  5  6
           0       0.60      1.00      0.75        15                15  0  0  0  0  0  0
           1       1.00      0.93      0.97        15                 1 14  0  0  0  0  0
           2       0.87      0.87      0.87        15                 0  0 13  2  0  0  0
           3       0.62      0.87      0.72        15                 0  0  0  0 15  0  0
           4       1.00      1.00      1.00        15                 0  0  0  0  0 15  0
           5       1.00      1.00      1.00        15                 0  0  0  0  0 15  0
           6       0.00      0.00      0.00        15                 9  0  0  6  0  0  0

