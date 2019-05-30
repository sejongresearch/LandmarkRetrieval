#  세종대 인근 랜드마크 분류기 프로젝트

### 한달 진행상황
- 데이터 수집
- 학습을 위한 데이터 전처리
- 학습 모델 구현 및 정확도 테스트

### 전체 계획대비 진행상황
#### 완료
- 학습을 위한 데이터 전처리
- 학습 모델 구현 및 정확도 테스트
- 데이터 수집
#### 진행 예정
- 데이터 추가 수집
- 기본 네트워크 변경하기 ( 현재 Resnet18을 VGG16, VGG19 등 여러 네트워크로 변경하기 )
- 데이터 추가 전처리 (밝기에 대한 민감도를 줄이기 위한 opencv를 활용한 이진화)
- 정확도가 낮은 요인 분석
- 모델 최적화
- 데모 제작

#### 진행 코드
- [데이터전처리](https://github.com/socome/2019.Spring.AI_Leader/blob/master/%EB%8D%B0%EC%9D%B4%ED%84%B0_%EC%A0%84%EC%B2%98%EB%A6%AC_ipynb%EC%9D%98_%EC%82%AC%EB%B3%B8.ipynb)
- [전체 모델 (현재 정확도 = 0.71)](https://github.com/suimn416/2019.Spring.AI_Leader/blob/master/VLADNet_jwkim.ipynb) 
  [[참고한 코드](https://github.com/lyakaap/NetVLAD-pytorch)]
- [전체 모델 (keras 버전) 구현 중(미완)](https://drive.google.com/file/d/1OyTXv6IG5E1Uq1ASOLUc9dz-kyDvu-Si/view?usp=sharing)

- [Train_code](https://github.com/socome/2019.Spring.AI_Leader/blob/master/VLADNet_jwkim_train.ipynb)

![Train_loss](https://user-images.githubusercontent.com/44772344/58648839-935f7700-8345-11e9-8532-b1abfe4930e4.PNG)</br>
<학습시 로스가 떨어지는 모습>

- [Test_code](https://github.com/socome/2019.Spring.AI_Leader/blob/master/VLADNet_jwkim_test.ipynb) 

### 문제점
기숙사의 경우 정확도 0퍼센트</br>
기숙사는 AI센터 or 세종대 정문으로 분류(AI센터는 그렇다해도 세종대 정문은 무엇..?)</br>
-> 확인이 
