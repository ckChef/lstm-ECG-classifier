# lstm-ECG-classifier
---

# 개요

## 신경망의 목적

심전도 데이터 상의 부정맥 신호 패턴을 학습하여 정상 심전도와 부정맥 상태를 구분

## 신경망 구조

### lstm layer

- 3개의 layer
- 5개의 hidden size
- bidirectional lstm

### FC layer

- 10 - 128 - 64 - 5
- 분류하려는 클래스의 갯수가 5개이므로 최종 레이어에서 5개의 출력

## data set

RCNN 모델을 이용한 부정맥 신호 인식에 관한 논문[1]의 저자가 가공해놓은 데이터셋[2] 이용하였음  
training data 87533개, test data 21891개로 구성

신경망의 구조는 해당 논문을 소개한 블로그[3]에서 참고하여 코드로 구현하였음



---

# 결과

- 21890개의 test data중 20177개를 알맞게 분류

---

# 개선이 필요한 사항

- 배치 정규화 등 모델 최적화 방법이 적용되지 않았으며 해당 방법들의 적용을 통해 모델의 정확도를 높이는 것이 필요
- 5개의 클래스 중 모델의 추정 클래스와 label의 클래스가 같은지만 고려하며 정확도를 평가하였음. 따라서 f1 score등 더 정량적인 모델의 평가가 필요

---

# References

## [1]참고논문

- [ECG Heartbeat Classification: A Deep Transferable Representation Mohammad Kachuee, Shayan Fazeli, Majid Sarrafzadeh University of California, Los Angeles (UCLA) Los Angeles, USA](https://arxiv.org/abs/1805.00794)

## [2]데이터셋

- [ECG Heartbeat Categorization Dataset Segmented and Preprocessed ECG Signals for Heartbeat Classification](https://www.kaggle.com/shayanfazeli/heartbeat)

## [3]신경망 구조 참조 블로그

- [심전도(ECG)에 나타나는 이상 패턴을 자동으로 탐지할 수 있을까?](https://inforience.net/2019/04/28/ecg_classification/)
