# cloth-classification


## 의상을 가지고 있는 특성에 따라 구분할 수 있도록 만든 모델을 목표로함 

# 1. inner, outer, pants, top 4가지로 먼저 나누어 인식하게 만듬.


# 2. 이너나 아우터중 가지고 있는 패턴에 따라 check, herringbone, solid, stripe, window 5가지의 패턴으로 나뉠 수 있게 만듬.


# 3. 마지막으로 옷이 가장 많이 함유하고 있는 색상을 추출하여 나타나게 함.



# model : resnet에 대해 공부하던 중이였기 때문에 resnet을 사용하여서 진행함.

![image](https://user-images.githubusercontent.com/62790857/212640724-c7a94eca-e49f-4807-93d9-8d45277b93da.png)

먼저 패턴 모델을 학습하기 위해 준비한 상태

앞서 말한 5가지의 패턴과 라벨링 과정임.

![image](https://user-images.githubusercontent.com/62790857/212640942-9c7fdd51-5289-4633-bf62-7537dc492cf6.png)


모델 구축


![image](https://user-images.githubusercontent.com/62790857/212641001-23d455d2-c218-474d-8d64-0d864a8bcbe4.png)


학습 완료 후 정확도 확인



![image](https://user-images.githubusercontent.com/62790857/212641044-70b9f998-a6b8-4a05-be8b-99e62eaa135f.png)


결과





파츠 모델도 똑같이 학습 후 결과를 출력 해봄.

![image](https://user-images.githubusercontent.com/62790857/212641295-81fe75e0-fc93-487e-9b00-5fe9636babda.png)



색상 모델 : k-menas 클러스터를 이용해
가장 색을 많이 차지하는 군집을 선택하여 그 rgb좌표를 옷이 대표하는 색상으로 선택하기로 함.

centroids는 임의로 4개로 지정하고 진행

![image](https://user-images.githubusercontent.com/62790857/212641583-e4817c60-e7cf-4856-b3d0-edc00edcb73f.png)


rgb 값 도출 및 비율 출력

![image](https://user-images.githubusercontent.com/62790857/212641694-91f96ff0-4ebe-41ac-aaf4-c10e04f58ce0.png)


학습 결과를 이미지화

![image](https://user-images.githubusercontent.com/62790857/212641794-48f11fd1-ed5e-4f0a-89cb-d7e75e576d0c.png)





