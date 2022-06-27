# RCNN을 이용한 차량 객체 탐지

## RCNN이란
Region-based Convolutional Neural Network. CNN과 region proposal 알고리즘을 연결하여 객체 탐지를 수행하는 two-stage 신경망 아키텍쳐이다. CNN을 이용하여 이미지 분류를 수행하고 region proposal을 이용하여 이미지 내 객체(objects)의 위치를 표시(localization)한다.

## 프로젝트 가설 설정
RCNN으로 실제 자율주행 시스템에서 사용가능한 차량 객체 탐지 모델을 훈련할 수 있다.

## 데이터셋
차량 외 다른 객체가 거의 없는 데이터셋으로, 차량 객체 탐지 모델을 학습하기에 적합하다. 다른 객체가 없어 모델 성능이 잘 나오므로, 다른 객체를 많이 포함하는 이미지 데이터셋으로 학습한 모델에 대해 해당 모델을 비교 대상으로 이용할 수 있다.

## 모델 구조
* 사전 학습 모델: VGG16(imagenet 데이터로 학습)
* selectvie search: 2000개의 region proposal을 뽑음
* CNN: 앞에서 나온 region들에 대해, 즉 2000번 만큼 CNN을 수행. 여기에서 특성 벡터를 추출
* SVM: 추출된 특성 벡터를 기반으로 분류기 학습

## 실험 결과
