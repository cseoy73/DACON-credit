#### LGBM



##### LGBM이란?	

​	light GBM을 의미

​	트리 기반의 학습 알고리즘인 gradient boosting 방식의 프레임워크

​	가볍고 속도가 빠르며, 정확도가 높다

​	*과적합에 민감(데이터의 개수가 10,000개 이상일 때 추천)



##### 다른 트리 기반 알고리즘과 다른점?

​	LGBM은 나무를 수직으로 확장 

→  수평으로 확장하는 알고리즘보다 낮은  loss 달성

​	*데이터가 작은 경우 과적합되기 쉬우므로 max_depth를 줄여줘야 함



##### 설치

​	가상환경 activate 후,

​	conda install -c conda -forge lightgbm

​	(pip install lightgbm으로 설치는 되나, import가 안되었다)



##### 주요 파라미터

1. objective
   * regression : 회귀 모델
   * binary : 분류 모델
   * multiclass
   * ....
2. metric
   * mae
   * rmse
   * mape
   * binary_logloss
   * ....
3. learning_rate : 일반적으로 0.01 ~ 0.1, 성능 높일 때 줄임
4. num_iterations : 기본값 100, 보통 1000을 권장, 너무 크면 과적합
5. max_depth : -1의 경우 제한없이 분기, feature가 많으면 크게 설정
6. boosting : 부스팅 방법
   * gdbt(default) : traditional Gradient Boosting Decision Tree
   * rf : Random Forest
   * dart : Dropouts meet Multiple Additive Regressin Tree
   * goss : Gradient-based One-Side Sampling
7. bagging_fraction : 배깅을 위해 랜덤 샘플링하여 학습에 사용, 0 < fraction <= 1
8. feature_fraction : 1보다 작은경우 매 iteration마다 다른 feature를 랜덤하게 추출하여 학습(ex. 0.8 - feature의 80%만 랜덤하게 선택)
9. scale_pos_weight : 기본값 1, 불균형의 데이터 셋에서 weight를 주는 방식으로 positive 조정
10. early_stopping_round : Validation 셋에서 평가지표가 더 이상 향상되지 않으면 학습 정지
11. 

