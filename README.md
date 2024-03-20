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



### Result


---



![result](https://github.com/seyeonJeong/average_temperature_forecast_model/blob/main/%EA%B2%B0%EA%B3%BC.PNG)


마치 평균 기온 예측 프로그램처럼 만들어서 적용하였다. 월(month)가 변함에 따라 평균 기온도 크게 변하였고, 위 사진의 10월을 보면 10월 초와 10월 말의 차이도 유의미하게 발생한것을 보아 일(day)에도 영향을 받는다.




### Conclusion

---



딥러닝 프로그래밍 공부를 시작하며 이전에 날씨 빅데이터를 활용한 프로젝트를 진행한 적이 있는데 해당 데이터셋으로 인공지능에 접목시켜 평균 기온 예측 프로그램을 만들어보게 되었다.

모델을 만들때 Dense층의 개수와 노드 개수를 적게 설정하였는데 loss값이 110에서 내려가지를 않아서, 층과 노드 개수를 늘려 loss를 10 미만으로 감소시켰다.

당연하게도 실세계에서 사용하기에는 무리가 있지만, 기온 (특히, 평균 기온)의 경우에는 계절의 영향을 많이 받기 때문에 연도, 월, 일의 정보로도 엇비슷한 결과를 도출해낼 수 있었다고 생각한다.

추후 지식이 더 깊어진다면 더욱 강건한 모델을 제작할 수 있을 것으로 예상한다.

