버섯의 클래스별로 Gradient Boosting 알고리즘을 사용하여 100%의 train과 test 정확도를 얻을 수 있었습니다.

버섯 feature csv파일은 [Kaggle](https://www.kaggle.com/uciml/mushroom-classification) 에서 다운받았습니다.

Gradient Boosting 모델은 랜덤포레스트보다 더 적은 수의 트리를 사용하며 learning rate을 추가한 모델입니다.

이전 트리의 오차를 보완하며 순차적으로 트리를 만들어 나갑니다.

<span style="color: green"> LabelEncoder </span>를 임포트해서 각 feature 열의 알파벳을 숫자로 변환하여 줍니다.

이전 drug classification의 경우 파이썬으로 직접 a->0, b->1, c->2 로 수정해 주었다면, LabelEncoder를 통해 이 과정을 손쉽게 for문으로 해결할 수 있습니다.

class를 포함한 모든 열의 문자를 숫자로 변경해주고 모델에 넣어주었습니다.

이번 실습에서는 <span style="color: green"> heatmap </span>을 이용하여 각 feature간의 상관관계를 확인하였습니다.

상관관계가 클수록 1.0에 가까운 수로 나오고, 상관관계가 반비례 관계 일수록 -1.0에 가까운 수로 나옵니다.

또한 <span style="color: green"> df.hist() </span>를 통해 각 feature들이 어떤 비중으로 구성되어 있는지를 확인하였습니다. 

만약 해당 feature의 변수가 하나만 있거나 거의 미미한 것이 눈으로 확인되면 해당 feature는 df.drop으로 제거해주었습니다.

이번에도 <span style="color: green"> model.feature_importances_ </span>로 학습 후에 각 feature의 중요도를 확인해 볼 수 있었습니다.

<span style="color: green"> classification_report(y_true, y_pred) </span>를 통해 precision, recall, f1-score 결과도 확인해 볼 수 있었습니다.

최종적으로는 <span style="color: green"> Confusion matrix </span>로 각 클래스당 정답을 얼마나 예측했는지 확인해보았습니다.
