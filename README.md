# Finger-Vein
가짜 지정맥 판별하기:hand:

**=> PPG를 이용한 가짜 손가락 정맥 데이터 감지**

### [ Data ] ###

- 850nm 적외선 조명기와 Logitech C600 웹캠으로 구성된 장치를 사용하여 얻은 실제 및 가짜 손가락 정맥 이미지 데이터를 기반으로 함

- 이미지의 공간 해상도와 캡처 프레임 속도는 각각 640 × 480 픽셀과 초당 30 프레임

- 실험자 20명에 대해 한명 당 4개의 영상을 취득하여 실제 및 가짜 손가락 정맥 데이터에서 각각 80개의 비디오 파일 얻음

- 하나의 비디오를 150개의 프레임으로 분할하는데 100개의 프레임과 겹치게 함

### [ Data Processing ] ###

과정 

1) 하나의 비디오를 frame을 받아온다.
2) frame 하나당 픽셀 평균 값을 구한다.
3) 150개의 프레임으로 분할하고 100개의 프레임이 겹쳐야 되기 때문에 픽셀 평균 값이 들어있는 리스트를 150간격으로 자르고 50씩 shift해서 frame크기 만큼 진행한다.
4) 150 간격으로 자른거를 주파수 변환한다.

*실험자 번호 짝수 : train 데이터 /  실험자 번호 홀수 : test 데이터*

### [ Model ] ###

주파수 변환한 것을 사진으로 변환해 CNN기반 모델 사용 => 해당 프로젝트에서는 VGG16 사용

<VGG 16 구조>

![image](https://user-images.githubusercontent.com/66320010/117974216-47f2d780-b368-11eb-9bc4-9a8814b76ae3.png)

![image](https://user-images.githubusercontent.com/66320010/117974275-58a34d80-b368-11eb-85e0-fc258ddaf995.png)
