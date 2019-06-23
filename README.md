#  세종대 인근 랜드마크 분류기 프로젝트
<p align="center">
<img src="https://user-images.githubusercontent.com/44772344/59923142-a3163b00-946d-11e9-8881-2a0250b3eb31.PNG">
</p>

## 목표

<p align="center">
<img src="https://user-images.githubusercontent.com/44772344/58701146-24cdf800-83dd-11e9-924d-4e5e247bfec3.png">
</p>

## 데이터셋 
**DataBase(DB)** : 직접 촬영한 데이터셋 / test : 직접 촬영한 데이터셋(train에 포함 x) + 네이버 로드뷰 캡쳐 

**클래스** : 장소(DB(776장),test(100장))

**0** : AI센터(182장,14장) 

**1** : 시계탑(108장,23장)

**2** : 어린이대공원 정문(170장,15장) 

**3** : 세종대 정문(98장,24장) 

**4** : 박물관(110장,17장) 

**5** :  석상(108장,7장) 

### [데이터셋 보기_train](https://drive.google.com/drive/folders/1bnuESMz_cti7Q3OIX_D9_qN-MgBlJznl?usp=sharing)
### [데이터셋 보기_test](https://drive.google.com/drive/folders/1ViFzzgWUzb2s2RVXTl49Ewpl-iFSRKuL?usp=sharing)

## 한달 진행상황
- 데이터 수집
- 학습을 위한 데이터 전처리
- 학습 모델 구현 및 정확도 테스트

## 전체 계획대비 진행상황
#### 완료
- 학습을 위한 데이터 전처리
- 학습 모델 구현 및 정확도 테스트
- 데이터 수집
- 데이터 추가 수집
- 기본 네트워크 변경하기 ( 현재 Resnet18을 VGG16, VGG19 등 여러 네트워크로 변경하기 )
- Image Retrieval 추가
- 모델 최적화


#### 진행 예정
- 데이터 추가 전처리 (밝기에 대한 민감도를 줄이기 위한 opencv를 활용한 이진화)
- 정확도가 낮은 요인 분석
- 데모 제작

#### 진행 코드
- [데이터전처리](https://github.com/socome/2019.Spring.AI_Leader/blob/master/%EB%8D%B0%EC%9D%B4%ED%84%B0_%EC%A0%84%EC%B2%98%EB%A6%AC_ipynb%EC%9D%98_%EC%82%AC%EB%B3%B8.ipynb)
---------------------------------------------------------------------------------------------------
- [1차 베이스라인 코드](https://github.com/suimn416/2019.Spring.AI_Leader/blob/master/VLADNet_jwkim.ipynb) 
  [[참고한 코드](https://github.com/lyakaap/NetVLAD-pytorch)]
---------------------------------------------------------------------------------------------------
- [2차 코드 - Train_code (pytorch)](https://github.com/socome/2019.Spring.AI_Leader/blob/master/VLADNet_jwkim_train.ipynb)
- [2차 코드 - Test_code (pytorch)](https://github.com/socome/2019.Spring.AI_Leader/blob/master/VLADNet_jwkim_test.ipynb) 
- [2차 코드 - Train/ Test code (keras/tensorflow)](https://github.com/glee1228/2019.Spring.AI_Leader/blob/master/netVLAD_triplet_keras.ipynb)
---------------------------------------------------------------------------------------------------
- [이미지 유사도 순위(top5)출력](https://github.com/socome/2019.Spring.AI_Leader/blob/master/VLADNet_jwkim_test_retrieval.ipynb)

---------------------------------------------------------------------------------------------------
- [최종 코드 - Train/ Test code (pytorch - 평가포함)](https://github.com/suimn416/2019.Spring.AI_Leader/blob/master/train.ipynb)

- [웹 애플리케이션 inference 코드 - Test code (pytorch)](https://github.com/suimn416/2019.Spring.AI_Leader/blob/master/infer.ipynb)



## 결과(TSNE을 통한 차원감소) [TSNE란?](https://bcho.tistory.com/1210)

##### train data set visualization
<p align="center">
<img width="460" height="300" src="https://user-images.githubusercontent.com/44772344/58684401-24b90280-83b3-11e9-9bbe-921b259c093b.png">
</p>

## 결과 (K-Nearest Neighbor Algorithm) [KNN란?](https://ko.wikipedia.org/wiki/K-%EC%B5%9C%EA%B7%BC%EC%A0%91_%EC%9D%B4%EC%9B%83_%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98)
<p align="center">
<img width="567" alt="TestImage" src="https://user-images.githubusercontent.com/26589942/59279004-1ebdfe00-8c9e-11e9-84fe-07910c06f499.png">
<img width="1070" alt="ResultImage" src="https://user-images.githubusercontent.com/26589942/59279009-2087c180-8c9e-11e9-9636-0964765bc13c.png">
</p>



## 이미지 검색 결과 평가 방법

- [Precision@K(P@K)](https://github.com/suimn416/2019.Spring.AI_Leader/issues/43)
- [Mean Average Precision(MAP)](https://github.com/suimn416/2019.Spring.AI_Leader/issues/43)


[논문](https://github.com/sejongresearch/2019.Spring.AI_Leader/issues/49)

[PPT](https://github.com/sejongresearch/2019.Spring.AI_Leader/issues/48)
