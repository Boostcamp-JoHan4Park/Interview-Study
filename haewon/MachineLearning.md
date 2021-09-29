# Machine Learning

## Questions  
* [알고 있는 metric에 대해 설명해주세요.](#1)  
* [Cost Function과 Activation Function은 무엇인가요?](#2)  
* [Tensorflow, PyTorch 특징과 차이가 뭘까요?](#3)  
* [Data Normalization은 무엇이고 왜 필요한가요?](#4)  

## Answers  
### #1 todo. 수학수식 넣기, 사진 크기 조정, 내용 보충
- *Classification Metrics (accuracy, precision, recall, F1-score, ROC, AUC)*
- *Regression Metrics (MSE, MAE)*
- *Ranking Metrics (MRR, DCG, NDCG)*
- *Statistical Metrics (Correlation)*
- *Computer Vision Metrics (PSNR, SSIM, IoU)*
- *NLP Metrics (Perplexity, BLEU score)*
- *Deep Learning Related Metrics (Inception score, Frechet Inception distance)*
---
- MSE(평균 제곱 오차) : 
  오차에 제곱이 되기 때문에 이상치(outlier)를 잡아내는 데 효과적
- MAE(평균 절대값 오차) : 
  변동치가 큰 지표와 낮은 지표를 같이 예측하는 데 효과적
- RMSE : MSE값에 루트
- RMAE : MAE값에 루트
- Accuracy, Recall, Precision

    Accuracy : 올바르게 예측된 데이터의 수를 전체 데이터의 수로 나눈 값

    Recall : 실제로 True인 데이터를 모델이 True라고 인식한 데이터의 수

    Precision : 모델이 True로 예측한 데이터 중 실제로 True인 데이터이 수

![image](https://user-images.githubusercontent.com/49435163/134614742-e666d846-18c3-4d6f-b21a-5b46d7a256ad.png)

- F1 score  :
  precision 과 recall의 조화평균

### #2
정규화는 학습과정에서 scale이 큰 feature가 다른 feature를 지배하는 것을 막기위해 데이터 분포를 고르게 만들어 줍니다. 데이터 정규화를 통해 학습을 더 빨리하고 Local Minima에 빠지게 될 가능성을 줄일 수 있습니다. 

- Min-Max Normalization
- Z-Score Normalization
- 
### #3
많은 local minimum들 중 loss가 가장 최소가 되는 부분이 global minimum이다. 즉 최적의 파라미터를 찾는데 있어서 local minima에 빠지게 되면 global minima를 찾기 힘들어지게 된다.
![image](https://user-images.githubusercontent.com/49435163/134620219-69dc81ba-9093-45ad-8456-f5f6bb58f3f8.png)


### #4
차원이 커질수록 데이터가 상대적으로 희박해지는 문제로 KNN분류 알고리즘에서 흔하게 발생하는 문제이다. 이를 해결하기 위해 차원 축소 알고리즘을 사용한다.
![image](https://user-images.githubusercontent.com/49435163/134620157-31a9c51c-4e08-4a2c-acfa-2e7fb2019361.png)


