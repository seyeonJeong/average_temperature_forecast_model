# average_temperature_forecast_model


### Introduction

---

간단한 머신러닝 알고리즘을 이용한 서울의 평균기온 예측 프로그램이다.


![model](https://github.com/seyeonJeong/average_temperature_forecast_model/blob/main/%ED%8F%89%EA%B7%A0%EA%B8%B0%EC%98%A8%20%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8%20%EB%AA%A8%EB%8D%B8.PNG)


출력층을 제외한 활성화함수는 relu를 사용하였고, 출력층에는 사용하지 않았다. (분류 모델의 경우 softmax, sigmoid etc.. 사용가능, 해당 모델의 경우 출력값을 그대로 이용한다.)

optimizer은 adam, 손실함수는 MSE를 사용하였다. epoch는 2000을 사용하였는데, earlystopping 기능을 통해 validation loss가 일정 횟수(본 모델에서는 50회) 변하지 않는다면 학습을 종료한다.

![loss](https://github.com/seyeonJeong/average_temperature_forecast_model/blob/main/loss%EA%B0%92.PNG)

최종 loss값은 loss: 13.7553, validation_loss : 12.4566 이 출력되었다.

![real_pred_temp](https://github.com/seyeonJeong/average_temperature_forecast_model/blob/main/%EC%8B%A4%EC%A0%9C%EC%98%A8%EB%8F%84%EC%98%88%EC%83%81%EC%98%A8%EB%8F%84.PNG)

실제 평균 기온과 예상 평균 기온을 test dataset과 predicted dataset을 비교하였다. 비슷한 경향성을 보이는 것을 확인할 수 있다.

